# Search
Our search is powered by [AWS Kendra](https://aws.amazon.com/kendra/), it not only understands keywords but also natural language. Try "What is TechPass?" instead of just the keyword "TechPass", you will see different results, the one with clearer intention tend to generate more accurate results. For this case, it should show suggested answer for the question. For publishers, when you want the user to search with intent, it is good to write something that tackles some problems.

# Index
Documents that are referenced in the `_sidebar.md` file will be indexed, this is because we don't want the files to be exposed accidentally in search page. But take note for such case, user will still be able to access the document via direct url access.

# Limitations
* It only supports text, it does not search within resources like PDF files. 
* We are checking embedded documents links only, broken links for other cases are not supported now.

> Please let us know if any of these are needed, we will gather interests and prioritize accordingly, thank you.

# Private Documentation
* Search will be following the same permissions as the documentation settings.
* For non-login users, documentation description will be used instead of the contents of the documentation during search.

# Frequently asked questions
> If you have [FAQs](https://docs.aws.amazon.com/kendra/latest/dg/in-creating-faq.html) that want to be featured in the search results, do let us know!

# Synonyms 
We maintain a set of [synonyms](https://docs.aws.amazon.com/kendra/latest/dg/index-synonyms.html), do let us know if there are more:
```md
aws => amazon web services
DynamoDb, DDB
SHIPHATS, SHIP-HATS
SGTS, Singapore Government Tech Stack
CStack,Container Stack
CICD, CI/CD
Continuous Integration (CI), CI/CD
Continuous Delivery (CD),Continuous Deployment
Infrastructure as Code (IaC), Programmable Infrastructure
Orchestration, Automation
Deployment Pipeline, Release Pipeline, Delivery Pipeline
Monitoring and Observability,Application Performance Monitoring (APM)
Version Control, Source Control
Agile Development, Agile Software Development
training, learning
FOD, Fortify on demand
```