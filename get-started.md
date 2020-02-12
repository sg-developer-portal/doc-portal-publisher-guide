# Get started

You will need a [TechPass](https://www.techpass.gov.sg) account to host your documentation, as well as a free [github.com](https://github.com) to host your documentation's git repository. You will also need to use [Docsify](https://docsify.js.org) to structure and view your documentation locally before you push it up your repository. 

## Hosting your documentation

### 1. Sign in with TechPass

After acquiring your TechPass account, click on the Log In button on the [home page](/).

### 2. Link your account to your github.com account

Once signed in, go to the account tab and click on the "authorize to GitHub" link. You will be directed to your GitHub account and you will have to grant OAuth permissions for the documentation portal to pull your documentation repository and host it.

### 3. Create your Docsify project

The easiest way to get started with Docsify is through its [command line tool](https://docsify.js.org/#/quickstart). You will need to have Node.js and NPM installed on your machine.

  1. Use the Docsify CLI to scaffold your project. This creates a README.md and index.html file within your working directory.

  ```bash
  # Within your project directory
  npm install -g docsify-cli
  docsify init . # creates index.html and README.md within your working directory
  ```

  Alternatively, use npx to directly run docsify-cli:

  ```bash
  npx docsify-cli init .
  npx docsify-cli serve .
  ```

  [Learn how Docsify works](https://docsify.js.org).
  
  2. Commit your markdown files (it is not necessary to commit your index.html file - it will not affect your documentation on the documentation portal).

  3. Create a new github.com project and push your new repository to that project.

### 4. Activate your GitHub project on Documentation Portal

Once your GitHub project is linked to the documentation portal, you will be able to activate it from the documentation portal. 

Activation means that every push to your documentation on the `master` branch will be automatically pulled and served by the documentation portal. Changes will be almost instantaneous.

If you activate a project in `public` mode, it will be accessible from the internet. If you choose `restricted` mode, only users logged in to Documentation Portal will be able to see it.