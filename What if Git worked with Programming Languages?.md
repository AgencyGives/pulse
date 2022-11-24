I use git most days of the week. And for the vast majority of my commits, this means committing *code*.

So why would I say something like *What if Git worked with Programming Languages*?

Well, the title is deliberately provocative, but I genuinely mean it, and it's not wrong: Git does *not* work with programming languages. Instead it works with source files of text.

The fact that git works on *lines of text* has worked fantastically well - better than it has any right too. But is this as far as we can go?

## A Potted History of Version History

I absolutely love git, and I love what it has done to the development process even more.

I remember the bad old days of revision control. I used *file* based revision control on VMS. I've used CVS, subversion (svn), and visual source safe in development environments. The pain and torment these systems caused me has been quite successfully sublimated into my
unconscious mind, only rising to the surface when I'm forced to think about the history of revision control.

Git is not without its pains - you'll find yourself knee deep in some horrendous merge or rebase at some point, confused how to get things working again. But there are so many benefits over what it was like in the past that these things are easily excused.

The fundamentally multi-master approach of git, combined with the concepts of CI/CD have yielded enormous benefits. They've actually made my life better.

But they've also made collaboration better. I'm still learning about the potential to improve software develpment on a weekly basis. In my opinion the well of possibilities in most development houses is probably not yet fully tapped.

Automatic testing, including unit tests or even very sophisticated integration testing, becomes enormously simpler with the ability to create the *hypothetical commits* of a pull request. It's essentially like having a [modal logic](https://en.wikipedia.org/wiki/Possible_world) at our disposal for reasoning about correctness. And perhaps someday, these concepts will be made [formal](https://dl.acm.org/doi/pdf/10.1145/2661136.2661137).

Yet it would be hubris to think that this is the the end of history for versioning.

## Git for programming languages

The text-orientated design of git reflects the old unix philosophy of creating simple tools that work generically. And for unix, generic meant: files and text (think sed, awk, pipes etc).  Git builds on technology that literally goes back to the earliest days of unix, and
the `diff` program.

The *current* version of git is also able to find differences in binary files. But this eschews lines of text for continuous strings. This does not represent a *greater* awareness, but rather a *lesser* awareness of the *syntax and semantics*.

Programming languages are not really just lines of text. Diffs from two different changes to a source file are not necessarily composable, even if there are no overlapping changes. Program code has *syntax*, and this syntax is knowable, even in the case of the most dynamic of languages (such as those with configurable readers such as Common Lisp). A source file, if it isn't broken, represents a particular structured object, an abstract syntax tree.

