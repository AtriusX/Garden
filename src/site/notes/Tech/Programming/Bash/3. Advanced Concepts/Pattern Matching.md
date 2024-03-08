---
{"tags":["scripting","terminal"],"dg-publish":true,"authors":["Atri"],"permalink":"/tech/programming/bash/3-advanced-concepts/pattern-matching/","dgPassFrontmatter":true,"created":"2024-03-07T03:01:55.838-05:00","updated":"2024-03-08T03:26:52.493-05:00"}
---

## Case Statements

Control flow is able to be managed effectively by `if` statements [[Tech/Programming/Bash/2. Basic Concepts/2.5 Conditionals#^8e91a9\|as discussed here]]. Though, sometimes there may be cases where you want a more flexible option for handling command execution. This is where `case` statements come into play; they offer a much more flexible workflow compared to your typical `if` statement.

To define a `case` statement, you can define your logic like so:

```bash
example="hello"

case $example in
	world!)
		echo "Branch A"
		;;
	hello)
		echo "Branch B"
		;;
	*)
		echo "Branch C"
		;;
esac
```

> [!note] 
> You must use `;;` at the end of each pattern block; this is not a typo. In Bash, this syntax functions as the analog for the `break` keyword in equivalent languages when used in the context of a `case` statement.

Case statements also support simple union declarations per-pattern:

```bash
example="hello"

case $example in
	hello | world!)
		echo "Branch A"
		;;
	*)
		echo "Branch B"
		;;
esac
```

If the need arises, it is also possible to perform expression matching when a simple pattern is defined as the statement:

```bash
example="hello"

case $example in
	h*)
		echo "World!"
		;;
	*)
		echo "This should not execute"
		;;
esac
```

>[!warning] 
>While it may seem at a glance that you can use Regular Expressions with case statements, it does not appear that they function exactly the same as they do in other languages. Care should be taken to ensure your expressions are behaving exactly as intended.