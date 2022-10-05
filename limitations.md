# Limitations

There are some limitations that doc portal has and this portion of the document will go through them.

## Maximum Folder Size

Doc Portal currently can support documents with repository size up to `2gb`.
   
Considerations on 2gb limit: Current the biggest document size is around 100mb. However, we will be monitoring the documents' size growth closely, and make necessary adjustment if needed.

Besides above, larger repo documents also would take longer to publish. Figures for reference,

- `109mb` takes around `10 seconds` to complete publishing
- `2gb` takes around `3 ~ 4 minutes` to complete publishing

In the future, we are also thinking of displaying some metadata in the team docs page, which will include documentation size. However in the meantime, here are some ways in which you could check the size of your repository : 

1. Use file explorer or finder in local to get the file size
2. Use command `du -sh {path to folder e.g /Users/yannyeinaung/doc-publisher-guide}` (you can run `pwd` to get path of current directory)
3. Call github api in browser `https://api.github.com/repos/{owner}/{repo}` e.g `https://api.github.com/repos/sg-developer-portal/doc-portal-publisher-guide` which will return a json object with `size` key which will display the size of repo in KB. Only works with public repos.
   
## Maximum Files in One Folder

In accordance to [S3's Request Limit](https://aws.amazon.com/premiumsupport/knowledge-center/s3-request-limit-avoid-throttling/), `under each directory(folder) maximum of 3500 files are allowed`. A `folder` refers to the prefixes before the last `/` and a `file` is anything that's not a folder, consider this example:

- root-lvl-dir/
  - sub-dir/
    - sub-item.md
  - item.md

`root-lvl-dir` has `item.md `as a file and can have 3499 more of such files but `sub-dir` is not considered a file of `root-lvl-dir` since it's a folder. Similarly, `sub-item.md` is considered to be a file under `root-lvl-dir/sub-dir` and can have 3499 more files.

## Discourage of Multi-Doc Repo Structure

A Multi-Doc Repo Structure refers to multiple sub-folders within the repository that holds separate markdown files within and each of these sub-folders are used to create its own document. For e.g:

- root-lvl-dir/
  - sub-dir/
    - sub-item.md
  - sub-dir-2/
    - sub-item-2.md

The folders `sub-dir`, `sub-dir-2` and `root-lvl-dir` can be used to create separate documents in doc portal.

The way our publishing flow and backend logic is set up, it does not support this type of structuring well. Here are a few reasons:

   1. It could increase publishing and updating time since these are relative to size of the repository and not the size of the sub folders
   2. Repository may exceed our current supported size limit of `2gb`
   3. Any update made under a sub-folder (e.g `sub-dir`) through github, re-triggers the publishing flow for all of the documents tied to `the entire repository(e.g. 'root-lvl-dir')`. This could lead to the setbacks in reason 1 and 2 as well.


**We are working on solutions to fix this but we are discouraging it in the meantime as it could dampen your Doc Portal experience.**