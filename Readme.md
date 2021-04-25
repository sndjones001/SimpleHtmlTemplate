<!--- 
Reference to create a package file for static webpages: https://wweb.dev/blog/how-to-create-static-website-npm-scripts/ , https://github.com/wwebdev/static-website-template
Reference to github supported emoji: https://wweb.dev/blog/how-to-create-static-website-npm-scripts/ 
Reference to unicode symbols: https://www.compart.com/en/unicode/search?q=block#characters
Reference to svg icons in github: https://github.com/leungwensen/svg-icon
Reference to vscode icons in github: https://github.com/PKief/vscode-material-icon-theme/tree/master/icons
For markdown: https://docs.github.com/en/github/writing-on-github/working-with-advanced-formatting
For markdown github badges: https://github.com/Naereen/badges
For markdown logo github badges: https://github.com/Ileriayo/markdown-badges
--->


Here we describe the most basic setup for a website creator using nodejs development environment. File, folder Names, etc. are used to provide an example. Feel free to change the names as per your wish. 

# ✳️ Prerequisites
Install <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/nodejs.svg" alt="nodejs" width="16"> [node.js / npm](https://nodejs.org/en/). 
We are using <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/vscode.svg" alt="vscode" width="16"> [Visual Studio Code](https://code.visualstudio.com/) as an editor. Use your own editor as per your preference.  
Create a github reporsitory and clone and create a folder in your local system.

# ✳️ Setup npm package
Setup a new <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/npm.svg" alt="npm" width="16"> **npm** package. Execute the following command:
```bash
$ npm init
```


The <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16" style=""> **package.json** file looks like this:
```json
{
    "name": "simple-website",
    "version": "1.0.0",
    "description": "this is an example for a simple website with node.js",
    "main": "index.js",
    "scripts": {
    },
    "author": "<your-name>",
    "license": "ISC"
}
```
Now the directory structure looks like   

>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **node_modules**  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/git.svg" alt="gitattributes" width="16"> *.gitattributes*  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/git.svg" alt="gitignore" width="16"> *.gitignore*  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> package-lock.json  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> package.json  <br/>  

The two files <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/git.svg" alt="gitattributes" width="16">**.gitattributes** and <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/git.svg" alt="gitattributes" width="16">**.gitignore** may not be present depending upon how you created your git repository folder.  
A <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/git.svg" alt="gitattributes" width="16">**.gitattributes** file is a simple text file that gives attributes to pathnames. Enables you to perform a variety of functions such as commanding Git how it should diff (show changes between an index and a tree, changes between two trees, etc.) non-text files or having Git filter content before checking it into or out of Git. Settings are specified for a path, so that Git applies those settings only for a subdirectory or subset of files.  
A <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/git.svg" alt="gitattributes" width="16">**.gitignore** file specifies intentionally untracked files that Git should ignore.

# ✳️ Create <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/html.svg" alt="sass" width="25"> index.html
Create a <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/html.svg" alt="sass" width="16"> **index.html** file in the root directory. <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/html.svg" alt="sass" width="16"> **index.html** is considered the default file which is served.
```html
<!DOCTYPE html>
<html lang="de">
    <head>
        <title>Simple Website Template</title>
        <meta charset="utf-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1" />
    </head>

    <body>
        <h1>Simple Website Template</h1>
    </body>
</html>
```

