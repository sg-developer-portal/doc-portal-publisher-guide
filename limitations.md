# Limitations

There are some limitations that doc portal has and this portion of the document will go through them.

## Maximum Folder Size

Doc Portal currently can support up to `2gb` of repository size. Bigger than this and it will not publish properly.

We reasoned that `2gb` limit would be more than enough for most publishers as currently the biggest document size is `200mb`. However, we will be monitoring the documents' sizes and if we see a general upward trend going past `1gb` we will start to work on improving scalability.

Per our test, to publish a repo size of `2gb` it takes around `4 ~ 5 minutes`

In the future, we are also thinking of displaying some metadata, which will include documentation size, in the team docs page. But in the meantime, here are some ways in which you could check the size of your repository : 

1. Use file explorer or finder in local to get the file size
2. Use command `du -sh {path to folder e.g /Users/yannyeinaung/doc-publisher-guide}` (you can run `pwd` to get path of current directory)
3. Call github api in browser `https://api.github.com/repos/{owner}/{repo}` e.g `https://api.github.com/repos/sg-developer-portal/doc-portal-publisher-guide` which will return a json object with `size` key which will display the size of repo in MB. Only works with public repos.

## Maximum Files in One Folder

Doc Portal has a limit of `3500 files for every directory(folder)` and any more than this could slow down publishing time. This is in accordance to [S3's Request Limit](https://aws.amazon.com/premiumsupport/knowledge-center/s3-request-limit-avoid-throttling/). A `folder` is defined by the prefixes before the last `/` and a `file` is anything that's not a folder, consider this folder example :

- root-lvl-dir/
  - sub-dir/
    - sub-item.md
  - item.md

`root-lvl-dir` has `item.md `as a file and can have 3499 more of such files but `sub-dir` is not considered a file of `root-lvl-dir` since it's a folder. Similarly, sub-item.md is considered to be a file under `sub-dir` or more accurately, `root-lvl-dir/sub-dir` and can have 3499 more files.

## Inaccurate Last Commit Display

When publishing big files, the last commit detail might appear even though not all the files are done publishing yet. We are working on a better way to display data for this.

# Issues

- [ ] Inaccurate display of last commit
- [ ] Long wait on UI when slug name is changed and saved
- [ ] Even when 1 file is changed, whole repo needs to be fetched
- [ ] Tracking of repo sizes in our internal dashboard