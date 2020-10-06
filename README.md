# tangro-actions-template

A GitHub Action template for tangro GitHub actions. It has the build step, the workflow and some dependencies pre-configured.

# Using this template

a) Either go to [the repository](https://github.com/tangro/tangro-actions-template) and click on [Use this template](https://github.com/tangro/tangro-actions-template/generate)

b) Or go to [create new tangro repo](https://github.com/organizations/tangro/repositories/new) or [create new user repo](https://github.com/new) and then select the `tangro/tangro-action-template` from the _Repository template_ list.

# Creating a Readme

When writing a `README.md` please do not change the `README.md` inside the root directory. Change `templates/README.md` instead. Use `<%= name %>` as a placeholder whenever you would write the action's name. It will be replaced with the `name` from the `package.json`. Use `<%= version %>` every time you want to reference the current version of the action.

This way the example in the README will always show the latest version of each action. You do not have to use a placeholder when you want to pin the version of an action to a specific version. Please do not forget to add a comment why you have to pin the version.

To run the script you need a environment variable called `GITHUB_TOKEN`. It has to store a [personal access token](https://github.com/settings/tokens/new) with repo access.

> Use `npm run update-readme` to update the project's readme.

These placeholders are available by default. You can add more by editing `scripts/update-readme.js`.

- `<%= name %>` - The name from the `package.json`. For example `actions-license-check`.
- `<%= version %>` - The version from the `package.json`. For example `1.0.1`.
- `<%= uses %>` - The whole action name including the owner and version. For example `tangro/actions-license-check@1.0.1`.
- `<%= actions.checkout =>` - The latest version of [actions/checkout](https://github.com/actions/checkout) including owner, name and version. For example `actions/checkout@v2.1.1`
- `<%= actions['setup-node'] %>` - The latest version of [actions/setup-node](https://github.com/actions/setup-node) including owner, name and version. For example `actions/setup-node@v2.1.3`
- `<%= tangro['actions-deploy'] %>` - The latest version of [tangro/actions-deploy](https://github.com/tangro/actions-deploy) including owner, name and version. For example `tangro/actions-deploy@v1.0.3`

We use [ejs](https://ejs.co/). Feel free to use more templating features from ejs.

# Development

Create a new repository and copy the contents of this template repository to the new repository. Do not forget the `.github` folder. It may be hidden on your machine.

# Publishing an action

> You do not have to run `npm build`. It will be done automatically.

There is a workflow already pre-configured that automatically publishes a new version when you push your code to the `master` branch. The workflow will automatically

1. remove the `dist` folder
2. Build a new version
3. Bump the version number
4. Update the README with all the updated version numbers
5. Create a tag with the new version number

The workflow will also create or use a branch called `latest` and overwrite the contents of the version.

After the workflow/action has run your action will be available to be used.

# Scripts

### `npm run update-readme`

Only use inside the action you are developing. Uses the README script to update the README with all the latest versions.

### `npm run update-dependencies`

Use here or inside the action you are developing to update the dependencies.

# FAQ

## Do I need to check-in the node_modules folder

No. This template uses [@zeit/ncc](https://github.com/zeit/ncc) to automatically create and bundle a single `index.js` with the `node_modules` and code included.

## Can I put the `dist/` folder into the `.gitignore`

No. It needs to be present for the action. It is planned to automatically alter the `.gitignore` to always check-in the `dist/` folder. But that's not ready yet.

## What happens if I ran `npm build`

The workflow deletes the `dist` folder before every build. You can just leave it.

## Can I use a different branch than `master`

Yes. Edit the `.github/workflows/release-action.yml`
