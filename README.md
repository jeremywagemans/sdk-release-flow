# skd-release-flow

## Steps to setup a repo

1. Create minimal package.json
```
{
  "name": "evervault-<language>",
  "private": true,
  "version": "<version>",
  "devDependencies": {
    "@changesets/cli": "^2.26.2"
  }
}
```
2. Run `npx changeset init`
3. Delete `README.md` in `.changeset`
4. Update `config.json` with the following values:
```
{
  "$schema": "https://unpkg.com/@changesets/config@2.3.1/schema.json",
  "changelog": "@changesets/cli/changelog",
  "commit": false,
  "fixed": [],
  "linked": [],
  "access": "restricted",
  "baseBranch": "main",
  "updateInternalDependencies": "patch",
  "ignore": [],
  "privatePackages": {
    "version": true,
    "tag": true
  }
}
```
5. Update the github actions
6. Update workflow permissions (repo settings > actions > workflow permissions) to read and write permissions

## Release steps

1. Run `npx changeset` in your local terminal to submit changes made