---
title: A tale of two machines
tags:
- computationalism
- consciousness
- Göd
- dualism
thumbnail: /images/a-tale-of-two-machines/thumb.jpg
excerpt: "How is it possible that we can be conscious of a universe that at the same time computes us? How can we observe the progression of a universe that we are part of?"
---

How is it possible that we can be conscious of a universe that at the same time computes us? How can we observe the progression of a universe that we are part of? Assuming that our mind is fully embedded into our universe: If the universe would suddenly stop its computations, we could not notice. At every moment, we only exist in a single state. Single states cannot give rise to experience, as any mental process requires a sequence of states (for instance, to retrieve a memory and become aware of its contents).

"Cogito ergo sum" does not work for me: access to and interpretation of the idea that I seem to exist and cogitate in this moment requires a long computational process, which means that I have to introduce additional assumptions beyond the single state the universe offers in the present.
How can we resolve this?


Let _"Mind"_ be a computational machine that observes a universe.

Let the universe be a succession of states, each consisting in an ordered arrangement of little differences, that is, a vector of bits. (A bit is simply an information measure for a yes or a no.) The computation of the universe, i.e. the thing that lets us generate all these states which make up the universe, shall be defined using another machine. In honor of Kurz Gödel, who dedicated himself to the question of generating all valid mathematics from a set of initial axioms, I will call this universe computer _"Göd"_. 

Göd needs

- a set of possible instructions, 
- a current position, or _address_, of a bit in the universe, which is currently the object of computational manipulation
- the current instruction

The current instruction and position make up Göd's state (_"the Word"_). Göd is initialized with an initial universe state, an initial state and the first instruction (the Word).

Technically, we could store Göd's state as part of the universe's state, but that is not a requirement, and somewhat impractical, as it might mean that we have to set aside and insulate a part of the universe for Göd's state, and often come back to it to read it. (Therefore: _"In the beginning was the Word, and the Word was with Göd, and the Word was Göd."_)

The simplest format in which we could define an instruction consists of

~~~
if bit at current address is 0:
  write (0|1) at position
  position++ | position--
  current_instruction = (<one of the possible instructions>)
else: # bit at current address is 1
  write (0|1) at position
  position++ | position--
  current_instruction = (<one of the possible instructions>)
execute(current_instruction)
~~~

As you can see, this (pretty much) defines a Turing Machine. Many alternatives are possible, for instance, we could be writing and reading more than one bit within an instruction, or we could use probabilistic transitions. We could even have a Göd at every single position in the universe, never let them change positions, but allow them to read some of the other neighboring positions as input to the current instruction, which would define the universe as a _cellular automaton_.

As mentioned above, Mind is likewise a machine, one that uses a succession of observation states as its input (which takes in a vector of bits from the universe). Note that the order of the observation states does not necessarily need to be the order in which the universe is computed (the causal order does not have to co-incide with the apparent temporal order, which amounts to temporal non-locality). The mind has a current state, from which (combined with the observation state), it calculates a new current state.

In this arrangement, Mind does not itself write to the universe, because we have defined Göd as the computational engine of the universe already. However, Mind can be embedded into the universe, in such a way that Göd delivers the computational substrate of Mind.
In the common physicalist monist world view, this is indeed the case: the universe's state contains the patterns that we interpret as a brain with neural circuitry, and the neurons store and compute the state of Mind. The universe supplies Mind with an observation vectors (for instance, as patterns of information at its sensory nerves), but the Mind does not write to the universe, because that is already taken care of by the brain, i.e., the underlying substrate. Thus, Göd is causally insulated from Mind.

Other arrangements are possible: for instance, the universe could be computed within Mind. In this idealist monism, Mind would be Göd (but very likely without knowing it). In a sense, this is the case in dreams, or (according to many eastern and occult world views) the normal state of affairs.

In a dualist arrangement, where Mind is not computed by the universe and only reads from it, Mind's internal states cannot influence the universe itself. To become part of or influence the observation, an equivalent of internal states of Mind must be somehow duplicated by Göd (_occasionalism_). Otherwise, they won't ever be causally relevant for events in the universe (_epiphenomenalism_).

A computer within a computer is a common concept. For instance, it is possible to build a computer, complete with keyboard and display, and capable of running small games, in the computer game "Minecraft". This computer is powered by "redstone" conductors and switches supplied by the game. The computer architecture that runs Minecraft (a PC, Mac or tablet) won't have any influence on how the redstone computer runs. The redstone computer is causally insulated from the original substrate, despite partaking in it.
A redstone computer may also experience the apparent continuity of the sequence of states of the Minecraft program. That is possible because it uses only a small part of the Minecraft world for its implementation, and most of Minecraft won't play a causal role in the state of that inner computer, except indirectly, by influencing its observation vector .

<figure>
<iframe width="560" height="315" src="http://www.youtube.com/embed/lB684ym3QY4" frameborder="0"> </iframe> 
<figcaption>Laurens Weyn 2011: Redstone computer with GPU</figcaption>
</figure>

Thus, the redstone computer is practically causally insulated from its universe. Except in very special cases, which we can usually recognize, we can act as if they were indeed separate systems, and the redstone computer were running in its own substrate. Likewise, Mind can mostly be treated as causally independent even when observing and interacting with Göd.

The computation of I is sufficiently causally insulated from Göd that we can mostly ignore that I is part of Göd. We can observe the progress of the universe by storing memories of different observation vectors and interpreting them accordingly. We can even create a partial simulation of Göd in I. All of our memories are encoded in the current state of Göd, but that is irrelevant. Different parts of our memory encode different observation vectors of Göd, i.e. they allow us to experience Göd as a process, rather than a state.

