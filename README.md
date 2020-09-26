
# Create-react-app

When creating a React enviroment there are many things to consider: 
 - Version-collision
 - Different environments: development-environment, production-environment, test-environment. 
create-react-app sets all this up for you. 

create-react-app comes with react, react-dom and react-scripts. 
React-scripts comes with webpack, babel etc. 

With create-react-app you do not need to worry about how to compile jsx, this is all abstracted internally in the package.

But you can eject the application. With the PERMANENT command:
```npm run eject```
It wil copy all the files and tools to your project and you can modify them as you wish 


# Setting up the environment from scratch - Installation

To create a javascript environment from scrats for React, you need to install a few dependencies and wire them to work together.
These tools are constantly changing. This is not up to date. 

See jscomplete.com/reactful

Let's start:

## 1. npm init --> package.json

```npm init -y```

Inits with the default. Creates a `package.json`

## 2. server (eg express)

```npm i express```

Npm also creates the folder `node_modules`, and the `package-lock.json`-file. Since they were not present. 

Express depends on alot of dependecies, and all of them are installed to the node_modules folder: 
```added 50 packages from 37 contributors and audited 50 packages in 3.129s```

## 3. React and React DOM 

```npm i react react-dom``` 

These hold the react-core library and react dom functionality that we use to render the react app to the dom. 
It also contains the server-dise rendering to the dom. 
(created 8 new modules)
```added 8 packages from 3 contributors and audited 58 packages in 2.246s```

## 4. Webpack 

```npm i webpack webpack-cli```

Webpack is a module bundler. 
When we ship to browser we ship everything in a single bundle. 
Because browsers don't know how to work with modules jet. 
Bundle all the applications modules in a single file and ship that to the browser. 

```added 388 packages from 217 contributors and audited 448 packages in 16.943s```

## 5. Babel 

```npm i babel-loader @babel/core @babel/node @babel/preset-env @babel/preset-react```

Babel compiles jsx to React-api calls. 

Babel must be hooked into the webpack process. 
So that while Webpack compiles, if it sees any JSX, it should invoke babel to compile it to React-API calls. 
This is done by the `babel-loader`. 


The rest of the packages are configuring babel: 
 - babel/core - the core babel. 
 - babel/node - is needed if you are doing sereverside rendering. And is needed to understand jsx?
 - babel/preset-env - needed to target older browsers. (eg. compile the code to not use arrow-functions.)
 - babel/preset-react - needed to compile react.  


```added 169 packages from 59 contributors and audited 617 packages in 12.441s```


## 6. Development dependencies

Not needed in production. Mark them with `-D` flag. 

### 6.1 Dev: nodemon

```npm i -D nodemon```
Automatically restart node when we change things in node. 
Because node requires you to restart everytime you restarts something. 
Runs when you save. 
```added 95 packages from 33 contributors and audited 712 packages in 8.332s```

### 6.2 Dev: ESLint 

```npm i -D eslint babel-eslint eslint-plugin-react```

ESLint do checks in code as you type. 
ESLint will automatically analyse your code and tell you if you have a problem, 
or if your code is lacking in certain qualities. 
It can also be used it you want consistent styling, and this can be shared across the team. 

 - babel-eslint - so eslint understands babel 
 - eslint-plugin-react - undertsand jsx and react-stuff


## 7. Testing: Jest

(not in this course)

## 8. Prettier

(not in this course)

Works well with ESLint. Automatically formats the file when saving.

# Setting up the environment from scratch - Configuration

## ESLint

`.eslintrc.js`

## Directory structure

The structure can be how you like. 
But if you follow this, webpack-configuration will be easier. 
Because this is the structure webpack is looking for: 

 - dist - for distribution 
 - src - for sourcecode
 - src/components - for components daah (react-stuff)
 - src/server - for server-stuff daaaaah. 
 