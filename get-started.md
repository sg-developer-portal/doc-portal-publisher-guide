# Overview

![Get Started Overview](assets/get-started-overview.png)

## Prerequisites
The documentation portal syncs up your documentation repository containing Markdown or OpenAPI(Swagger) files and hosts them as documentation pages.

You will need
1. A [TechPass](https://www.techpass.gov.sg) account to log in and host your documentation.
2. A free [github.com](https://github.com) account to host your documentation's git repository.

If your documentation is in Markdown, you will need [Docsify](https://docsify.js.org) to write and structure it on your development machine before pushing it to your GitHub repository.

If your documentation is in OpenAPI/Swagger, i.e. you are writing API documentation, you will need [ReDoc](https://github.com/Redocly/redoc) to view it on your development machine before pushing your `swagger.json` file to your GitHub repository.

## Starting with a new repo on GitHub

### 1. Create your Docsify project

The easiest way to get started with Docsify is through its [command line tool](https://docsify.js.org/#/quickstart).

1. You will need to have Node.js and NPM installed on your machine. Use the [official installer](https://nodejs.org/en/) or
   the [nvm tool](https://github.com/nvm-sh/nvm).

2. Create a Git repository to hold your documentation.

   ```bash
   mkdir my-docs
   cd my-docs
   git init
   ```

3. Use the [Docsify CLI](https://docsify.js.org/#/quickstart) to generate a documentation site. This creates the README.md and index.html files within your working directory.

   ```bash
   # Install Docsify CLI
   npm install -g docsify-cli
   # Create an index.html and README.md within your working directory
   docsify init .
   ```

4. Start up a live-reloading server for your documentation. Open a browser and view it at http://localhost:3000.

   ```bash
   # View your documentation at http://localhost:3000
   docsify serve .
   ```

4. Commit your markdown files

   ```bash
   git add --all
   git commit -m "Initial commit"
   ```

5. [Create a new github.com project](https://github.com/new) (this can be either public or private) and follow
   the instructions on GitHub to push your new repository to that project.

   ```bash
   # Either SSH authentication
   git remote add origin git@github.com/my-username/my-project.git
   # Or HTTP
   git remote add origin https://github.com/my-username/my-project.git

   # Push to the master branch of your GitHub project
   git push -u origin master
   ```

   Note that you should have at least a `README.md` file at the **root** of your project, which will serve as the home page for your documentation.

### 2. Log in and link your TechPass account to your GitHub account

Log in to documentation portal by clicking on `Log in with TechPass`. Navigate to `Browse Docs` > `My Docs` and click on the "authorize to GitHub" link. You will be directed to your GitHub account and you will have to grant OAuth permissions for the documentation portal to pull your documentation repository and host it.

### 3. Publish your documentation on Documentation Portal

> Make sure you have **pushed** changes made to your documentation files to the master branch on GitHub!

Once your GitHub repository is linked to the documentation portal, you will be able to publish it from the documentation portal.

From the top navigation bar, go to `Browse Docs` > `My Docs`. You should see the your personal or organisational GitHub accounts that Documentation Portal is connected with. Find the GitHub repository containing your documentation and click "Publish".

![My Docs page screenshot](assets/my_docs_list_screen.png)

In the publish menu:

1. Set "Documentation visibility" to "Public".
2. Set "Documentation Technology" to "Markdown".
3. Fill in the display name for your documentation page.
4. Click "Publish this project".

![My Docs publish screenshot](assets/my_docs_publish_screen.png)

Once published, your documentation will be hosted at docs.developer.gov.sg. All changes made to your GitHub repository would be automatically
synced to the documentation portal.

> When published, every push to your documentation files on the `master` branch will be automatically pulled and served by the documentation portal.

> If you publish a project in `public` mode, it will be publicly accessible from the internet.
> If you choose `private` mode, only users logged in to Documentation Portal through TechPass will be able to see it. You can also set specific access controls via email domains or specific emails.
> You can also specify the category that your documentation belongs to.
> For a complete description of publishing settings, see [advanced settings](advanced/publish-settings).

?> For more information, see [how documentation portal works](advanced/how-documentation-portal-works).
