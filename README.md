# java-husky-commitizen-maven-spotless-example
java-husky-commitizen-maven-spotless-example

## Husky

### Install
    
    npm install husky --save-dev

### Configure

Add a hook

    npx husky add .husky/commit-msg 'npx --no -- commitlint --edit "$1"'

    npx husky add .husky/pre-commit "mvn test"

## commitlint

### Install commitlint

    npm install --save-dev @commitlint/{cli,config-conventional,prompt-cli}

### Configure

    echo "module.exports = {extends: ['@commitlint/config-conventional']};" > commitlint.config.js 

### Add hook
    
    npx husky add .husky/commit-msg  'npx --no -- commitlint --edit ${1}'

### Test

    git commit -m "new: initial commit"

    ⧗   input: new: initial commit
    ✖   type must be one of [build, chore, ci, docs, feat, fix, perf, refactor, revert, style, test] [type-enum]

    ✖   found 1 problems, 0 warnings
    ⓘ   Get help: https://github.com/conventional-changelog/commitlint/#what-is-commitlint

    husky - commit-msg hook exited with code 1 (error)

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
