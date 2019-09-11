# tangro-actions-template

A GitHub Action template for tangro GitHub actions. It has the build step, the workflow and some dependencies pre-configured.

# Using this template

a) Either go to [the repository](https://github.com/tangro/tangro-actions-template) and click on [Use this template](https://github.com/tangro/tangro-actions-template/generate)
b) Or go to [create new tangro repo](https://github.com/organizations/tangro/repositories/new) or [create new user repo](https://github.com/new) and then select the `tangro/tangro-action-template` from the _Repository templaet_ list.

# Development

Create a new repository and copy the contents of this template repository to the new repository. Do not forget the `.github` folder it may be hidden on your machine.

# Publishing an action

> **Important** Do **not** run `npm build`. It will be done automatically. And do not check in the `dist` directory.

There is a workflow already pre-configured that automatically publishs a new version when you push your code to the `master` branch. The workflow will take your npm package version and publish the action under that version. You have two options

- Keep the current version number and the action will be updated
- Bump the version number and a new action will be created

The action-release workflow will create a branch with the `package.json` version as its name. An already existing branch will be overwritten.

After the workflow/action has run your action will be available to be used.

# FAQ

## Do I need to check-in the node_modules folder

No. This template uses [@zeit/ncc](https://github.com/zeit/ncc) to automatically create and bundle a single `index.js` with the `node_modules` and code included.

## Can I put the `dist/` folder into the `.gitignore`

No. It needs to be present for the action. It is planned to automatically alter the `.gitignore` to always check-in the `dist/` folder. But that's not ready yet.

## What happens if I ran `npm build`

Just delete the `dist/` folder.

## Can I use a different branch than `master`

Yes. Edit the `.github/workflows/release-action.yml`
