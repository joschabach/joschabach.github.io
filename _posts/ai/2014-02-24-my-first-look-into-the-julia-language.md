---
title: My first look into the Julia language
tags:
- julialang
- scientific computing
- programming
- Julia
- Python
excerpt: "Julia is a rather new programming language; it started out in 2009 and is being developed by bunch of scientific programmers at the MIT."
---

[Julia](http://julialang.org/) is a rather new programming language; it started out in 2009 and is being developed by bunch of scientific programmers at the MIT. The syntax looks a little like Matlab, and the authors really seem to have mathematical and statistical applications in mind. But in my view, Julia has the potential to become really popular in a few short years down the road. Julia's syntax is almost as pleasant to me as Python's, nothing looks too arcane and mind-bending, and yet at its core, it is a much more modern language.

Like Lisp, Julia allows the modification of its own syntax tree and gives us true macros (but still, we use infix notation, so Lispers will grumble). If you are really concerned with speed, you can access the low level virtual machine code and even assembler code from within Julia, too. Julia is also designed with multi-threading and large-scale distributed computation in mind, with easy-to-use coroutines. A generator syntax like in Python is missing, but there are work-arounds.

Julia also addresses my main gripe with Python: it allows for optional type annotations for arguments. I hate Java's type bureaucracy as much as any other hippie programmer out there, but sometimes, it would really help readability if I was allowed to specify a little type here and there. Even more importantly, the lack of type information is the main reason behind Python's sluggishness. Because the compiler can only infer the type of many objects at run-time, optimization is much harder, and Python's speed of execution is often one or two magnitudes worse than C. Julia has no such limitation; as a programmer, I can easily target bottlenecks in my code and optimize the heck out of them.

In some respects, Julia's syntax offers slight improvements over Python. You can often omit asterisks in multiplications (`2a + 7^b`, instead of `2*a + 7**b`) and some `return`s in functions (the result of the last expression will be returned). This is not very pythonic (it needlessly introduces syntactic variance), but makes your code look a little more like math at times. Also, Lambdas won't require the stupid `lambda` keyword. You can define a function to calculate the area of a circle like this, if you like:

~~~
α(r) = π*r^2
~~~

Other things, I like not so much. Block endings are not marked by indentation, but with `end` keywords, littering my code with redundancy. (Oh, I really loved my significant whitespace.) Julia also does not support trueish and falsish expressions in if statements, so instead of `if my_list: ...`, we would write `if length(my_list) > 0 ...`

Python does not offer abstract super-classes. Julia does the opposite: all super-classes must be abstract, i.e. it is not possible to subclass any existing types. I am sure that there is some great philosophy behind this, and perhaps we won't get as much duplicated code as I imagine, and yet... ~Also, Julia does not have namespaces yet, which I expect to create trouble once a lot of different community built libraries start shadowing each other's function names.~ Update: by now, Julia has namespaces, called 'modules'. (Thanks to John Myles White for pointing this out!)

How fast is Julia? There are many benchmarks, but let me see for myself. Here is a little bit of deliberately unoptimized code to calculate the first million prime numbers in Python:

~~~
def is_prime(n):
    if n < 4:
        return True
    if n % 2 == 0:
        return False
    for a in range(3, int(math.sqrt(n))+1):
        if n % a == 0:
            return False
    return True

def calculate_primes(n):
    "returns an array with n primes"
    primes = []
    p = 1
    for i in range(0, n):
        while not is_prime(p):
            p += 1
        primes.append(p)
        p += 1
    return primes
 
~~~


calculate_primes(1000000) took 6 minutes and 5 seconds on my computer.

The closest equivalent in Julia looks like this:

~~~

function is_prime(n)
    if n < 4
        return true
    end
    if n % 2 == 0
        return false
    end
    for a = 3:int(sqrt(n))
        if n % a == 0
            return false
        end
    end
    return true
end

function calculate_primes(n)
    primes = Int64[]
    p = 1
    for i = 1:n
        while ! is_prime(p)
            p += 1
        end
        push!(primes, p)
        p += 1
    end
    return primes
end

~~~


Julia was done after an impressive 32 seconds. Wow. That is more than 11 times faster in this simple example. (Adding type information to the function arguments will shave off less than a second, presumably because the LLVM already makes enough inferences.) Sure, Julia's transparent LLVM compilation is slower than Python's JIT compiler, but that would certainly be a tradeoff I am willing to make.

By the way, I could have omitted the `return` keyword at the last line of both functions, but not in the other lines (doing so will not produce error messages, but different results). I don't think omitting keywords in some positions but not in others will improve readability.

Despite my hatred for the `end` keyword (8 additional, totally redundant lines in the tiny bit of code above) and a bunch of niggles and little warts, I think that I could fall in love with Julia. But right now, I won't use it in any commercial or large-scale academic project (tools and libraries are nowhere near what you get for Common Lisp, Java, Python, Ruby or even Matlab and R). I would also not recommend it for learning or teaching programming, particularly because it still has a few teething issues, and its error messages are usually unhelpful (and in my experiments rarely pointed at the actual line with the bug). At the moment, Julia is a beautiful toy for those that want to pioneer new tools and frameworks in an emerging community. In the long run, interesting things will happen. If Julia manages to gain the maturity of Python and straightens out its warts, it might become the language of choice way beyond the statistics and science communities. But if Python stops stalling, gets its shit together and steals optional types, integrated  support for fast matrix operations and decent concurrency from Julia, ... ah, I should stop dreaming.

If you want to try Julia for yourself, you can download the free [JuliaStudio](http://forio.com/products/julia-studio/), a clean and easy to use but rudimentary IDE (much more primitive than even Python's pre-packaged IDLE). There is no dedicated Julia IDE available at this time, and the available packages for debugging and profiling are still quite experimental. The Julia documentation has come a long way in the last year, and the community seems to be growing rapidly, but of course it is nowhere near what you will find for the established languages.
