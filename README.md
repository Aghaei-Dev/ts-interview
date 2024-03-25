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

`number` : numeric values . integers or floats .
`string` : Represents a sequence of characters, commonly used for storing textual data.
`void` : Represents the lack of a type, commonly used as the return type for functions that do not return a value.
`null` : Represents the absence of a value intentionally assigned to a variable.
`undefined` : Represents a variable that has not yet been assigned a value.
`any` :Represents any type of value and allows a variable to store multiple types.

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

  <summary>6 ) String interpolation in Ts</summary>

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
