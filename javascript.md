<h1>clouser vs scope </h1>
<hr>

<h2>Scope : </h2>
<b>-> Scope means where a variable can be accessed in a program.</b>
<br>
- It defines the visibility or lifetime of variables.<br><br>

<b>ex.</b>

let a = 10; // global scope

function test() {
let b = 20; // local scope
console.log(a); // accessible
}

console.log(b); // error (b is not in this scope)<br><br>

<b>Types of Scope (in JavaScript) : </b>

<b>Global Scope</b> – variable accessible everywhere.

<b>Function Scope</b> – variable accessible only inside the function.

<b>Block Scope</b> – Blocks can be inside:
if
for
while
{ } anywhere in code

Variables declared with let and const have block scope.
<br>

So basically:
👉 Scope = rules that control where variables can be used.<br><br><br>

<h2>Clouser : </h2>
<b>-> Clouser is a function that remembers the variables of its outer function even after the outer function has returned.</b>
<br>
- It is a combination of a function and the lexical environment within which that function was declared.<br><br>

<b>ex.</b>

function outer() {

let a = 10;

function inner() {
console.log(a);
}

return inner;

}

let func = outer();

func(); // 10
<br>

<b>Here:</b>

inner() still remembers count.

Even though outer() has already finished.

👉 That memory of outer variables is called a closure.<br><br>

<h4>Key Difference : </h4>

<table>
<tr>
    <td><b>Scope</b></td>
    <td><b>Clouser</b></td>
</tr>
<tr>
    <td>Defines where variables are accessible.</td>
    <td>A function that remembers its outer variables.</td>
</tr>
<tr>
    <td>Concept related to variable visibility.</td>
    <td>Concept related to function + preserved scope.</td>
</tr>
<tr>
    <td>Exists during program structure.</td>
    <td>Exists when a function captures outer scope.</td>
</tr>
</table>
<br>

<h1>let vs var vs const</h1>
<hr>

<h3>1. var : </h3>
<b>-> var is the old way to declare variables (before ES6).</b><br><br>
<b>Key points :</b>
<ol>
<li>Function scoped</li>
<li>Can be redeclared</li>
<li>Can be updated</li>
<li>Hoisted (moves to the top of scope)</li>
</ol>
<br>
<b>ex.</b>

function test() {

if (true) {  
var a = 5; // here a will stick to function not this if block
}

console.log(a); // output : 5
}
test();
<br><br>

<h3>2. let : </h3>
<b>-> let was introduced in ES6 (2015).</b><br><br>
<b>Key points :</b>
<ol>
<li>Block scoped</li>
<li>Cannot be redeclared</li>
<li>Can be updated</li>
<li>Hoisted (moves to the top of scope)</li>
<li>Not usable before declaration (Temporal Dead Zone)</li>
</ol>
<br>
<b>ex.</b>

function test() {

if (true) {  
let a = 5; // here a will stick to this if block
}

console.log(a); // output : error (a is not in this scope)
}
test();
<br><br>

<h3>3. const : </h3>
<b>-> const is used for constant values.</b><br><br>
<b>Key points :</b>
<ol>
<li>Block scoped</li>
<li>Cannot be redeclared</li>
<li>Cannot be reassigned</li>
<li>Must be initialized when declared (Means Value of Const must be assigned at declaration)</li>
<li>Hoisted (moves to the top of scope)</li>
<li>Not usable before declaration (Temporal Dead Zone)</li>
</ol>
<br>
<b>ex.</b>

const x = 10;
x = 20; // value can't be reassigned
<br><br>
<b>-> objects and arrays can still change internally:</b>

<b>ex.2</b>

const user = { name: "John" };

user.name = "Mike"; // allowed
<br><br>

<h4>Key Diffrence :</h4>

<table>
<tr>
    <td><b>var</b></td>
    <td><b>let</b></td>
    <td><b>const</b></td>
