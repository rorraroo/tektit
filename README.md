# Tektit!

A somewhat tiny postfix stack language written in [Pyrop](https://github.com/rorraroo/pyrop) in a day as a proof it's a gem of a language (pun intended). Everything is a list of ints, every token is one character (except numbers), and it all works from the top of the stack.

Also tektite is a gem too, and a really cool one. Read about moldavites!

## How it runs?

```
pyrop tektit.prp samples/hello_builder.tkt
```

## How it works?

- Numbers push themselves: `12` → `[12]`
- Letters push a reference to their variable: `a` → address `97`
- Addresses are ASCII codes, so there are 128 variables (only letters have names)
- What gets pushed on top of the value stack is taken first from the value stack.

## How it operates?

| | |
| --- | --- |
| `.` `!` | peek / pop the top int |
| `,` | join two values |
| `~` | drop |
| `^` | fetch a variable's contents |
| `@` | store a value into a variable |
| `%` | toggle reference / literal |
| `#` `$` | print as numbers / as characters |
| `+ - * /` | math, element by element |
| `= < >` | compare, gives `1` or `0` |
| `[ ]` | loop while the top int isn't `0` |

## How it examples... okay I'm sorry

This code counts down from 10, one number per line. 

```
10.[.#10$1-.]
```

```
10
9
8
7
6
5
4
3
2
1
```

A better example is [this one](samples/hello_builder.tkt).