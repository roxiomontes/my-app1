# Contributing Guidelines

So you're interested in giving us a hand? That's awesome! We've put together some guidelines that should help you get started quickly and easily. If you need help with anything, please email the Tech Culture team at TechCulture@intuit.com. Thank you for stopping by!

## Before You Write Any Code

Please share with us your idea and intent for changes at TechCulture@intuit.com or to our Slack channel [#svc-opensource](https://intuit-teams.slack.com/archives/C98K2PDB5).

## Code Contribution Process

After the change has been discussed, follow the process below to make the change and submit a pull-request.

1) Fork our Intuit Open Source [repo](https://github.intuit.com/dev-devx/intuit-open-source) and set it up locally
2) Refer our README's [Getting Started](https://github.intuit.com/dev-devx/intuit-open-source#getting-started) section to set up your local development environment
3) Checkout a branch from master with branch name in the format: 

    `feature/<BRIEF_DESCRIPTION>`
    `fix/<BRIEF_DESCRIPTION>`

    (e.g. `feature/error-handling`)
4) Make modifications to code
5) Write and validate unit tests and functional tests
6) Commit code and push branch.
7) Create a new pull request
    1) Find `Reviewers` section on top right and select gear to add reviewers (REQUIRED)
    2) Fill out the pull request template (REQUIRED)

## Code quality expectations:

### Code coverage:
1) **Unit test**: coverage percent is at **80%** 
2) **Functional tests**: P1 and P0 test cases are automated

### Documentation:
If your code changes require modifications to build commands, (e.g. start/build application or run tests)
update the [README](https://github.intuit.com/dev-devx/intuit-open-source/blob/master/README.md)
 
### PR checks
Make sure all the PR automated checks pass

 ## Contact Information:
- When PR is created, **if all code quality expectations** are met, a team member will review your code within **2 days**.
For any questions please email the EA engineering team at TechCulture@intuit.com or Slack us at [#svc-opensource](https://intuit-teams.slack.com/archives/C98K2PDB5)

# Onboarding your Project to the Open Source Site
If you have recently Open Sourced your project or do not see it listed in the [Open Source site](https://opensource.intuit.com/), you can follow these steps to add your project and showcase it amongst the rest. Throughout the process, make sure to follow our contribution guidelines.

## Contact Us

1. Email us at TechCulture@intuit.com or Slack us at [#svc-opensource](https://intuit-teams.slack.com/archives/C98K2PDB5) with your project name, assets and mention you want to onboard your project onto the website. Our design team will work with you on adapating an image asset for the site.

## Fork our Repository

1. Fork our Intuit Open Source [repo](https://github.intuit.com/dev-devx/intuit-open-source) and set up locally
1. Create a new branch `git checkout -b feature/new-project-<project-name>`
1. Read our README's [Getting Started](https://github.intuit.com/dev-devx/intuit-open-source#getting-started) section to set-up your local development environment

## Add the Provided Project Image Asset

1. Place the png image provided by our design team in `src/assets/projects`

## Add your Project Description in `content.json`
Please ensure your project description is between 50 and 100 characters.

1. Open `src/nls/content.json` and find the project descriptions section, which looks like: 
   
   `"projects.<project-name>.desc": "project-description",`
2. Insert your project description in the following format:
   
   `"projects.<project-name>.desc": "your-project-description",`

## Configure your project in `project-data.jsx`

1. Open `src/js/data/project-data.jsx` and import your image as
   `import ProjectName from '../../assets/projects/<project-name>.png';`
1. Select one of the following project categories for your project:
      - frontend
      - backend
      - mobile
      - infrastructure
      - testing
      - data
      - developer-tools
1. Add the following element inside the projectData array and use the project category you selected above
   ```
    {
        title: 'ProjectName',
        description: <FormattedMessage id="projects.<project-name>.desc" />,
        icon: ProjectName,
        tabs: ['your-project-category-from-list-above'],
        url: 'https://github.com/<your-project-repo-url>',
    },
   ```

## Test your Changes
Make sure you have installed the proper packages by following our README's [Getting Started](https://github.intuit.com/dev-devx/intuit-open-source#getting-started) section and follow the instractions on running the plugin locally

1. Run the plugin locally (see our [README](https://github.intuit.com/dev-devx/intuit-open-source/blob/master/README.md))
1. Navigate to the projects section and visually ensure that your project is correctly displayed to your selected category
      - Category
      - Logo
      - Title
      - Description
1. Run `yarn test` to ensure your changes didn't alter the funcionality of the plugin

## Commit and push your changes
Make sure you are working from your `feature/new-project-<project-name>` branch

1. Stage your changes
1. Commit with the following text format: `feat(projects): added your-project-name to projects`
1. Push your changes to your `feature/new-project-<project-name>` branch
