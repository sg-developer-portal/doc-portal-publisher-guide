## GitHub OAuth permissions

When linking up your GitHub account or organisation, Documentation Portal requests for permission to access your GitHub repositories through GitHub APIs. The scope needed is `repo` as defined in the [GitHub OAuth scope list](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/#available-scopes).

### Permissions for organisation repositories

Documentation Portal will assume [the same level of permissions](https://help.github.com/en/github/setting-up-and-managing-organizations-and-teams/repository-permission-levels-for-an-organization) as you do in a GitHub organization repository. This means that on your [account](/account) page, you will only be able to view repositories for which you have been explicitly given `read+` permissions, and you can only publish/unpublish documentation for a repository if you have `admin` level permissions.