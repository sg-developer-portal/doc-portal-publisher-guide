# Overview
<!-- todo: update this diagram -->
![Get Started Overview](assets/get-started-overview.png)

## Prerequisites

The developer portal documentation service syncs up your documentation repository containing Markdown or OpenAPI(Swagger) files and hosts them as documentation pages.

You will need:

1. A [TechPass](https://www.techpass.gov.sg) account to log in and host your documentation.
2. A free [github.com](https://github.com) account to host your documentation's git repository.
3. *To be onboarded as a publisher on the Documentation Service.

?> *To onboard as a publisher, please reach out to the Developer Portal Team [via email](mailto:gds_developer_portal@tech.gov.sg).

You can publish 2 types of documentation:

1. Markdown. This requires you to commit a directory of documentation markdown files to a GitHub repository with a `_sidebar.md` file to format the side navigation for documentation readers.

2. OpenAPI/Swagger. This requires you to commit a swagger file to a GitHub repository.

You can then publish your documentation on the Documentation Service via our publisher app (see detailed steps below).

## Overview of steps
<div style="text-align:center">
   <img src="assets/new-publishing/publishing-guide.gif"/>
</div>

1. Write and preview your documentation on your machine with tools such as [Docsify](/get-started?id=create-and-preview-markdown) for Markdown, and [ReDoc](/get-started?id=preview-oas) for OpenAPI
2. Create a GitHub repository and push your documentation to it
3. Log in to the documentation service with your TechPass account
4. Go through the guided publishing flow via the [publisher app](https://docs.developer.gov.sg/teamdocs/products).

## Quickstart

The two types of documentation that you can publish are:
1. Markdown 
2. Open API Specification / Swagger

The following examples show you how to get started with the creation of such docs, and also how to serve them on your local machines so that you can have a preview of how they would look like when published.

### 1a. Markdown
#### Create and Preview Markdown

The easiest way to get started with **Docsify** is through its [command line tool](https://docsify.js.org/#/quickstart).

1. You will need to have Node.js and NPM installed on your machine. Use the [official installer](https://nodejs.org/en/) or the [nvm tool](https://github.com/nvm-sh/nvm).

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
   # Creates an index.html and README.md within your working directory
   docsify init .
   ```

4. Start up a live-reloading server for your documentation. Open a browser and view it at http://localhost:3000.

   ```bash
   # View your documentation at http://localhost:3000
   docsify serve .
   ```

5. Commit your markdown files

   ```bash
   git add --all
   git commit -m "Initial commit"
   ```

### 1b. OpenAPI Spec


From the [official OpenAPI specification site](https://swagger.io/specification):

> The OpenAPI Specification (OAS) defines a standard, language-agnostic interface to RESTful APIs which allows both humans and computers to discover and understand the capabilities of the service without access to source code, documentation, or through network traffic inspection.
>
> An OpenAPI document (or set of documents) defines or describes an API. An OpenAPI definition uses and conforms to the OpenAPI Specification.

You can defined an OpenAPI or Swagger document in `yaml` or `json` and publish that on the developer documentation portal. It would be rendered as a human-readable page using the [ReDoc](https://github.com/Redocly/redoc) engine.


**<small>Note: This file must be named `swagger.json`, `swagger.yml` or `swagger.yaml`!</small>**

#### Preview OpenAPI
You can use the [redoc CLI](https://github.com/Redocly/redoc/tree/master/cli) to preview how your API documentation would look like. You will need to have Node.js and NPM installed on your machine. Use the [official installer](https://nodejs.org/en/) or the [nvm tool](https://github.com/nvm-sh/nvm).

```bash
npm i -g redoc-cli
redoc-cli serve swagger.yml
```

You can then navigate to http://localhost:8080 to preview your rendered API documentation:

![openapi documentation with redoc screenshot](assets/redoc-preview.png)

### 2. Push to GitHub
After your Markdown or OpenAPI documentation is prepared, push it to GitHub.

[Create a new github.com repository](https://github.com/new) (this can be either public or private) and follow
the instructions on GitHub to push your new repository to that project.

```bash
# Either SSH authentication
git remote add origin git@github.com/my-username/my-project.git
# Or HTTP
git remote add origin https://github.com/my-username/my-project.git

# Push to the master branch of your GitHub project
git push -u origin master
```
>For **Markdown Docs**, you should have at least a `README.md` file at the **root** of your project, which will serve as the home page for your documentation.

>For **OpenAPI/Swagger Docs**, you should have at least a `swagger.json`, `swagger.yml` or `swagger.yaml` file at the **root** of your project, which will serve as the home page for your documentation.

### 3. Log in and access your Product space

<div style="text-align:center">
   <img src="assets/new-publishing/access-product.gif"/>
</div>

Log in to the developer documentation portal by clicking on `Log in with TechPass` on the navigation bar. 

Navigate to `Team Docs` to find the products what you can publish documentation for.

Select the Product of which you are intending to publish documentation for, then click on the "Publish documentation" button. 

### 4. Publish your documentation with the guided Publishing Wizard

The publishing wizard will guide you through the steps required to get your documentation published.
#### Step 1. Select a Git Provider

![Select Repo](assets/new-publishing/select-git.png)

In this step, you select a git provider (only GitHub available for now, but more options are coming soon!) and authorise your account to the documentation service with the necessary permissions to perform publishing.

If this is your first time publishing a document, and you have not authorised your GitHub account to us before, you will be prompted to do so when you click next.

#### Step 2. Select a Repository

<div style="text-align:center">
   <img src="assets/new-publishing/select-repo.png"/>
</div>

In this step, you select a repository from your GitHub account to link up to your to-be published documentation. Your personal repositories along with the repositories of any organisation/teams of which your GitHub account is an admin of, will be available for selection. You can toggle these options under the 'Account' dropdown selection.

#### Step 3. Enter Document Details

<div style="text-align:center">
   <img src="assets/new-publishing/document-settings.png"/>
</div>

In this step, you provide details regarding how you want your documentation to be displayed both for readers and search engines. 
The common options are:

1. Display Name: The title that people see when clicking on links to your documentation, e.g. "MyTechProduct User Guide"
2. Description: A short description of your product, e.g. "Find out how to integrate your backend with MyTechProduct here".
3. Visibility: Public (public internet) vs private (only viewable by logged in TechPass users, with further email/domain-based restrictions available).
4. Documentation type: choose the format of your documentation, either as pages written in Markdown or OpenAPI/Swagger specifications.
5. Branch: Choose the branch of your GitHub repo to publish your documentation from.

For more detailed descriptions of each option, see [publishing settings](advanced/publishing-settings).

#### Step 4. Summary
<div style="text-align:center">
   <img src="assets/new-publishing/summary.png"/>
</div>

This is the final step where you review your repository selection and inputs. Upon verifying that all configurations are in order, click on 'Publish Documentation' to have your documentation published!

Once published, your documentation will be hosted at docs.developer.gov.sg. All changes made to your GitHub repository would be automatically
synced to the documentation portal.
