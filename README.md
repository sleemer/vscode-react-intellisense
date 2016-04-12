# Five steps to intellisense within your vscode-es2016-react project
**Short** version of guideline for setting up VS Code intellisense to work with react.js projects.

### Used resources:
1. [VS Code release notes](https://code.visualstudio.com/Updates)
2. [ESLint](http://eslint.org/)
2. [Babel](https://babeljs.io/)

### Versions of os, tools and libraries 
1. OS X El Capitan
2. VS Code - Insiders v0.10.15
3. ESLint VS Code extension v0.10.13
4. react v15.0.1
5. babel-core v6.7.6
6. eslint v2.7.0
7. babel-eslint v6.0.2

### What you get:
1. Intellisense for es2015
2. Intellisense for react
3. Intellisense within your project modules 

### Create react.js project:
1. Create package.json 
    - npm init –y 
2. Install react 
    - npm install react --save 
    - npm install react-dom --save

## Setup VS Code intellisense for react.js project: 

1. Install VS Code, if it has not been done yet - [eslint extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint).
2. Create jsconfig.json file
    ```
    "compilerOptions": { 
        "target": "ES6", 
        "module": "commonjs", 
        "allowSyntheticDefaultImports": true 
    }
    ```    
3. Set up eslint: 
    - npm install eslint –-save-dev 
    - create .eslintrc file
    ``` 
    "parser": "babel-eslint", 
    "env": { 
            "browser": true, 
            "commonjs": true, 
            "node": true, 
            "es6": true 
    }, 
    "parserOptions": { 
            "ecmaVersion": 6, 
            "sourceType": "module", 
            "ecmaFeatures": { 
                "jsx": true, 
                "classes": true, 
                "defaultParams": true 
            } 
    } 
    ```
    - edit VS Code Workspace Settings (.vscode/settings.json): 
    ```
    "javascript.validate.enable": false,
    "eslint.enable": true
    ```
4. Set up babel: 
    - npm install babel-core --save-dev 
    - npm install babel-preset-es2015 --save-dev 
    - npm install babel-preset-react --save-dev 
    - npm install babel-preset-stage-0 --save-dev 
    - npm install babel-eslint --save-dev
    - create .babelrc file:
    ```  
    "presets": [ 
        "es2015", 
        "stage-0", 
        "react" 
    ] 
    ```
5. Install the typings for react by running 
    - typings install --ambient react