# ✳️ Add Sass support
We will add support to <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/sass.svg" alt="sass" width="16"> **[Sass](https://sass-lang.com/)** modules. <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/sass.svg" alt="sass" width="16"> **[Sass](https://sass-lang.com/)** is a CSS extension language. 

## 🔹 Add [node-sass](https://www.npmjs.com/package/node-sass) module
Add a dev dependency for [![node-sass](https://img.shields.io/badge/node--sass-latest-green)](https://www.npmjs.com/package/node-sass). It enables us to compile [<img alt="SASS" src="https://img.shields.io/badge/SASS-hotpink.svg?&style=for-the-badge&logo=SASS&logoColor=white"/>](https://sass-lang.com/) files to [<img alt="CSS3" src="https://img.shields.io/badge/css3-%231572B6.svg?&style=for-the-badge&logo=css3&logoColor=white"/>](https://www.w3.org/Style/CSS/specs.en.html) files.  
Execute the following to install:
```bash
$ npm i -D node-sass
```

Add to the __*scripts*__ section in the <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> **package.json** file: 
```json
"css:scss": "node-sass --output-style compressed -o dist src/scss"
```

The <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> **package.json** file looks like this:
```json
{
    "name": "simple-website",
    "version": "1.0.0",
    "description": "this is an example for a simple website with node.js",
    "main": "index.js",
    "scripts": {
        "css:scss": "node-sass --output-style compressed -o dist src/scss"
    },
    "author": "<your-name>",
    "license": "ISC"
}
```

## 🔹 Create <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="25"> **src** folder
Create a directory <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **src**, and inside of <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **src** create <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **scss**. Now the directory structure looks like   


>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **node_modules**  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **src**  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;┗━ <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **scss**  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;┗━ <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/sass.svg" alt="json" width="16"> index.scss  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/git.svg" alt="gitattributes" width="16"> *.gitattributes*  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/git.svg" alt="gitignore" width="16"> *.gitignore*  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/html.svg" alt="sass" width="16"> index.html  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> package-lock.json  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> package.json<br/>

## 🔹 Execute <span style="padding: 10px 4px 5px; margin: 0; border-radius: 4px; color: #000; background-color: #F5F4F4; font-family:Consolas; font-weight: bold;">css:scss</span> npm command
When you execute this command in command line under the local repository directory
```bash
$ npm run css:scss
```

This will compile your <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/sass.svg" alt="sass" width="16">**.scss** files from <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **/src/scss/** into <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **/dist/**. Additionally the ***--output-style compressed*** will remove all line-breaks and whitespaces to reduce the file size.

The folder structure will look like this:

>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **dist**  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;┗━ <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/css.svg" alt="json" width="16"> index.css  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **node_modules**  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **src**  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;┗━ <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **scss**  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;┗━ <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/sass.svg" alt="json" width="16"> index.scss  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/git.svg" alt="gitattributes" width="16"> *.gitattributes*  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/git.svg" alt="gitignore" width="16"> *.gitignore*  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/html.svg" alt="sass" width="16"> index.html  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> package-lock.json  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> package.json<br/>


## 🔹 Link to [<img alt="CSS3" src="https://img.shields.io/badge/css3-%231572B6.svg?&style=for-the-badge&logo=css3&logoColor=white"/>](https://www.w3.org/Style/CSS/specs.en.html) file in [<img alt="HTML5" src="https://img.shields.io/badge/html5-%23E34F26.svg?&style=for-the-badge&logo=html5&logoColor=white"/>](https://www.w3.org/TR/html52/) file
Include the compiled <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/css.svg" alt="css" width="16">index.css file in the <head>of your <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/html.svg" alt="html" width="16">index.html.
```html
<!DOCTYPE html>
<html lang="de">
    <head>
        ...
        <link rel="stylesheet" type="text/css" href="dist/index.css">
    </head>

    ...
</html>
```

## 🔹 Add [autoprefixer](https://www.npmjs.com/package/autoprefixer) module
Add a dev dependency for [![autoprefixer](https://img.shields.io/badge/autoprefixer-latest-green)](https://www.npmjs.com/package/autoprefixer). This is plugin to parse CSS and add vendor prefixes to CSS rules using values.
Execute the following to install:
```bash
$ npm i -D autoprefixer
```
 
Add to the __*scripts*__ section in the <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> package.json file: 
```json
"css:autoprefixer": "postcss -u autoprefixer -r dist/*.css"
```
This will check your <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/css.svg" alt="css" width="16"> **css** files in the <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **/dist/** directory and add the prefixes for them. So you need to run two commands in sequence to build <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/css.svg" alt="css" width="16"> **css** files from <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/sass.svg" alt="scss" width="16"> **scss** files:
1. ```$ npm run css:scss```
1. ```$ npm run css:scss```

As we don't want to run the scripts one after another, let's add another script to the <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> **package.json** which will run the scripts sequentially by connecting the scripts with ***&&***.
```json
"build:css": "npm run css:scss && npm run css:autoprefixer"
```
By running ```$ npm run build:css```, you will now run firstly ```$ npm run css:scss``` and afterward ```$ npm run css:autoprefixer```.

## 🔹 Add Linting
We will use [![stylelint](https://img.shields.io/badge/stylelint-latest-green)](https://stylelint.io/) to make sure we have no errors in our CSS and to be able to enforce code conventions.  
Execute the following to install:
```bash
$ npm i -D stylelint
```

Before we're able to add the scripts for linting, we have to add the file <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/stylelint.svg" alt="stylelint" width="16"> .stylelintrc. This file will contain the rules, which stylelint should apply. For more information about the rules, you can check the [documentation](https://stylelint.io/user-guide/rules/list). Add some basic rules:
```json
"rules": {
    "block-no-empty": true,
    "color-hex-case": "lower",
    "color-hex-length": "short",
    "color-no-invalid-hex": true,
    "declaration-colon-space-after": "always",
    "max-empty-lines": 2
}
```
Add to the __*scripts*__ section in the <span style="padding: 10px 4px 5px; margin: 0; border-radius: 4px; color: #000; background-color: #F5F4F4; font-family:Consolas"><img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> package.json</span> file: 
```json
"css:lint": "stylelint src/scss/*.scss --syntax scss || true",
"build:css": "npm run css:lint && npm run css:scss && npm run css:autoprefixer"
```

The folder structure will look like this:

>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **dist**  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;┗━ <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/css.svg" alt="json" width="16"> index.css  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **node_modules**  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **src**  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;┗━ <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **scss**  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;┗━ <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/sass.svg" alt="json" width="16"> index.scss  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/git.svg" alt="gitattributes" width="16"> *.gitattributes*  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/git.svg" alt="gitignore" width="16"> *.gitignore*  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/html.svg" alt="sass" width="16"> index.html  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> package-lock.json  <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> package.json<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/stylelint.svg" alt="stylelint" width="16"> .stylelintrc


# ✳️ Add Automatic file update support
We will use [![onchange](https://img.shields.io/badge/onchange-latest-green)](https://www.npmjs.com/package/onchange) **npm** module which will watch the <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **/src/scss/** directory for changes and will run ```$ npm run build:css``` whenever there is any changes in any file.  

Execute the following to install:
```bash
$ npm i -D onchange
```

Add to the __*scripts*__ section in the <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> **package.json** file: 
```json
"watch:css": "onchange \"src/scss\" -- npm run build:css"
```

# ✳️ Add Automatic browser refresh support
Add [![browser-sync](https://img.shields.io/badge/browser--sync-latest-green)](https://github.com/BrowserSync/browser-sync) **npm** module. This helps in live reload and runs a local server.

Execute the following to install:
```bash
$ npm i -D browser-sync
```

Add to the __*scripts*__ section in the <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> **package.json** file: 
```json
"serve": "browser-sync start --server \"dist\" --files \"dist\""
```

As this will only watch the <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **/dist/** directory, so we need to move our <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/html.svg" alt="html" width="16"> **index.html** file into the <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **/dist/** directory.  
After moving the <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/html.svg" alt="html" width="16"> **index.html**, we need to update the stylesheet link to ```href="/index.css"```.  
If you now run ```$ npm run serve ``` your website should automatically open in the browser.

# ✳️ Add Automatic run all support
We can make it efficient by adding support to run the ``` watch ``` and the ``` browser-sync ``` together. We will add [![npm-run-all](https://img.shields.io/badge/npm--run--all-latest-green)](https://www.npmjs.com/package/npm-run-all) npm module.

Execute the following to install:
```bash
$ npm i -D npm-run-all
```

Add to the __*scripts*__ section in the <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> **package.json** file: 
```json
"watch": "run-p serve watch:css"
```

By running ```$ npm run watch``` we are watching for changes in our directory <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> /**src/scss** and compile our <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/sass.svg" alt="scss" width="16"> **scss** into the <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **/dist/** directory. Also, we have autoprefixing and linting for our CSS in place. Additionally, the script is running a development server, which automatically refreshes our browser whenever something in distchanges.

# ✳️ Add image minification support
By reducing the file size of images, we can improve the webpage loading speed. We will use [![imagemin-cli](https://img.shields.io/badge/imagemin--cli-latest-green)](https://www.npmjs.com/package/imagemin-cli).

Execute the following to install:
```bash
$ npm i -D imagemin-cli
```

Add to the __*scripts*__ section in the <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> **package.json** file: 
```json
"build:images": "imagemin src/images/**/* --out-dir=dist/images",
"watch:images": "onchange \"src/images\" -- npm run build:images"
```

If you now run ```$ npm run build:images``` it will minify all images in your directory <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **/src/images** and store them in <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **/dist/images**. The ```watch``` script will look for changes in <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **/src/images** and will run the ``` build ``` script whenever something changes.

Update the ```watch``` script to the __*scripts*__ section in the <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> **package.json** file: 
```json
"watch": "run-p serve watch:*",
"build": "run-p build:*"
```

This runs both the ``` watch:css ``` and ``` watch:images ``` script. The ``` * ``` operator makes the scripts run all other scripts starting with ``` watch: ``` or ``` build: ```. If you have your ``` $ npm run watch ``` script still running, you need to restart it.

# ✳️ Add <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/javascript.svg" alt="javascript" width="25"> Javascript support
[![imagemin-cli](https://img.shields.io/badge/webpack-latest-green)](https://github.com/webpack/webpack) npm module is a module bundler. Its main purpose is to bundle <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/javascript.svg" alt="javascript" width="16"> **Javascript** files for usage in a browser, yet it is also capable of transforming, bundling, or packaging just about any resource or asset.  

[![babel](https://img.shields.io/badge/babel-latest-green)](https://babeljs.io/) is a toolchain that is mainly used to convert ECMAScript 2015+ code into a backwards compatible version of JavaScript in current and older browsers or environments. We will use 
1. [![babel-loader](https://img.shields.io/badge/babel--loader-latest-green)](https://github.com/babel/babel-loader). This package allows transpiling JavaScript files using [babel](https://babeljs.io/) and [webpack](https://github.com/webpack/webpack).
1. [![@babel/preset-env](https://img.shields.io/badge/@babel/preset--env--loader-latest-green)](https://babeljs.io/docs/en/babel-preset-env) is a smart preset that allows you to use the latest JavaScript without needing to micromanage which syntax transforms (and optionally, browser polyfills) are needed by your target environment(s). This both makes your life easier and JavaScript bundles smaller!

Execute the following to install:
```bash
$ npm i -D webpack webpack-cli babel-loader @babel/preset-env
```

Create a file <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/webpack.svg" alt="webpack" width="16"> **webpack.config.js** in your project root with the following content:
```javascript
module.exports = {
    entry: './src/js/main.js',
    output: {
        path: __dirname + '/dist',
        filename: 'bundle.js'
    },
    module: {
        rules: [{
            test: /\.m?js$/,
            exclude: /node_modules/,
            use: {
                loader: 'babel-loader',
                options: {
                    presets: ['@babel/preset-env']
                }
            }
        }]
    }
}
```

Update the __*scripts*__ section in the <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> **package.json** file: 
```json
"build:js": "webpack --mode=production",
"watch:js": "onchange \"src/js\" -- webpack --mode=development"
```

This will use the **development** mode when we're watching the files and the **production** mode when we run ```npm run build```.  
Add the entry point of the output js file <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/javascript.svg" alt="javascript" width="16"> bundle.js created in <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **dist** directory to the <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/html.svg" alt="html" width="16"> **index.html** file:  

```html
<script src="./bundle.js"></script>
```
```markdown
Best Practice

ℹ️  Maintain a single entry point for javascript files say, in /src/js/main.js.
Use moduler approach where maintain seperate javascript files for different logics
but import them into single file main.js as 

import './somemodule'
```

# ✳️ Add linting support
We will also add a linter for javascript files. We will install [![eslint](https://img.shields.io/badge/eslint-latest-green)](https://github.com/eslint/eslint) **npm** module and [![eslint-webpack-plugin](https://img.shields.io/badge/eslint--webpack--plugin-latest-green)](https://github.com/webpack-contrib/eslint-webpack-plugin) **npm** module.

Execute the following to install:
```bash
$ npm i -D eslint eslint-webpack-plugin
```

To enable linting we need to create a configuration file <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/eslint.svg" alt="eslint" width="16"> **.eslintrc.json** in the root folder and add the module to our webpack configuration. For detail see the [documentation](https://eslint.org/docs/user-guide/getting-started).  

The <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/eslint.svg" alt="eslint" width="16"> **.eslintrc.json** file may contain:

```json
{
    "env": {
        "browser": true,
        "es2021": true
    },
    "extends": [
        "standard"
    ],
    "parserOptions": {
        "ecmaVersion": 12,
        "sourceType": "module"
    },
    "rules": {
        "quotes": [
            "error",
            "double"
        ],
        "indent": ["error", 4],
        "no-path-concat": "off"
    }
}
```


# ✳️ Add html support
For development using multiple html pages we can use the following modules:

1. [![posthtml](https://img.shields.io/badge/posthtml-latest-green)](https://github.com/posthtml/posthtml) **npm** module → is a tool for transforming HTML/XML with JS plugins.
1. [![posthtml-cli](https://img.shields.io/badge/posthtml--cli-latest-green)](https://github.com/posthtml/posthtml-cli) **npm** module → **PostHTML** сommand line interface
1. [![posthtml-modules](https://img.shields.io/badge/posthtml--modules-latest-green)](https://github.com/posthtml/posthtml-modules) **npm** module → Import and process HTML Modules with PostHTML
1. [![htmlnano](https://img.shields.io/badge/htmlnano-latest-green)](https://github.com/posthtml/htmlnano) **npm** module → Modular HTML minifier, built on top of the **PostHTML**.

Execute the following to install:
```bash
$ npm i -D posthtml posthtml-cli posthtml-modules htmlnano
```

Create the file <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> **posthtml.json** in the project root, which contains the configuration for the posthtml build:
```json
{
    "input": "src/views/*.html",
    "output": "dist",
    "plugins": {
        "posthtml-modules": {
            "root": "./src/views",
            "initial": true
        },
        "htmlnano": {}
    }
}
```

This will tell **posthtml** to render all <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/html.svg" alt="json" width="16"> **HTML** files from <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **src/views** into <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **dist**. Now we only need to move the <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/html.svg" alt="json" width="16"> **index.html** from <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **dist** to <img src="https://raw.githubusercontent.com/leungwensen/svg-icon/master/dist/svg/ant/folder.svg" alt="folder" width="16"> **src/views** and update the <img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/master/icons/json.svg" alt="json" width="16"> **package.json** with the scripts:

```json
"build:html": "posthtml -c posthtml.json",
"watch:html": "onchange \"src/views\" -- npm run build:html"
```
