# Limitations

There are some limitations that doc portal has and this portion of the document will go through them.

## Maximum Folder Size

Doc Portal currently can support up to `2gb` of repository size. Bigger than this and it will not publish properly.

We reasoned that `2gb` limit would be more than enough for most publishers as currently the biggest document size is around `100mb`. However, we will be monitoring the documents' sizes and if we see a general upward trend going past `1gb` we will start to work on improving scalability.

Per our tests, 

- `109mb` takes around `10 seconds` to complete publishing
- `2gb` takes around `3 ~ 4 minutes` to complete publishing

In the future, we are also thinking of displaying some metadata in the team docs page, which will include documentation size. However in the meantime, here are some ways in which you could check the size of your repository : 

1. Use file explorer or finder in local to get the file size
2. Use command `du -sh {path to folder e.g /Users/yannyeinaung/doc-publisher-guide}` (you can run `pwd` to get path of current directory)
3. Call github api in browser `https://api.github.com/repos/{owner}/{repo}` e.g `https://api.github.com/repos/sg-developer-portal/doc-portal-publisher-guide` which will return a json object with `size` key which will display the size of repo in KB. Only works with public repos.

## Maximum Files in One Folder

Doc Portal has a limit of `3500 files for every directory(folder)` and any more than this could slow down publishing time. This is in accordance to [S3's Request Limit](https://aws.amazon.com/premiumsupport/knowledge-center/s3-request-limit-avoid-throttling/). A `folder` is defined by the prefixes before the last `/` and a `file` is anything that's not a folder, consider this folder example:

- root-lvl-dir/
  - sub-dir/
    - sub-item.md
  - item.md

`root-lvl-dir` has `item.md `as a file and can have 3499 more of such files but `sub-dir` is not considered a file of `root-lvl-dir` since it's a folder. Similarly, `sub-item.md` is considered to be a file under `sub-dir` or more accurately, `root-lvl-dir/sub-dir` and can have 3499 more files.

## Discourage of Multi-Doc Repo Structure

A Multi-Doc Repo Structure is when there are multiple folders within the repository that are used to create to create its own document in Doc Portal. For e.g:

- root-lvl-dir/
  - sub-dir/
    - sub-item.md
  - sub-dir-2/
    - sub-item-2.md

The folders `sub-dir` and `sub-dir-2` are used to create separate documents in doc portal. Even the `root-lvl-dir` could be used to create a dcoument. 

The way our publishing flow and backend logic is set up, it does not support this type of structuring well. Here are a few reasons:

   1. It could increase publishing and updating time since these are relative to size of th repository and not the size of the sub folders
   2. Repository may exceed our support threshold of `2gb`
   3. When an update is made to a sub folder (`sub-dir`) through github, it will retrigger the publishing flow for all of the documents tied to this repository

**We are working on solutions to fix this but we are discouraging it in the meantime as it could dampen your Doc Portal experience.**

## Inaccurate Last Commit Display

When publishing big files, the last commit detail might appear even though not all the files are done publishing yet. We are working on a better way to display data for this.

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
