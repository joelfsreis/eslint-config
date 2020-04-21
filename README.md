# eslint-config

This configuration uses airbnb and prettier configuration plus some extra rules that we find handy for *React* applications

For more documentation you can check `ESLint` and `Prettier` documentations as well the `airbnb` and `prettier` configurations for more information

## Install
You need to have eslint and prettier already installed as dev dependencies on your project. If you are using `create-react-app` you can skip this next step as you don't need to install them, react-scripts already takes care of that for you
```
npm install --save-dev eslint prettier
```
This command will install our config using the code standards from airbnb config and code style from prettier config.
```
(
  export PKG=@joelfsreis/eslint-config;
  npm info "$PKG@latest" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs npm install --save-dev "$PKG@latest"
)
```

To configure ESLinter and Prettier you can add to your `package.json`
```
"eslintConfig": {
  "extends": "@joelfsreis",
},
"prettier": "@joelfsreis/prettier-config"
```

Or create a `.eslintrc` and `.prettierrc` files and add `extends: "@joelfsreis"` and `"@joelfsreis/prettier-config"` respectivally. As an example:
```
<!-- .eslintrc -->
{
  "extends": "@joelfsreis"
  <!-- you can edit this configuration as usual, check ESLint docs -->
}

<!-- .prettierrc -->
"@joelfsreis/prettier-config"
```

- `package.json` scripts
```
"lint": "eslint ./",
"lint:fix": "eslint ./ --fix",
"format": "prettier --write \"{,!(node_modules)/**/}*.js\""
```

TODO:
- add links for documentation
- create eslint plugin with rules
- create multiple configurations, each one for specific env