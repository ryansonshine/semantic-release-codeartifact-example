# Semantic Release CodeArtifact Example

A sample repository using the [semantic-release-codeartifact](https://github.com/ryansonshine/semantic-release-codeartifact)
plugin for [semantic-release](https://github.com/semantic-release/semantic-release)

## How this repo was made

1. `npm init`
2. `npm install -D semantic-release semantic-release-codeartifact`
3. Add [`.releaserc.json`](./.releaserc.json)
4. Create release workflow in [`.github/workflows/release.yml`](.github/workflows/release.yml)
5. Add `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`, and `AWS_REGION` to GitHub secrets
6. Made a commit following the [conventional-changelog standard](https://github.com/conventional-changelog/conventional-changelog)

To streamline the commit process [commitizen](https://github.com/commitizen/cz-cli) 
has been added to allow for an interactive menu for commit messages and
[husky](https://github.com/typicode/husky) for git hooks.

The following steps were taken for setting these up:

1. `npx commitizen init cz-conventional-changelog --save-dev --save-exact`
2. `npx husky-init && npm install`
3. `npx husky add .husky/prepare-commit-msg "exec < /dev/tty && git cz --hook || true"`
