---
title: Another Perversion of Human Thought Processes
tags:
- GOTO
- task switching
- cognition
- Inverse Markov Decision Process
- COMEFROM
- thought process
- Artificial Intelligence
- IMDP
excerpt: "My first word was... GOTO. At least as far as programming languages are concerned. It turns out that GOTO captures a fundemental thing about how our computers work, and how our minds *don't* work."
---

My first word was... `GOTO`.

I grew up in an age of steam locomotives, cobblestone roads and Z80 processors with the clock speed of a cuckoo watch. The first language I ever learned was BASIC, and `GOTO` was the first command I came across. I still love the exotic, Japanese elegance of these four letters, and the subtle combination of  simplicity, power and unconditional brutality that is embodied in its application. `GOTO` does not purport any kind of metaphysical humdrum that is so commonplace in contemporary programming ("functions as first class objects", "syntactic closures" etc.). It's a down-to-the-metal, no-nonsense equivalent to how the processor changes the locus of execution from one portion of the memorized program to an arbitrary other position. `GOTO` is the teleportation spell of computer programming: when the computer reads a `GOTO`, it immediately and unconditionally teleports to the location stated after the `GOTO` (in BASIC, to an arbitrary programming line).

Power corrupts, however, and lesser minds get easily confused, so [computer scientists] (http://www.massey.ac.nz/~kahawick/159331/Goto-Harmful-Dijkstra.pdf) went to work to abolish the magic word. It may be argued that program code has become more clear, pure and structured due to the prohibition of `GOTO`, but these are obviously requirements that reflect the depressing inability of mentally handicapped people to handle intricate, surprising and characterful control-flows. Naturally, connaisseurs of programs with these latter properties came up with the [`COMEFROM`](http://c2.com/cgi/wiki?ComeFrom) statement, to protest the influx of sanity into the sacred dungeons of our profession.
`COMEFROM` is the opposite of `GOTO`: it does not trigger a jump _from_ its own location, but instead _pulls_ the control to itself whenever the computer happens to process the location mentioned after the `COMEFROM`. A hapless reader who does not know all of the program won't know what hit him: the execution may leave the current point of execution at any time (just because some arbitrary `COMEFROM` may lurk in a dark corner of the code, patiently waiting for its chance to wrest control from an unsuspecting little routine task). Even better: there may be multiple `COMEFROM` statements pointing to the same location, battling for taking over in unforeseen ways. Its beautiful!

Sadly, because of the weak-mindedness of the programming establishment, `COMEFROM` has never become a popular addition of any serious programming language. But I have reason to think that meditating about it may yet prove useful: extensive use of the `COMEFROM` statement may be one of the defining characteristics of the human thought process.

Current AI paradigms often use Markov processes to model the equivalent of thought processes: each situation, event or object is treated as a place in a hypothetical space of possibilities, and control travels step by step from one place to its neighbors, depending on conditions and probabilities at the given place. This is not unlike to serendipitous traveling in the real world, including the ability to cover long distances in a very short time, but always triggered and enabled by the conditions I find in the original location. Human thought processes, however, often seem to work the other way around: during the course of contemplating element A, we do not switch to element B (because A has told us to), but our attention gets, suddenly and surprisingly, hogged by element Q, simply because it lurked in the background (together with many of its unruly brethren), and Q is agitated by A (and a host of other influences) so much that it calls all the attention to itself. For example, thinking about toroids may suddenly switch to a contemplation of eating candy, not because toroids hold references to candy, but because our candy activation sink holds references to donuts, and takes over whenever another thought process mentions donut shaped objects. Q (candy) effectively has a heuristic `COMEFROM` statement: with a certain probability, it will draw the control from A (toroids) to itself, no matter what A says and wants. Q is possibly not alone in possessing a `COMEFROM A`: many other states may strive to gain control, and will either suppress the competition or become active in parallel.

`COMEFROM` might be a terrible idea for writing deterministic and salient programming code, but it might also be an undervalued tool for building brain-like problem solving mechanisms. A starting point to harness the power of `COMEFROM` could be inverse, concurrent Markov processes, whereby many potential states are activated in parallel, monitoring the current state, and competing for becoming the locus of execution themselves. If you have thoughts, ideas or criticisms of today's lunchbreak epiphany, please let me know in the comments.

TL;DR: The (satirical) `COMEFROM` statement might be an important part of the control flow of human thought processes.