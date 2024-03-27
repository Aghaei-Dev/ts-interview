# TS Interview

## Part one

<details>
  <summary>1 ) What is the Typescript Really is?</summary>

it's a free and open-source high-level programming language developed by Microsoft which acts as a statically-typed superset of JavaScript.
By extending JavaScript with type annotations and interfaces, it enables developers to catch errors during the compilation process rather than at runtime, thus ensuring safer and more efficient code

</details>

<hr/>

<details>

  <summary>2 ) can You explain some built in type in TS?</summary>
so We have several built in type in ts.
like :

- `number` : numeric values . integers or floats .
- `string` : Represents a sequence of characters, commonly used for storing textual data.
- `void` : Represents the lack of a type, commonly used as the return type for functions that do not return a value.
- `null` : Represents the absence of a value intentionally assigned to a variable.
- `undefined` : Represents a variable that has not yet been assigned a value.
- `any` :Represents any type of value and allows a variable to store multiple types.

give me an example :

```ts
let name: string = 'Aghaei'
let age: number = 22
let isAdmin: boolean = true
let user: null = null
let value: undefined = undefined
let uniqueKey: symbol = Symbol('key')
```

</details>

<hr/>

<details>

  <summary>3 ) What is <code>tsconfig.json</code> file?</summary>

it's a configuration file used by TypeScript to control various aspects of the TypeScript compiler behavior when building (transpile) TypeScript files into JavaScript. This file provides a way to define the **options** and **settings** that the TypeScript compiler (typically tsc CLI) should use during the compilation process.

it has many options like :

- `target`: Specifies the output language level, e.g., `ES5`, `ES6`, or a `higher ECMAScript version`.
- `module`: Sets the module system used in the output, e.g., CommonJS, AMD, UMD, or ES2015.
- `outDir`: Indicates the output directory for the compiled JavaScript files.
- `sourceMap`: Generates source map files for debugging purposes.
- `strict`: Enables stricter type checking and other compiler checks to ensure more robust code.
- `watch`: Enables watch mode, where the compiler will automatically recompile when there are changes in the TypeScript files.
- `exclude`: An array that lists file patterns to be excluded from the compilation, usually for files that are dependencies or not required for the build process.

and so on...

</details>

<hr/>

<details>

  <summary>4 ) Typescript advantages?</summary>

- Large-scale application support: TypeScript's features, such as generics, namespaces, and modules, foster the creation of modular and scalable code, making it an ideal choice for large and complex applications.

- Better tooling and editor support (intellisense and Developer Experience): TypeScript provides excellent integration with popular IDEs, resulting in advanced autocompletion, code navigation, and refactoring tools. This improves the development experience and boosts productivity.

- Static typing: TypeScript adds static typing to JavaScript, which catches type-related errors at compile-time instead of runtime. This allows developers to identify and fix issues early in the development process, reducing bugs and improving overall code quality.

- JavaScript ecosystem compatibility: TypeScript is fully compatible with JavaScript libraries, frameworks, and tools, enabling seamless integration into existing development workflows.

- Code maintainability: TypeScript's static types, interfaces, and other OOP features contribute to better code readability and maintainability, making it easier for developers to understand and work with shared codebase.

</details>

<hr/>

<details>

  <summary>5 ) String interpolation in Ts</summary>

