# Numpy.jl
A siren's song to unwitting Pythonistas. Also a semantic/functional clone of the homonymous library.

## FAQ

- First of all: Why?
    - To ease one's transition to Julia by making someone familiar to Numpy feel "at home" using Julia (the siren's song yada yada ...)
    - To have an easy and fast answer to the question "with Numpy I do "X" using function "Y", how do I do "X" in Julia?"
    - ...
    - Profit !


- What do you mean by "semantic/functional clone"?

    It means it will, **as much as possible**, follow Numpy's syntax, structure, and behavior.

    Meaning, functions will have the same name and options, return the same types,
    source files and directories will likewise be organized the same way.
    A more concrete example: 

    if a given Numpy function `bla()` returns a list of integers, then Numpy.jl's `bla()` function will return a list of integers too. A Julian list of Julian integers, but a list of integers nonetheless.

    If the file that defines this function in Numpy is named `bla.py` and is located inside the `ploc` directory, then Numpy.jl will have a `ploc` directory with a `bla.jl` file inside too.


- Does it means that Numpy.jl will emulate all of Numpy's quirks and idiosyncrasies?

    Yes, but possibly not all of them. It will be a delicate balance between avoiding [maintenance](https://devblogs.microsoft.com/oldnewthing/?s=Getting+MS-DOS+games+to+run+on+Windows+95&submit=%EE%9C%A1)  [hell](https://support.microsoft.com/en-us/help/214326/excel-incorrectly-assumes-that-the-year-1900-is-a-leap-year) and  throwing the [Principle of Least Surprise](https://en.wikipedia.org/wiki/Principle_of_least_astonishment) out the window.


- Does it means that Numpy.jl will implement 100% of Numpy's API?

    Probably no. There are modules which are very specific to python, so kinda pointless to port, like e.g. `setuputils` and `f2py`.


- Will it have a C core and a Julia wrapper like Numpy?

    ![NO](noooooooo.gif)

    Now seriously, that's missing the point, because:
    - one of Julia's "raison d'être" is precisely not doing this kind of thing, A.K.A ["the two languages problem"](https://arxiv.org/abs/1209.5145).
    - In addition to core Julia, there are already some libraries that cover some parts of Numpy, they will be used whenever possible. Wheels work just fine as they are.
    Think about Numpy.jl more like a wrapper/rerouter to actual code rather than something made from scratch.


- Will it be a wrapper around Numpy's libraries?

    This goes to the "maybe in the future" category. [Scikit-learn.jl](/cstjean/ScikitLearn.jl) can do it with scikit-learn, though. 

    Nothing is out of the table, it's just too early to think of this.


- Is Scikit-learn.jl an inspiration?

    Definitely.

- Why LGPL3?

    Because it's enough for any (non-)commercial use anyone might have.

- Will there be a Scipy.jl or Pandas.jl in the future?

    Who knows ...


## (Roughly a) roadmap
- Implement the `core` module
- Find out the 3 ... 5 ... most used modules and implement them.
- Now I'll take requests from the audience. What's your favorite module that is not here yet?
- (Maybe) somekind of integration with [Py2Jl.jl](/JuliaCN/Py2Jl.jl), or using [Pycall.jl](/JuliaPy/PyCall.jl) to make a bridge to Numpy.
- Other ideas that may happen.
