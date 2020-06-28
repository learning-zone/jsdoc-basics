# JSDoc Tutorial 


An API documentation generator for JavaScript.

* *[JSDoc Guide](jsdoc-guide.md)*
* *[Live Example](https://learning-zone.github.io/general-interview-questions/jsdoc-example/docs/)*

## Installation and Setup


**Step 01**: 

To install the latest version on npm globally

    npm install -g jsdoc


To install the latest version on npm locally and save it in your package's
`package.json` file:

    npm install --save-dev jsdoc

**Step 02**:

Create a `package.json` file inside jsdoc-example folder using below command

```
    npm init -y
```
```
{
  "name": "jsdoc-example",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "doc": "jsdoc -c jsdoc.json"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "jsdoc": "^3.6.4"
  }
}

```
**Step 03**:  

Create a `jsdoc.json` file inside jsdoc-example folder

```
{
    "source": {
        "include": ["src"],
        "includePattern": ".js$",
        "excludePattern": "(node_modules/|docs)"
    },
    "plugins": ["plugins/markdown"],
    "templates": {
        "cleverLinks": true,
        "monospaceLinks": true
    },
    "opts": {
        "recurse": true,
        "destination": "./docs",
        "template": "./custom-template",
        "tutorials": "./tutorials",
        "readme": "./README.md"
    }
}
```
**Step 04**:

Create a src folder and add the following code

```javascript
/**
 * Class to create a person object
 */
class Person {
  /**
   * 
   * @param {Object} personInfo Information about the person 
   */
  constructor(personInfo) {
      /**
       * @property {string} name Person Name
       */
      this.name = personInfo.name;
      /**
       * @property {string} name Person Age
       */
      this.age = personInfo.age
  }
  
  /**
   * @property {Function} greet A greeting with the name and age
   * @returns void
   */
  greet() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age}`);
  }
}
```
Now run jsdoc in your command line
```
    npm run doc
```
This will create the docs directory which contains the mini-documentation for the **Person Class**. Open the **docs/index.html** file in your browser

<img src="assets/jsdoc.png" alt="JSDoc Image" />


## For more information

+ Documentation is available at [jsdoc.app](https://jsdoc.app/).
+ Contribute to the docs at
[jsdoc/jsdoc.github.io](https://github.com/jsdoc/jsdoc.github.io).
+ [Join JSDoc's Slack channel](https://jsdoc-slack.appspot.com/).
+ Ask for help on the
[JSDoc Users mailing list](http://groups.google.com/group/jsdoc-users).
+ Post questions tagged `jsdoc` to
[Stack Overflow](http://stackoverflow.com/questions/tagged/jsdoc).