its also known as template literal or template string.
It allows you to embed expressions within string literals, using backticks (`) instead of single or double quotes. To include a variable or expression within the string, use the ${expression} syntax.

example :

```ts
let name: string = 'Aghaei'
let job: string = 'front end developer'
let age: number = 22

let message: string = `hi! i'm ${name} and i'm ${age} years old . i'm a ${job}. happy to see you here`
```

</details>

<hr/>

<details>
  <summary>6 ) Optional parameters in TS?</summary>
A function can mark one or more of its parameters as optional by suffixing its name with ‘?’. In the example below, the parameter greeting is marked optional.
example :

```ts
function greeting(name: string, message?: string) {
  if (!greeting) greeting = 'Hello'

  console.log(`${greeting}, ${name}`)
}
```

</details>

<hr/>

<details>

  <summary>7 ) What do you know about Enum in TypeScript?</summary>

In TypeScript, an Enum (short for enumeration) is a custom data type that allows you to define a set of named numeric constants, making your code more self-explanatory and easier to maintain. Enums provide a robust and expressive way to handle sets of values that represent specific categories, states, or options in your program.

example :

```ts
enum Role {
  User,
  Admin,
  Guest,
}
```

</details>

<hr/>

<details>

  <summary>8 ) How can we Make an array readonly?</summary>

Using ReadonlyArray type, we can define Arrays to be read only

example :

```ts
function bar(array: ReadonlyArray<number>) {
  array.slice() //Just fine
  array.pop() //Error
}
```

</details>

<hr/>

<details>

  <summary>9 ) How can we extract some types and Ignore others?</summary>

we have Omit utility type.its create a new type from an existing type by excluding specific properties from it.it has two arguments first the type we want to modify and seconde the property we wanna omit.

example :

```ts
interface Product {
  id: number
  title: string
  price: number
}
type UnPriceProduct = Omit<Product, 'price'>
```

</details>

<hr/>

<details>

  <summary>10 ) How can we manage default parameters in a function in TS?</summary>

Easyy... just assign a default value in the function signature.

why we use default parameters?
it helps the function's flexibility and ensure that it behaves predictably even when some parameters are not supplied by the caller

example :

```ts
function greeting(name: string, message: string = 'hi') {
  console.log(`${message} , ${name}`)
}

greeting('john', 'good afternoon') // goodafternoon , john
greeting('doe') // hi , doe
```

</details>

## Part Two

<details>
  <summary>1 ) Explain User-defined data types in TS?</summary>

These are the data types that are defined by the user they may contain multiple values of multiple data types.

- `arrays` : In typescript, arrays are used to store the multiple values of any kind of data type.

- `classes` : Used to store different data type values in the form of key-value pairs.

- `Interface` : These represent the basic syntax and blueprint that an entity must adhere to.

- `enums` : A special class that specifies the constant variables.

</details>

<hr/>

<details>
  <summary>2 ) Explain The <code>any</code> type </summary>

There are times when you want to store a value in a variable but don’t know the type of that variable in advance. For example, the value is coming from an API call or the user input. The ‘any’ type allows you to assign a value of any type to the variable of type any.

</details>

<hr/>

<details>
  <summary>3 ) How to specify optional properties in TypeScript?</summary>

An object type can have zero or more optional properties by adding a ‘?’ after the property name.
In the example above, because the property ‘z’ is marked as optional, the compiler won’t complain if we don’t provide it during the initialization.

```ts
let coordinates: { x: number; y: number; z?: number } = {
  x: 10,
  y: 20,
}
```

</details>

<hr/>

<details>
  <summary>4 ) Explain the purpose of the never type in TypeScript</summary>

As the name suggests, the never type represents the type of values that never occur. For example, a function that never returns a value or that always throws an exception can mark its return type as never.

```ts
function throwError(message: string): never {
  throw new Error(message)
}
```

never Vs Void
why we use never sometimes?

You might wonder why we need a `never` type when we already have `void`. Though both types look similar, they represent two very different concepts.

A function that doesn't return a value implicitly returns the value undefined in JavaScript. Hence, even though we are saying it’s not returning anything, it’s returning ‘undefined’. We usually ignore the return value in these cases. Such a function is inferred to have a void return type in TypeScript.

</details>

<hr/>

<details>
  <summary>5 ) What is the <code>typeof</code> operator? How is it used in TypeScript?</summary>
typeof operator in TypeScript returns the type of the operand as a string.

you can use this for narrowing the type !

example :

```ts
type Combinable = string | number
function add(a: Combinable, b: Combinable) {
  if (typeof a === 'string' || typeof b === 'string') {
    return add.toString() + b.toString()
  }
  return a + b
}
```

</details>

<hr/>

<details>
  <summary>6 ) how to use rest parameters and arguments in TypeScript</summary>
A rest parameter allows a function to accept an indefinite number of arguments as an array. It is denoted by the ‘…’ syntax and indicates that the function can accept one or more arguments.

example :

```ts
function add(...values: number[]) {
  let sum = 0
  values.forEach((val) => (sum += val))
  return sum
}
const sum = add(20, 10, 20, 30)
console.log(sum) //80
```

</details>

<hr/>

<details>
  <summary>7 ) Explain the different variants of the for loop in TypeScript.</summary>

nothing changed from before !
just like before we use in the js...

- <code>for</code>

  ```ts
  const values = ['hello world', 2024, false]
  for (let i = 0; i < values.length; i++) {
    console.log(values[i])
  }
  ```

- <code>forEach</code>

```ts
const values = ['hello world', 2024, false]

values.forEach((val) => console.log(val))
```

- <code>for of</code>

```ts
const values = ['hello world', 2024, false]

for (let val of values) {
  console.log(val)
}
```

</details>

<hr/>

<details>
  <summary>8 ) Explain the symbol type in TypeScript.</summary>

Symbols were introduced in ES6 and are supported by TypeScript. Similar to numbers and strings, symbols are primitive types. You can use Symbols to create unique properties for objects.

You can create symbol values by calling the Symbol() constructor, optionally providing a string key.

example :

```ts
let one = Symbol('aghaei')
let sameAsOne = Symbol('aghaei')

console.log(one === sameAsOne) //false symbols are unique
```

</details>

<hr/>

<details>
  <summary>9 ) What is an interface?</summary>

An interface defines a contract by specifying the type of data an object can have and its operations. In TypeScript, you can specify an object’s shape by creating an interface and using it as its type. It’s also called “duck typing”.

example :

```ts
interface Employee {
  name: string
  salary: number
}

function printEmployeeData(employee: Employee) {
  console.log(`${employee.name}'s salary = ${employee.salary}`)
}

let john: Employee = {
  name: 'John Doe',
  salary: 10000,
}

printEmployeeData(john) // "John Doe's salary = 10000"
```

</details>

<hr/>

<details>
  <summary>10 ) Explain the various ways to control member visibility in TypeScript.</summary>

TypeScript provides three keywords to control the visibility of class members, such as properties or methods.

- <code>public</code> :You can access a public member anywhere outside the class. All class members are public by default.
- <code>protected</code> : A protected member is visible only to the subclasses of the class containing that member. Outside code that doesn’t extend the container class can’t access a protected member.
- <code>private</code> :A private member is only visible inside the class. No outside code can access the private members of a class.

</details>

<hr/>

## Part Three
