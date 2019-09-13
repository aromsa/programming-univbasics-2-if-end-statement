# Programming as Conversation 2: Selection with if...end and Statement Modifiers

## Learning Goals

* Write an `if...end` statement
* Write an `if...else...end` Statement
* Write an `if...elsif...else...end` Statement
* Use statement modifiers to change default sequence

## Introduction

We've covered the **default sequence** Ruby follows when reading and executing
a Ruby file: top-down, left-to-right for every non-commented line.

Let's teach the sequence to change by using the **selection**
statement: `if...end`. Selection statements skip code. If the default sequence
is top-down, they "hop over" some lines based on certain conditions.

## ![Selection Glyph](https://curriculum-content.s3.amazonaws.com/programming-univbasics-2/sequence-and-comments/Selection_midi.png) Write an `if...end` Statement 

```ruby
run_code_inside = true
puts "Code before if...end"
if run_code_inside
  puts "code inside"
end
puts "Code after if...end"
```

Try entering this code in your file and try running it. The output should be
the following:

```text
Code before if...end
code inside
Code after if...end
```

Following the **default sequence** we:

1. Assign `run_code_inside`
2. Print out with `puts "Code before if...end"`
3. Reach the `if` statement
4. Evaluate the expression to the right of the `if` statement
5. Since it evaluates `true`, we perform the code between the `if` and `end`
   reserved words
6. Print out with `puts "Code after if...end"`

Try changing `run_code_inside` from `true` to `false` and see how the **default
sequence** is overridden:

1. Assign `run_code_inside`
2. Print out with `puts "Code before if...end"`
3. Reach the `if` statement
4. Evaluate the expression to the right of the `if` statement
5. Since it evaluates `false`, we skip to the `end` reserved word
6. Print out with `puts "Code after if...end"`

## ![Selection Glyph](https://curriculum-content.s3.amazonaws.com/programming-univbasics-2/sequence-and-comments/Selection_midi.png) Write an `if...else...end` Statement

A slightly more advanced version of `if...end` is `if...else...end`. In this
code, we are guaranteed that the code in ONE of the two blocks will run (as the
Boolean expression can only ever be one of two choices).

```ruby
chance_of_rain = 0.2
puts "Let's go outside!"
if chance_of_rain > 0.5
  puts "Pack an umbrella!"
else
  puts "Enjoy the fine day!"
end
puts "Oh, and always wear sunscreen!"
```

The output is the following when the chance of rain is `<= 0.5`:

```text
Let's go outside!
Enjoy the fine day!
Oh, and always wear sunscreen!
```

If we change `chance_of_rain` to `1`, we get:

```text
Let's go outside!
Pack an umbrella!
Oh, and always wear sunscreen!
```

In an `if...else...end` statement, if the expression to the right of `if`
evaluates `true`, the work between `if` and `else` is run. If the expression to
the right of `if` evaluates `false`, the code between `else` and `end` runs.

## ![Selection Glyph](https://curriculum-content.s3.amazonaws.com/programming-univbasics-2/sequence-and-comments/Selection_midi.png) Write an `if...elsif...else...end`

Sometimes choices are strictly limited to a path A or path B option, sometimes
there's a third, fourth, option. In that case, we need the
`if...elsif...else...end` statement.

```ruby
chance_of_rain = 0.2
if chance_of_rain <= 0.25
  puts "Pack a sun shelter!"
elsif (chance_of_rain > 0.25 && chance_of_rain < 0.75)
  puts "Pack an umbrella!"
else
  puts "Stay home and read Hegel."
end
```

Try filling in a table on some scratch paper by changing the
value of `chance_of_rain`. You'll see that you get different output!

|`chance_of_rain` value|Output|
|-|-|
|`0.0000001`|&nbsp;|
|`0.2`|&nbsp;|
|`0.2000001`|&nbsp;|
|`0.3`|&nbsp;|
|`0.9`|&nbsp;|
|`1000`|&nbsp;|
|`-23`|&nbsp;|

## ![Selection Glyph](https://curriculum-content.s3.amazonaws.com/programming-univbasics-2/sequence-and-comments/Selection_midi.png) Use Statement Modifiers to Change Default Sequence

Ruby has a useful feature called a _statement modifier_ that allows you to put
a conditional at the end of a statement. For example, let's consider this
statement:

```ruby
puts "Hey, it's 2019!"
```

However, we don't want to say "Hey, it's 2019!" every time this code is run. We
**only** want to say it's 2019 if it's actually 2019. This is a good case for
an `if` statement modifier.

```ruby
puts "You know what year it is??"
this_year = 2019
puts "Hey, it's 2019!" if this_year == 2019
``` 

With output:

```text
You know what year it is??
Hey, it's 2019!
```

Now, with the statement modifier `if this_year == 2019` we are only putting it
if the year is, in fact, 2019.

We can also use `unless` in a statement modifier as well. 

> **LOGICAL FACT**: The English Logician Augustus DeMorgan _proved_ that
> "if-not" is equal to "unless." This had huge implications for the
> construction of CPUs, but he discovered it in the era of inkwells and steamer
> ships. See [DeMorgan's Laws][demorgan]

```ruby
this_year = 2019
puts "Hey, it's not 2019!" unless this_year == 2019
``` 

## Conclusion

In this lesson, we've learned the most essential SELECTION statement: the `if...else...end`
statement. It can be expanded slightly with `elsif`. SELECTION has multiple means
of use in Ruby

[demorgan]: https://en.wikipedia.org/wiki/De_Morgan%27s_laws
