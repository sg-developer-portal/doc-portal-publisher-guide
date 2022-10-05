# Issues

## Fixed

### GitHub Api Rate Limit

GitHub has a API call limit of 5000 per hour per user. Before this fix any document published or updated through github, each file in the repository would make one api call. The api calls are authenticated by github token tied to individual github user account.

Combined with the usage of Multi-Doc Repo Structure, where a single change to any file in the repository re-triggers a publishing flow for all the documents tied to the repository, the limit was easily getting exceeded.

For example, consider a repository with `500 files` in total with `2 sub-folders`, each sub-folder is published as individual documents. Making a change to any file in the repository will trigger the publishing flow for both of the documents tied to these sub-folders even if no changes were made to files under them. Meaning our backend will start to process `2 * 500 number of api calls` where 2 is `the no. of folders published as documents`. Hence the rate limit of 5000 api calls will be exceeded when publishing multiple times or large amount of documents.

Solution:
Instead of making 1 api call for 1 file, we changed it to making 1 api call to fetch the entire repository in a zipped form, after which the document is processed and uploaded to our storage. This way, as per our previous example, instead of `2 * 500` it will become `2 * 1 apicall for zipped repo`, reducing the chances of hitting the api limit significantly.

## Backlog

### Tracking of repo size & displaying meta data

We are planning to have a way of tracking repo sizes in  our internal dashboard as well as to display some meta data for users to see on doc portal for each doc. For example we could display the size and number of files.

### Inaccurate display of last commit

Current display of last commit is inaccurate as it appears even though documents may not have yet finished uploading, when the name of document is changed and publishing flow is re-triggered ,or when changes are pushed to github.

### Optimised doc updating flow

Our current logic is to fetch entire repository no matter how big the changes are. This was to tackle github's api rate limit but may cause inefficiencies for small changes. Since even a change to just 1 will re-trigger fetching and processing of entire repo.