We should be able to leverage this. When we do a diff between two different source programmes, we *could* be looking at the alterations to the [abstract syntax
tree](https://www.andres-loeh.de/GDiff.html). And these diffs can even be found, communicated and applied [efficiently](https://dl.acm.org/doi/10.1145/3341717).

And if we were storing information as ASTs, rather than lines of text, we could store them in a [graph database](http://terminusdb.com). Imagine the kinds of testing and linting which could now take place. You could have a full graph query language at your disposal to search for problems and perform analysis!

Of course the *unit of analysis* for programming languages has remained the text file. [Structure editors](https://en.wikipedia.org/wiki/Structure_editor) haven't really taken off yet despite several
[historical](https://larrymasinter.net/interlisp-ieee.pdf) and [contemporary](https://github.com/JetBrains/MPS) attempts.

There are probably some good reasons for this. Humans expect things that they saw recently adjacent to remain spatially adjacent. Files definitely act like this, whereas the SmallTalk approach of putting it in a database does not. However we don't have to abandon this structure to  get the additional benefits of structure editors. Lists also retain order and adjacency.

There is also the problem of what to do when in a syntactically invalid state. But there are ways around this (think commit) and some programming environments, (such as [agda-mode](https://agda.readthedocs.io/en/v2.6.0.1/tools/emacs-mode.html)) are good at it.

Editors could benefit from a whole universe of new possibilities if they were storing structured documents at commits, rather than merely source files. If you're worried that you need to put some code somewhere and you don't know what it is yet, this problem can be
solved with [holes](https://jfdm.github.io/post/2020-07-09-Programming-with-holes.html).

As code bases grow, the need for more sophisticated linting, for better approaches to search and retrieval, for looking at all callers of a function or procedure, etc. becomes ever more important. What could once be done with grep and a few text files ceases to be pragmatic when your source tree is several hundred thousands or even millions of lines, with elaborate source trees.

There are real advantages to going beyond the "lines of text" view of programming languages *in general*, but definitely in terms of version control *in particular*.

## The New (and Old) Data Science Tools

While there may be advantages as yet unexplored for languages like python, there is a new class of very widely used *notebooks* such as [Jupyter Notebooks](https://jupyter.org/). These tools are intermediate between analytic environments and programming environments. They store graphics, data and program code together in a way that the outcomes can be easily reconstructed. This is a big advantage in data-science where you want to share your results in a visually expressive way. It is also one of the reasons that JetBrains developed its MPS structure-editor. It was to facilitate the creation of domain-specific languages which could likewise have rich environments.

And while this new approach to data science feels cutting-edge, if we look carefully (and squint our eyes just the right way) we'll recognise that the most widely used [programming language on the planet, Excel](https://github.com/GavinMendelGleason/excel_as_code), is
one of these data-visualisation-programming systems.

Unfortunately, because these new notebooks are *richer* than mere text files, they also fight with our collaboration tools. Git is significantly more painful when working with Jupyter notebooks than with raw python. The more we begin to rely on these tools for rapid development of data science analytic results, the more we will need advancement of our version control tools to help us on the collaboration and CI/CD front.

## The Future is Structured

Git's power and advantage over older collaboration and revision control tools is clear, but is this the end of the story? I wager it isn't.

The future will be in structured storage, structured diff, structured linting and search and perhaps someday we will even finally get our structure editors.

# Post Script

For those of you interested in the [discussion on Hacker News](https://news.ycombinator.com/item?id=28670372), I've written below to respond to some of the points and objections.

# Does Git Dream in Text?

Quite a few people [commented in a discussion on Hacker News](https://news.ycombinator.com/item?id=28670372) regarding my position piece [What if Git worked with Programming Languages?](./README.md) stating that I'm wrong - that Git doesn't actually do anything with lines. I knew that when I wrote the piece that this objection would arise, and was a bit unsure of whether to deal with it in the piece or not.

In the end I decided against mentioning it.

The reason for doing so is that the vast majority of users of git *know* that git thinks in lines of text. How could anyone think otherwise? The git commands constantly are alerting you about changes in terms of lines of text, git has a built in diff command and many of the operations end up being the application of patches which are in fact lines of text. The programme interface structured in such a way that the git users experience is precisely about lines of text.

There are a few cognoscenti on the other hand who *know* that git is *not* storing changes to lines of text. This is actually very relevant to the *model* of git storage because other revision control systems in the past really *did* store [diffs as the primary quantum](https://en.wikipedia.org/wiki/Source_Code_Control_System). Git instead stores collections of hashes which are content addressable to entire snapshots. This is a very different, and arguably better, model.

Or at least arguably better if what you're doing is comparing lines of text.

## Storing Structure

Full disclosure: I'm a member of the engineering team which developed [TerminusDB](https://terminusdb.com/), a version controlled graph database. When we were designing the architecture, we used git as sort of north-star to understand the *best* way to do version control. Having used other version control systems, I wanted to avoid some of the pitfalls.

However, while many elements of the storage mechanism in git turned out to be useful and instructive, the fact that it stores file objects each as their own thing proved to be less than ideal for the use-cases we envisaged. We wanted to be able to store database structure and
retrieve *fragments* of previous states of the database quickly by querying them. With large amounts of queryable data it makes a lot more sense to use a [persistent data
structure](https://en.wikipedia.org/wiki/Persistent_data_structure), rather than a check-pointed dump.

And a graph database is convenient for storing ASTs. TerminusDB uses the idea internally to store the [query language](https://github.com/terminusdb/terminusdb/blob/main/src/terminus-schema/woql.json).

These aren't just text files after all.

## Different Diffs

As some people also mentioned, git *does* expose the ability to do different types of diffs. This could, in theory give you the ability to do structural diffs inside of git, given that you knew something about the syntax of the object you were working with.

However, how do you make a tool that doesn't know anything about the syntax of the objects with which you are dealing *a priori*. In this case you need to have a system which is able to perform diffs on [generic ASTs](https://www.andres-loeh.de/GDiff.html). Plus, you will need to be pushing the AST generation further up the chain. This allows you to generically support any language that can be represented as an AST.

## So Text it is

And here we are back to the fact that git is designed to work with text files. It is not meant for *storing structure*, *querying structure* or *diffing structure*.

That isn't a bad thing. It's just because of what git was designed for. As an excellent tool for tracking changes in text files.
