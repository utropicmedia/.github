# Devlopment Requirements and Standards

Coding standards are important - not only for correctness in our work-products, but also to ensure that other technologists can understand what is being done programmatically, and why.

 

***\* NOTE: if we are updating/extending an existing project, the current standard, guidelines and style of that project should be used first and foremost. \****

## Documentation.

Each repo should have at a minimum the following:

1. README.md - Provides an overview of the project and basic usage this file should be brief and simple to read.
2. CHANGELOG.md - log of releases and associated changes
3. INSTALL.md - Information on the instalation and requirements of project 
4. docs/Home.md - this markdown page contains more details that related to items in README.md.  Topics like all possible usage flags, data flow diagrams, testing approaches and other considerations.
5. docs/arch.drawio.svg - Dataflow diagram for the project.
6. Diagrams (Data Flow, Architecture, etc.) should be created and maintained with [draw.io](http://draw.io) (https://app.diagrams.net/)
   
   

## Code Style.

Ecosystem/language-specific best-practices should always be followed.  

When modifying an existing project, current project conventions should also be followed.(Variable/function naming styles, whitespace, etc.)

At a minimum:

- class/file header blocks
- function header
- in-line comments where developers should pay specific attention
- Use language-specific linter on your local prior to committing code.
- **Errors/Exception Handling -** All errors/exceptions must be caught and handled:
  - For Release builds, Stacktraces and debugging information should not be displayed to the User 
  - If an Exceptions is caused by User input, an appropriate descriptive message should be shown to the User
  - If an Exception is caused by System/Platform errors an informative message should be returned to the User
- **Logging** -Use appropriate logging levels for various log messages.(i.e DEBUG, INFO, ERROR, VERBOSE, etc.)  Production releases should not include any DEBUG level logging messages.
- **Versioning** - follow Semantic Versioning(https://semver.org/) for releases 

## QA / Testing.

Pair-programming will be used whereby the team member doing the coding will be paired with another development resource to review code approaches and collaborate with on a daily basis.  

Weekly meetings are as follows:

- Code Walk-throughs once per week (Monday/Tuesday)
- Active projects will have Demo Days each Friday
- Additional meetings can be had on-demand 

All projects will be integrated into the CI / CD pipeline, currently serviced by [Google Cloud Build](https://console.cloud.google.com/cloud-build/dashboard?folder=true&organizationId=true&project=storj-utropic-services) although github actions can also be used.  A project will not be tagged for release without a successful pipeline build.  Each project is expected to have one core unit test that will be scripted into the pipeline.

**Code commits will be require the following to be merged:**

- Pull Request with changes
- Approval from a Senior Developer(admin); or
- Two individual reviewers
- Successful Static Analysis Scans
- Successful build pipeline processing