</tr>
<tr>
    <td>Function scoped</td>
    <td>Block scoped</td>
    <td>Block scoped</td>
</tr>
<tr>
    <td>Can be redeclared</td>
    <td>Cannot be redeclared</td>
    <td>Cannot be redeclared</td>
</tr>
<tr>
    <td>Can be Reassign</td>
    <td>Can be Reassign</td>
    <td>Cannot be Reassign</td>
</tr>
<tr>
    <td>Hoisted</td>
    <td>Hoisted</td>
    <td>Hoisted</td>
</tr>
<tr>
    <td>Not usable before declaration (Temporal Dead Zone)</td>
    <td>Not usable before declaration (Temporal Dead Zone)</td>
    <td>Not usable before declaration (Temporal Dead Zone)</td>
</tr>
</table>
<br><br>

<h1>Data Types :</h1>
<b>-> Data types are the types of data that can be stored in a variable.</b>
<br>
<b>-> In JavaScript, there are two types of data types :</b>
<ol>
<li>Primitive Data Types</li>
<li>Non-Primitive Data Types</li>
</ol>
<br>

<h3>1. Primitive Data Types : </h3>
<b>-> Primitive data types are the basic data types that can be stored in a variable.</b>
<br>
<b>-> There are 7 primitive data types in JavaScript :</b>
<ol>
<li>String</li>
<li>Number</li>
<li>BigInt</li>
<li>Boolean</li>
<li>Undefined</li>
<li>Symbol</li>
<li>Null</li>
</ol>
<br>

<h3>2. Non-Primitive Data Types : </h3>
<b>-> Non-primitive data types are the complex data types that can be stored in a variable.</b>
<br>
<b>-> There are 3 non-primitive data types in JavaScript :</b>
<ol>
<li>Object</li>
<li>Array</li>
<li>Function</li>
</ol>
<br>

<h4>Practices :</h4>
<br><br>

<b>Ex.1</b>

console.log(typeof undefined); // output : undefined
<br><br>

<b>Ex.2</b>

const name = "John";
console.log(typeof name); // output : string
<br><br>

<b>Ex.3</b>

const age = 25;
console.log(typeof age); // output : number
<br><br>

<b>Ex.4</b>

const isStudent = true;
console.log(typeof isStudent); // output : boolean
<br><br>

<b>Ex.5</b>

const address = null;
console.log(typeof address); // output : object (this is a bug in JavaScript)
<br><br>

<b>Ex.6</b>

const user = { name: "John", age: 25 };
console.log(typeof user); // output : object
<br><br>

<b>Ex.7</b>

const colors = ["red", "green", "blue"];
console.log(typeof colors); // output : object (this is also a bug in JavaScript)
<br><br>

<b>Ex.8</b>

const greet = function() { console.log("Hello"); };
console.log(typeof greet); // output : function (this is also a bug in JavaScript)
<br><br>

<b>Ex.9</b>

const id = Symbol("id");
console.log(typeof id); // output : symbol
<br><br>

<b>Ex.10</b>

const bigNumber = 1234567890123456789012345678901234567890n;
console.log(typeof bigNumber); // output : bigint
<br><br>

<h3>Null vs Undefined : </h3>
<hr>

<b>Quick Comparison : </b>
<br>

<table>
<tr>
    <td><b>Feature</b></td>
    <td><b>Null</b></td>
    <td><b>Undefined</b></td>
</tr>
<tr>
    <td>Value meaning</td>
    <td>Explicitly empty</td>
    <td>Variable exists but no value</td>

</tr>
<tr>
    <td>Type</td>
    <td>"object"</td>
    <td>"undefined"</td>
</tr>
<tr>
    <td>Type</td>
    <td>No</td>
    <td>Yes (uninitialized variable)</td>
</tr>
<tr>
    <td>Assigned by programmer</td>
    <td>Often</td>
    <td>Sometimes</td>
</tr>
</table>
<br><br>
