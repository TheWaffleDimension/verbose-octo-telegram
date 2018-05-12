# Lisp-Like-Lang (LLL/3l)

## Intro
Heyo, wassup? This is the GitHub repo for a shared project between @isaacimagine and @TheWaffleDimension. We're working on a programming language standard similar to Lisp, and hopefully, we'll be able to get an implementation in soon. What is 3l? 3l is a lisp-like language modeled off of cLisp, Python, and the like. As of right now, 3l is solely numerical. A brief syntax overview is laid out in in the Documentation Section.

## Installation
To be decided.

## Documentation
We have 3 types in 3l, we'll represent them using these symbols:

#

| Name     | Symbol |
| -------- | ------ |
| Float    | $      |
| Integer  | #      |
| Boolean  | &      |
| Variable | .      |

-------

Expressions take types, and generate new ones:
As per tradition, we're using s-exps.

#

| Function Use | Output Type |
| ------------ | ----------- |
| (+ $# $#)    | $#          |
| (- $# $#)    | $#          |
| (= $# $#)    | &           |
| (> $# $#)    | &           |
| (< $# $#)    | &           |
| (and &)      | &           |
| (or &)       | &           |
| (not &)      | &           |
| (input)      |             |

-------

Expressions are then evaluated, then passed to Blocks:
 + [print $#&]
 + [set . : $#&]
Stacks of blocks are then put in, or around Control Flows:
 + [while & : {}]
 + [if & : {}]


Sample Program:
```
fizzBuzz:
[set x : 0]
[while &1 : {
    [set toPrint : 0]
		[set y : x]
		[while &1 : {
				[if (< y 1) : {
				    [break]
				}]
				[set y : (/ y 5)]
				[if (= y 1) : {
				    [set toPrint : -1]
						[break]
				}]
		}]
		[set y : x]
		[while &1 : {
				[if (< y 1) : {
				    [break]
				}]
				[set y : (/ y 7)]
				[if (= y 1) : {
				    [set toPrint : (- toPrint 2)]
						[break]
				}]
		}]
		[if (= toPrint 0) {
				[print x]
		}]
		[if (= toPrint -1) {
				[print 2215]
		}]
		[if (= toPrint -2) {
				[print 2208]
		}]
		[if (= toPrint -3) {
				[print 22082215]
		}]
		[set x : (+ x 1)]
}]
```

### Steps in our master plan to world dominance:
 - [ ] Input/Output (brainf: ,.)
 - [ ] Data Storage/Retrieval (><)
 - [ ] operations (+-)
 - [ ] Loops (if statements can be modeled from loops, when you thing about it) ([])
