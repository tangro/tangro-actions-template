# <%= name %>

<< Add a short description about the action here >>

# Versions

Either use a specific version of this action, or `latest` which should always point to the latest version of `<%= name %>`. The latest published version of this action is `<%= version %>`.

# Parameters:

<< Describe the parameters here >>

| Name   | Type              | Default | Description       |
| ------ | ----------------- | ------- | ----------------- |
| sample | boolean(optional) | false   | << description >> |

# Example job

<< Add an example job here. use the placeholder `<%= version %>` to reference the current version of the action >>

```yml

```

> **Attention** Do not forget to pass the `GITHUB_TOKEN` and `GITHUB_CONTEXT` to the `<%= name %>` action

Steps the example job will perform:

<< Add the steps the action will perform, please remove / add steps >>

1. Check out the latest code
2. Use node v12
3. Run `npm install`
4. (this action) << add a description >>

# Usage

<< add some more examples >>

# Development

Follow the guide of the [tangro-actions-template](https://github.com/tangro/tangro-actions-template)

# Scripts

- `npm run update-readme` - Run this script to update the README with the latest versions.

  > You do not have to run this script, since it is run automatically by the release action

- `npm run update-dependencies` - Run this script to update all the dependencies
