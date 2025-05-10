# Google Meet Class 1
Module
A module is just a file, it can load each other and use special directives ‘export’ and ‘import’ to share functionality. Modularity is a key aspect of large scale software development. It helps to break a program into separate interchangeable components that can be used in different parts of the program. 
‘Export’ keyword labels variables and functions that should be accessible from outside the current module then ‘import’ allows the usage of the exporter ones in other modules.
In the tons of script tags, the order is important, one must not be mixed up before the other. We have to specifically name it the same name it was exported with so it can be imported correctly.
The module is the backbone of how things are done in JavaScript.
‘as’ is the key thing that helps us to achieve renaming
‘import *’ means import everything, it imports everything and saves it inside a variable, that variable becomes an object.

---
To use the default import, we have to use the default export. 
The key word for default export is ‘export default’
The default import can have any name, because it is default, it will automatically just assign whatever function or variable is coming.The difference between default and import * is that default just exports the particular thing you put export default in, while import * will take all the thing you are exporting and put it inside of an object so we can use them.
import maps allows us put JSON file inside a script and then use it. It allows us to map JSON to a particular import. We can import from HTTP URLs and data URLs. Dynamic imports is an import that looks like a function. It’s key goal is to give us the ability to import when we need to. It returns a function which is a promise based function. It allows loading ECMA script module asynchronously and dynamically into a potentially non-module environment. Dynamic import will only import when you need it, it is much more specific and will only run when you get to that particular line and it has to be ‘awaited’ before you can use it. It serves a much more amazing purpose than ordinary imports, put it as close as possible to where you want to use it.

---
Bundlers
‘NVM’ allows use of multiple versions at the same time.
‘npm init’ is a way to create a JavaScript project. JavaScript project have some identity that should show us what we do, we should see a package.JSON file in the code base.
A faster way is ‘npm init -y’
Or ‘npm init —yes’. The ES model can not work with npm packages that you install on your computer so it needs the bundler to help it be able to process that kind of npm packages. The browser needs something to package everything together and just give the browser what it understands since they can not do so much, we then employ the service of a bundler to do this. We can import ‘png’ or ‘svg’ because of bundlers, they become the level ground for all of us so things not available available in the browser but needed will be created by them.

---
npm init -y: Creates package.json, defining the project’s identity and dependencies.
Bundler (Vite): Bundles main.js, processes the npm package, and handles PNG/SVG imports, making them browser-compatible.
ES Modules: Uses import/export with ‘type="" ‘ in the <script> tag, relying on Vite to resolve dependencies.

