# vscode-react-intellisens-short
**Short** version of guideline for setting up VS Code intellisense to work with react.js projects.

## Prerequisites:
> This need to be done only once and will work for all projects 

1. Install the VS Code [eslint extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint).
 
## Setup VS Code for react.js project: 
> This need to be done for each new project.

1. Create package.json 
    - npm init –y 
2. Install react 
    - npm install react --save 
    - npm install react-dom --save
3. Create jsconfig.json 
    ```
    "compilerOptions": { 
        "target": "ES6", 
        "module": "commonjs", 
        "allowSyntheticDefaultImports": true 
    }
    ```    
4. Edit VS Code settings (.vscode/settings.json): 
    ```
    "javascript.validate.enable": false
    ``` 
5. Set up eslint: 
    - npm install eslint –-save-dev to install eslint into your workspace. 
    - use eslint --init to create an initial eslint configuration by answering questions or by picking a popular configuration. 
    - edit .eslintrc file
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
6. Set up babel: 
    - npm install babel-core --save-dev 
    - npm install babel-loader --save-dev 
    - npm install babel-preset-es2015 --save-dev 
    - npm install babel-preset-react --save-dev 
    - npm install babel-preset-stage-0 --save-dev 
    - npm install babel-eslint --save-dev
    - create .babelrc config file with content:
    ```  
    { 
        "presets": [ 
            "es2015", 
            "stage-0", 
            "react" 
        ] 
    } 
    ```
7. Install the typings for react-global by running typings install --ambient react-global from the terminal.

## Links:
1. [VS Code release notes](https://code.visualstudio.com/Updates)
2. [Babel docs](https://babeljs.io/)
