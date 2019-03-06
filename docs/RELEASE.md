## Developer Guide: Releases

### Background

`electron-builder` is used to package up the application by CircleCI. The configuration settings can be found in `package.json`, under the `"build"` key.

If you include a new top-level file to be distributed with the application, it must be added manually to the `"files"` array in the configuration settings.

### Testing a release candidate locally

`yarn build` will package up the app, with installers for each OS, and output them into a `release` directory.

### Preparing a release (via CI)

1. **Update the version number** of the release in `package.json`.
1. **Merge the new code into `master`.** CircleCI will build the new installers (`yarn build`) and create a draft release for the new version. **Note:** if the CI builds for a version number that already exists, it will replace the assets for that version.
1. **Write release notes.** The draft can be edited from the GitHub releases page. _TODO:_ Changelog.
1. **Publish the release.** Before the new installers can be viewed on the website, you must manually publish the draft. Within GitHub's UI, edit the draft and select `Publish release`.

### Preparing a release (manually)

1. **Add the GitHub access token** to the `.env` file as `GH_TOKEN`.
1. **Update the version number** of the release in `package.json`.
1. **Manually initiate the release** with `yarn release`.
1. **Write release notes.** The draft can be edited from the GitHub releases page. _TODO:_ Changelog.
1. **Publish the release.** Before the new installers can be viewed on the website, you must manually publish the draft. Within GitHub's UI, edit the draft and select `Publish release`.

_TODO:_ Use build channels

_TODO:_ Package signing
