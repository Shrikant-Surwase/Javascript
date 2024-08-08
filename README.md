This repo is used to take the important point/topics to understand the
javascript easily!!!!!

1) Javascript is the synchronous single threaded language
2) synchronous means each code is excecuted on in order
3) single threaded means code excecuted line by line
4) excecution context is very imp in js its one type of container where js code is excecuted
5) Its like a container in which two columns is there 1) Memory 2) Code
6) what happen when we excecute the js code?
7) Firs it create a GLOBAL EXCECUTION CONTEXT and then code is excecuted in two phase 1)memory creation phase and 2) code excecution phase
8) whenever we invoked the functin in js a LOCAL EXCECUTION CONTEXT is created and whenever return statement is their it will delete the local excecution context and return the value
9) In memory phase each value is assign to undefine first and then the declared value so undefied is imp in js
10) So what happend if we invoked a function in that function also a invoked another function so at that time the js engine create a global excecution context===>local excecution context===>local excecution context what is more like this So this is very tedious for js to overcome this js use STACK format to store the excecution context and called it as CALLSTACK
11) So the pick line is "CALLSTACK MAINTAIN THE ORDER OF EXCECUTION OF EXECUTION CONTEXT"
12) Hoisting is very interesting topic in js actually it is nothing but js default behaviour of moving declaration to the top 
means what happend when we declare a variable like
```javascript
called()
console.log(x)
console.log(called)
var x = 1
function called() {
    console.log('called')
}


}

```
this will give output like called undefined and given function called()
this is beacuse the HOISTING in js
13) Remember one thing that if we use arrow function then in global execution context the memory is allocated like variable 
e.g.
```javascript
//suppose we have a arrow function like this 
const data = () =>{
console.log('data')
}
```
at this time in global execution context the data = undefine is allocated insted of entire function
14) How functions are work in js?
we know that call stack are the stack where all the execution context is stored in stack format
lets take one example how the function is work
```javascript
var x = 1
a()
b()
console.log(x)
function a(){
console.log('a');
}
function b(){
console.log('b)
}
```
so what is the ouput the output is :
```javascript
a
b
1
```
why is like that bcause of the call stack 
consider it like a stack in which all the execution context is stored 
first stored the GEC(global execution context)
then a() LEC(local execution context)
it will run the function and return the a
and then pop the LEC of a()
the b() LEC is pushed
similarly execute the code and return the b
then pop from the call stack and then all the control is gone to the GEC

15) What is the WINDOW and THIS ?
Window is nothing but the global object created along with the global execution context
one more imp thing is this==window = true mean this is the keyword which is crated by the js engine along with the GEC
16) What is lexical environment and scope?
Lexical means the herarche where we have LEC along with the parent LEC
so every child has its LEC alog with its parent LEC so its like chain which is called scope chain

17) What is temporal dead zone?
So as we can see if we declare a variable with let or const then hoisted is not possible but in js let and const can be HOISTED
yes you heard right let or const can be hoisted but in a TEMPORAL DEAD ZONE;
So TDZ is the time in between the let variable is decleared to the value is assigned to that variable

18) what is BLOCK AND SCOPE?
BLOCK is nothing but the {} curly bracked which is also called compound statement
group of statement is used where the js expect a single statement
e.g. is if(conditon) true but what if we want multiple statement so at that time we need scope
one imp this is let and const is block scope means we can access the element only in the give block scope not outer that
but var is global scope we can access it throughout the scope
19) What is closures?
Now its time to learn hard topic , we know that we have lexical scope for a function and varible in that lexical scope can be access by using this function
so closure is the function bounded with the lexical environment/scope simple
```javascript

function init() {
    var x = 9;
    function a() {
        console.log(x);
    }
    return a;
}
const z = init();
console.log(z());

```
so here we can see z store the function along with its lexical scope or environment means we also have the value of x in z this is nothing but the closure which is used to return the function in the function
