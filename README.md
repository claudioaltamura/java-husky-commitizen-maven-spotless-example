![GitHub Workflow Status (with branch)](https://img.shields.io/github/actions/workflow/status/claudioaltamura/java-husky-commitizen-maven-spotless-example/maven-build.yaml?branch=main)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

# java-husky-commitizen-maven-spotless-example
java-husky-commitizen-maven-spotless-example

## Husky

### Install

    npm install husky --save-dev

### Configure

Add a hook

    npx husky add .husky/pre-commit "mvn spotless:check"

## commitlint

### Install commitlint

    npm install --save-dev @commitlint/{cli,config-conventional,prompt-cli}

### Configure

    echo "module.exports = {extends: ['@commitlint/config-conventional']};" > commitlint.config.js

### Add another hook

    npx husky add .husky/commit-msg  'npx --no -- commitlint --edit ${1}'

### Test hook commit-msg

    see https://typicode.github.io/husky/guide.html#test-hooks

    git commit -m "new: initial commit"

    ⧗   input: new: initial commit
    ✖   type must be one of [build, chore, ci, docs, feat, fix, perf, refactor, revert, style, test] [type-enum]

    ✖   found 1 problems, 0 warnings
    ⓘ   Get help: https://github.com/conventional-changelog/commitlint/#what-is-commitlint

    husky - commit-msg hook exited with code 1 (error)

see https://github.com/conventional-changelog/commitlint/#what-is-commitlint

### Bypass a commit

    git commit -m "yolo!" --no-verify


## Commitizen

### Install

    npm install -g commitizen

### Configure

    commitizen init cz-conventional-changelog --save-dev --save-exact

### Use

    git cz


### Override

    git commit -m "override cz" --no-verify

## Links

https://typicode.github.io/husky/#/?id=install

https://commitlint.js.org/#/guides-local-setup

http://commitizen.github.io/cz-cli/
