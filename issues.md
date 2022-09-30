# Issues

## Fixed

### GitHub Api Rate Limit

GitHub has a API call limit of 5000 per hour per user. Previous logic makes an api call for every file in the repository whenever a document is published or updates are made through github. The api calls are made with the github token, an identifier to prove that you are a particular github account, of the person that published the documentation.

This combined with the usage of Multi-Doc Repo Structure, where a change to any files in the repository retriggers a publishing flow for all the documents tied to the repository, the limit was easily getting exceeded.

For example, if a repository have `500 files` in total and also have 2 folders that are published as individual documents. If one were to make a change to a file in one of the folder, this will retrigger the publishing flow for the other folder as well. Meaning our backend will start to process `2 * 500 number of api calls` where 2 is the no. of folders published as documents. If this is done a few times or if there were more folders, it will exceed the limit of 5000 easily.

Solution:
Instead of making 1 api call for 1 file, we changed it to making 1 api call to fetch the entire repository in a zipped form, after which we will do some processing and upload it to our storage. This way, as per our previous example, instead of `2 * 500` it will become `2 * 1 api call for zipped repo`. This will reduce the chance of hitting the api limit greatly.

## Backlog

### Tracking of repo size & displaying meta data

We are planning ot have a way of tracking repo sizes in  our internal dashboard as well as to display some meta data for users to see on doc portal for each doc. For example we could display the size and number of files.

### Inaccurate display of last commit

Current display of last commit is inaccurate as it appears even though documents may not have yet finished uploading, when the name of document is changed and publishing flow is retriggered ,and when changes are pushed to github.

### Optimised doc updating flow

Our current logic is to fetch entire repository no matter how big the changes are. This was to tackle github's api rate limit but may cause inefficiencies for small changes. Since even a change to just 1 will retrigger fetching and processing of entire repo.