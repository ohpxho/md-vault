# PHP Notes - Sept. 10, 2025

## Closures

- Anonymous function
- Defined using `function` keyword
- You can bind variables outside of the scope of the closure by using `use` keyword

```
$myClosure = function($param1, $param2) use ($externalVariable) {
    // Function body
};
```

- You don't need to use `use` if you are going to access a super global variable or using $this

## Passing variables as reference

````
$closure = function () use (&$count) {
    $count++;
};```
````

- Add `&` when passing the variable.
- When you change its value from the passed reference, the original value will change as well

## What are Superglobals?

- Special built-in variables
- Always availables on any scope(class, closures, etc.)
- list:
  - $\_GET (holds the value from the url query stirng)
  - $\_POST (holds data sent via HTPP POST)
  - $\_REQUEST (contains GET, POST, COOKIE) (depends on PHP settings)
  - $\_SERVER (info about server and request environment)
  - $\_SESSION (stores data across multiple page request) (needs session_start())
  - $\_COOKIE (holds values sent by cookies from the client browser)
  - $\_FILES (info about uploaded files)
  - $\_ENV (envirnoment varialbes) (set in system or .env files)
  - $\_GLOBALS (an array of all global variables currently defined)
  - $php_errormsg (deprecated)

## Difference between globals and super globals
