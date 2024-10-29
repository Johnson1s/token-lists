# Local development

Below is a list of commands you will probably find useful.

## `yarn start`

Runs the project in development/watch mode. Your project will be rebuilt upon changes. 
TSDX has a special logger for you convenience. Error messages are pretty printed and formatted for compatibility VS Code's Problems tab.

<img src="https://user-images.githubusercontent.com/4060187/52168303-574d3a00-26f6-11e9-9f3b-71dbec9ebfcb.gif" width="600" />

Your library will be rebuilt if you make edits.

## `yarn build`

Bundles the package to the `dist` folder.
The package is optimized and bundled with Rollup into multiple formats (CommonJS, UMD, and ES Module).

<img src="https://user-images.githubusercontent.com/4060187/52168322-a98e5b00-26f6-11e9-8cf6-222d716b75ef.gif" width="600" />

## `yarn test`

Runs the test watcher (Jest) in an interactive mode.
By default, runs tests related to files changed since the last commit.

## Release Workflow

The `release.yml` workflow automates the release process of the project. It ensures a consistent and secure release process by automating the necessary steps.

### Steps involved in the workflow:

1. **Trigger**: The workflow is triggered manually via the `workflow_dispatch` event.
2. **Runner**: It runs on a specific runner group named `npm-deploy`.
3. **Load Secrets**: It loads secrets using the `1password/load-secrets-action` to access the `NPM_TOKEN`.
4. **Checkout Code**: It checks out the repository code using `actions/checkout`.
5. **Setup Node.js**: It sets up the Node.js environment using `actions/setup-node`.
6. **Install Dependencies**: It installs dependencies using `yarn install`.
7. **Release Command**: It runs the release command `yarn g:release` to publish the package.
