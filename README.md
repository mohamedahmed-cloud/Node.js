# Node.js
## ***Learning Node & Express from Freecodecamp***

[Video](https://www.youtube.com/watch?v=Oe421EPjeBE)

[Website](https://www.johnsmilga.com/)

[Github Code](https://github.com/john-smilga/node-express-course)



----
# MySummary
- we Will learn 
  - [ ] Node
  - [ ] express
  - [ ] mongoDB,Mongoose
  - [ ] Applications
  - [ ] Deployment
---
### Node.js
- is an enivorment to run js outside of the broswer
- Difference between node.js and broswer.js
---------
|broswer    |node       |
|-----------|-----------|
|DOM        | NO DOM    |
|Window     | NO Window |
|Interactive App |Server side app|
|No File system |File system|
|Fragmentation |version|
|ES6 Modules | common JS|

- `Vanilla js` is the pure js file without any using framework also called `plain js` and `core js`
- Ways to run js code directly
  - From make html file and js file then run it on broswer
  
    `OR`
  - From node.js command line it's called rpl stands for `read eval print` 
  
    `OR`
  - From Terminal that is in vs code means Cli excutable
---
### Globals 

- `__dirname` => path to current directory
- `__filename` => file name
- `require` => function to use modules `common js`
- `module` => info about current module (file)
- `process` => info about env where the program is being executed
---
### modules
- we can split our code files as many as we want but we notice a problem that we can't run more than one file at a time so we use module to handle this 
- Notes `next three block of code are sparately `
    ```js
    //sub file number one called "2.names"
    // secret
    const secret='f'
    // share
    const aya='aya'
    const sara='sara'
    // console.log(module)
    module.exports = {aya,sara}
    ```
    ```js
    //sub file number two called "3.function"
    const sayHi=(name)=>{
    console.log(`hello ${name}`)
    }
    module.exports =sayHi
    ```
    ```js
    //sub file number three called "4.extra"
    //Note when you export varible or funcition  like file number one differece when you export list or object
    module.exports.item=['mohamed','ahmed']
    const myObject={
        name :'mohamed',
        age : 21,
    }
    module.exports.my=myObject
    ```
    ```js
    //This is differnce from function in file two this executed commands in it when you invoke it in main file
    function printme(){
    console.log("MOhamed Ahmed Yousef")
    }
    printme()
    ```

    ```js
    //main file that will run 
    const names = require('./2.names')
    const sayHi = require('./3.function')
    const extra=require('./4.extra')
   //This function executed without make 'console.log() for it ' 
    require('./5.function2')

    sayHi("mohamed")
    sayHi(names.aya)
    sayHi(names.sara)
    console.log(extra)
    ```
---
### Built In Modules
- [ ] OS => Operation system module
- [ ] PATH
- [ ] FS => File System module
- [ ] HTTP => To set up `http server`
---
#### OS Module
- import os module
    ```js
    //import the module
    const os=require("os");
    ```
- get info about current user name
    ```js
    // info about current user
    const os=require("os");
    const user=os.userInfo();
    console.log(user)
    ```
- get the uptime for OS 

    ```js
    // method return system uptime in second
    const time=os.uptime();
    console.log(`my computer run for ${time} second`)
    ```
- get Info about OS 
```js
    // infor about my os
    const currentOS={
        name:os.type(),
        release:os.release(),
        totalMem:os.totalmem(),
        freeMem:os.freemem()
    }
    console.log(currentOS)
```
---
### Path Module
- help us to interact with file path easily
- import the module 
    ```js
    const path = require("path");
    ```
- type slash
    ```js
    const path = require("path");
    // Type the forward slash
    console.log(path.sep);
    ```
- Find the `path of the file` and `end of the path`
    ```js
    onst path = require("path");

    // Find the path of the file
    const filePath = path.join("/content", "subfolder", "test.txt");
    console.log(filePath);

    // Return the end of the filePath
    const base=path.basename(filePath);
    console.log(base)
    ```
- Return the absolute path of the file
    ```js
    const path = require("path");
    // return the absolute path 
    const absolute=path.resolve(__dirname, 'content','subfolder','test.txt');
    console.log(absolute)
    ```