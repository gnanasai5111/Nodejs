# Node JS

- Node js is a open source,cross platform javascript runtime environment. Node Js run time environment provides all the neccessary components in order to use and run a 
 js program outside the browser.Node js was written in c++ to access the low level features like file system,networking etc which cant be accessed by Javascript. 
 
 
**Chrome v8 engine** 

- Javascript code we write cannot be understood by computer, for that we need javascript engine.Js engine is a program that converts js code into machine code that 
computer understands. Js engines are typically developed by web browser vendors.
- Chrome v8 engine sits at the core of Node.js


### Js engines in different browsers

- v8: Google(chrome)
- JavaScriptCore: Apple(safari) 
- Chakra: Microsoft(edge)
- SpiderMonkey: Mozilla(Firefox)

### Javascript RunTime

- It is an environment which provides all the necessary components in order to run javascript.
- In chrome Browser, Js Runtime consists of  components such as v8 Js engine, web apis(DOM,timers,promises,async,await,callbacks,browser storage), event loops,
microtask queue and callback/task queue.
- V8 Js engine executes js code. It conists of call stack where js code gets excecuted and heap which is the memory , which stores all the variables that 
js needs.

### Executing js with node
1. REPL(Read Evaluate Print Loop)
-To enter into REPL,type node as a command in terminal
2. Executing code in js file.
- In terminal type : node filename

### Modules
- In node js ,each file is treated as a seperate module.3 types of modules.
1. Local Modules- Modules we create in our application.
2. Built in Modules- Modules that node provides.
3. Third Party Modules- Modules written by other developers that we can use in our application.

### Local Modules
-we use require method to load one module in other.

```
syntax: require(filepath)
ex: require("./add.js");
```

- we can export the modules using module.exports

```
const addition=(a,b)=>{
    return a+b;
}

const multiply=(a,b)=>{
    return a+b;
}

 module.exports={add:addition,mul:multiply}; // named export
 (or)
 module.exports=addition   // default export 
 (or)
 module.exports={addition,multiply}    // named export

```

### Immedialtely invoked function expression

```

(function(){
console.log("hello");
})();

```

### Built-in modules
- path,events,fs,stream,http


### Events

```
const EventEmitter=require("events");  //It returns a class

const emitter=new EventEmitter();
emitter.on("order-pizza",(size,type)=>{       // listener to reponse to events emitted
    console.log("order received",size,type);
})

emitter.emit("order-pizza","large","chicken");
```

### file system(fs)

```
fs.readFileSync("./name.txt","utf-8");   // synchronous blocks the thread 
fs.readFile("./name.txt","utf-8",(err,data)=>{   //asynchronous
if(err){
    console.log(err);
}
else{
    console.log(data);
}
});
```


