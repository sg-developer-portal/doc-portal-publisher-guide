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