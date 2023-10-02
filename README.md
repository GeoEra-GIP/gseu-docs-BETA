# EGDI Documentation

This project include documentation on deciding how to deliver data, how to set up your data sets, how to set up GeoPackages that can easily be uploaded and on the use of the EGDI platforms administration module.

Contributors to this documentation should write their part in Markdown as understood by docsify (<https://www.markdownguide.org/tools/docsify/>). To keep the markdown in a standardised way the use of a tool like markdownlint should be used.

This documentations are in UK english.

[Find the source on GitLab](https://geusgitlab.geus.dk/egdi-public/egdi-documentation)

[Read the documentation here](http://egdi-public.gitlabpages.geus.dk/egdi-documentation/)

Project is based on [docsify](https://docsify.js.org/) documentation site generator.

Currently the documentation contains the following published pages / chapters:

* doc/README.md
* main-content/main-content/DeliveringDataToEgdi.md General introduction an delivering data to EGDI
* main-content/main-content/SpatialData.md descriptions of how to set up your data sets
* main-content/main-content/GeoPackages.md examples on how to create different types of GeoPackages
* main-content/main-content/AdministrationModule.md user guide to the Administration module
* main-content/main-content/ListOfTerms.md List of terms used in the documentation

The project also contains a few unpublished pages:

* main-content/main-content/DocumentRepository.md initial document on the EGDI Document Repository
* main-content/main-content/Workflow.md contains the source code for the mermaid diagrams
* main-content/main-content/Test.md used to test syntax highlighting

## Updating pages

Require a GitLab user account.

* Edit markdown files directly in [GitLab](https://geusgitlab.geus.dk/-/ide/project/egdi-public/egdi-documentation/) or use an offline editor and use git to commit your changes to GitLab
* Make your changes and commit (or submit a merge request for somebody else to review)
* Once the changes merge into master, the project will be deployed on [GitLab pages](http://egdi-public.gitlabpages.geus.dk/egdi-documentation/).

## Creating new pages

* Create a new markdown file in docs folder (e.g. `readonly-methods.md`)
* Add a line in the `_sidebar.md` to create a link to that file in the sidebar (e.g `-  [Readonly Methods](readonly-methods.md)`)
* Once the changes merge into master it will be deployed on [GitLab pages](http://egdi-public.gitlabpages.geus.dk/egdi-documentation/)

## Running documentation locally

You can also run the project locally, make the changes and then submit your changes to GitLab.

* Install docsify: `npm i docsify-cli -g`
* Pull the project to your computer
* cd into api-guidance-docs
* Run the project - `docsify serve ./docs --open`
* Website will run on `http://localhost:3000/`
