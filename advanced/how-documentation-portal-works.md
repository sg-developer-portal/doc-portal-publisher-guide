## GitHub OAuth permissions

When linking up your GitHub account, Documentation Portal requests for permission to access your GitHub account through GitHub APIs. The scopes needed are `repo` and `admin:repo_hook` as defined in the [GitHub OAuth scope list](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/#available-scopes). 

This means that Documentation Portal, on behalf of you, has:
- Full access to your private and public repositories. That includes read/write access to code, commit statuses, repository and organization projects, invitations, collaborators, adding team memberships, deployment statuses, and repository webhooks for public and private repositories and organizations. Also grants ability to manage user projects.
- Read, write, ping, and delete access to repository [hooks]() in public and private repositories. The repo and public_repo scopes grants full access to repositories, including repository hooks. Use the admin:repo_hook scope to limit access to only repository hooks.
