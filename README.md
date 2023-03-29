# java-husky-maven-spotless-example


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

## commitizen

    npm install -g commitizen


## Links

https://commitlint.js.org/#/guides-local-setup

http://commitizen.github.io/cz-cli/