
# fasteR: Fast Lane to Learning R! 

![alt text](https://raw.githubusercontent.com/matloff/prVis/master/data/SwissRoll/SWwithY.png)

## *"Becoming productive in R, as fast as possible"*

### Norm Matloff, Prof. of Computer Science, UC Davis; [my bio](http://heather.cs.ucdavis.edu/matloff.html)

(See notice at the end of this document regarding copyright.)

This site is for those who know nothing of R, and maybe even nothing of
programming, and seek *QUICK, PAINLESS!* entree to the world of R.

* **FAST**:  You'll already be doing good stuff in R -- useful data analysis
-- in your very first lesson.

* **For nonprogrammers:**  If you're comfortable with navigating
the Web and viewing charts, you're fine.  This tutorial is aimed 
at you, not experienced C or Python coders.

* **Motivating:**  Every lesson centers around a *real problem* to be
solved, on *real data*.  The lessons do *not* consist of a few toy
examples, unrelated to the real world.  The material is presented in a
conversational, story-telling manner.

* **Just the basics, no frills or polemics:** 

    - Notably, in the first few lessons, we do NOT use Integrated
      Development Environments (IDEs).  RStudio, ESS etc. are great, but
you shouldn't be burdened with learning R *and* learning an IDE at the
same time, a distraction from the goal of becoming productive in R as
fast as possible.  

     Note that even the excellent course by [R-Ladies
Sydney](https://threadreaderapp.com/thread/1119025557830684673.html),
which does start with RStudio, laments that RStudio can be
**"way too overwhelming."**  

     So, in the initial lessons,  we stick to the R command line, and
focus on data analysis, not tools such as IDEs, which we will cover as
an intermediate-level topic.  (Some readers of this tutorial may already
be using RStudio or an external editor, and the treatment here will
include special instructions for them when needed.)

    - Coverage is mainly limited to base R. So for instance the popular
      but self-described "opinionated" Tidyverse is not treated at first, 
      partly due to its controversial nature (I am a [skeptic](http://github.com/matloff/TidyverseSkeptic)), 
      but again mainly because it would be an obstacle to your 
      becoming productive in R quickly.  A later lesson to be added will 
      introduce Tidy (defined as **dplyr** and pipes) and compare it to base-R.

      While you can learn a few simple things in Tidy quickly, thinking
      you are learning a lot, those things are quite limited in scope,
      and Tidy learners often find difficulty in applying R to real
      world data.  <span style="color:red"> Our tutorial here is aimed
      at learners whose goal is to USE the R system productively in
      their own data analysis.  </span>  

* **Nonpassive approach:**  Passive learning, just watching the screen, is NO
learning.  There will be occasional **Your Turn** sections, in which you the 
learner must devise and try your own variants on what has been presented.
Sometimes the tutorial will be give you some suggestions, but even then,
you should cook up your own variants to try.  <span style="color:red"> 
Remember:  You get out what you put in!</span>  The more actively you
work the **Your Turn** sections, the more powerful you will be as an R
coder.

## Table of Contents

**PART I**
* [Lesson 1: Getting Started](#overview)
* [Lesson 2: First R Steps](#firstr)
* [Lesson 3: Vectors and Indices](#vecidxs)
* [Lesson 4: More on Vectors](#less2)
* [Lesson 5: On to Data Frames!](#less3)
* [Lesson 6: The R Factor Class](#less4)
* [Lesson 7: Extracting Rows/Columns from Data Frames](#extractdf)
* [Lesson 8: More Examples of Extracting Rows, Columns](#moreextract)
* [Lesson 9: The tapply Function](#tapply)
* [Lesson 10: Data Cleaning](#less5)
* [Lesson 11: The R List Class](#less6)
* [Lesson 12: Another Look at the Nile Data](#less7)
* [Lesson 13: Pause to Reflect](#pause1)
* [Lesson 14: Introduction to Base R Graphics ](#less8)
* [Lesson 15: More on Base Graphics ](#less9)
* [Lesson 16: Writing Your Own Functions](#less10)
* [Lesson 17: 'For' Loops](#less11)
* [Lesson 18: Functions with Blocks](#ftnbl)
* [Lesson 19: Text Editing and IDes](#edt)
* [Lesson 20: If, Else, Ifelse](#ifelse)
* [Lesson 21: Do Pro Athletes Keep Fit?](#keepfit)
* [Lesson 22: Linear Regression Analysis, I](#linreg1)
* [Lesson 23: S3 Classes](#s3)
* [Lesson 24: Baseball Player Analysis (cont'd.)](#less15)
* [Lesson 25: R Packages, CRAN, Etc.](#cran)

**PART II**
* [Lesson 26: A Pause, Before Going on to Advanced Topics](#advanced)
* [Lesson 27: A First Look at ggplot2](#gg2first)
* [Lesson 28: Should You Use Functional Programming?](#appfam)
* [Lesson 29 Simple Text Processing, I](#txt)
* [Lesson 30: Simple Text Processing, II](#txt1)
* [Lesson 31: Linear Regression Analysis, II](#linreg2)
* [Lesson 32: Working with the R Date Class](#dates)
* [Lesson 33: Tips on R Coding Style and Strategy](#style)
* [Lesson 34: The Logistic Model](#logit)
* [Lesson 35: Files and Directories](#fd)
* [Lesson 36: R 'while' Loops](#whl)
* [To Learn More](#forMore)
* [Thanks](#thanks)
* [Appendix: Installing and Using RStudio](#rstudio)


## <a name="overview"> </a> Lesson 1:  Getting Started

For the time being, the main part of this online course will be this
**README.md** file.  It is set up as a potential R package, though, and
I may implement that later.

The color figure at the top of this file was generated by our
[`prVis` package](https://github.com/matloff/prVis/),
run on a famous dataset called *Swiss Roll*.

### Please note again:  

* Nonpassive learning is absolutely key!  So even if the output of an R
  command is shown here, run the command yourself in your R console, by
copy-and-pasting from this document into the R console.  <span
style="color:red">You will get out of this tutorial what you put
in.</span>  

* Similarly, the **Your Turn** sections are absolutely crucial.  Devise
  your own little examples, and try them!  "When in doubt, Try it
out!" is a motto I devised for teaching.  If you are unclear or
curious about something, try it out!  Just devise a little experiment,
and type in the code.  Don't worry -- you won't "break" things.

* <span style="color:red">Tip:</span>  I cannot *teach* you how to
program.  I can merely give you the tools, e.g. R vectors, and some
examples.  For a given desired programming task, then, you must
creatively put these tools together to attain the goal.  Treat it like a
puzzle!  I think you'll find that if you stick with it, you'll find
you're pretty good at it.  After all, we can all work puzzles.

### Starting out:

You'll need to [install
R](https://www.datacamp.com/community/tutorials/installing-R-windows-mac-ubuntu),
from [the R Project site](https://www.r-project.org).  Start up R,
either by clicking an icon or typing `R` in a terminal window.  We are
not requiring RStudio here, but if you already have it, start it; you'll
be typing into the R console, the Console pane.

As noted, this tutorial will be "bare bones."  In particular, there is
no script to type your command for you.  Instead, you will either
copy-and-paste from the text here into the R console, or type them there
by hand.  (Note that the code lines here will all begin with the R
interactive prompt, `>`; that should not be typed.)

This is a Markdown file.  You can read it right there on GitHub, which
has its own Markdown renderer. Or you can download it to your own
machine in Chrome and use the Markdown Reader extension to view it (be
sure to enable Allow Access to File URLs).  

When you end your R session, exit by typing `quit()`.

Good luck!  And if you have any questions, feel free to e-mail me, at
matloff@cs.ucdavis.edu

## <a name="firstr"> </a> Lesson 2: First R Steps

The R command prompt is `>`.  Again, it will be shown here, but you don't type
it.  It is just there in your R window to let you know R is inviting you
to submit a command.  (If you are using RStudio, you'll see it in the
Console pane.) 

So, just type `1+1` then hit Enter.  Sure enough, it prints out 2 (you
were expecting maybe 12108?):

``` r
> 1 + 1
[1] 2
```
But what is that `[1]` here?  It's just a row label.  We'll go into that
later, not needed quite yet.

### Example: Nile River data

R includes a number of built-in datasets, mainly for illustration
purposes.  One of them is `Nile`, 100 years of annual flow data on the
Nile River.

Let's find the mean flow:

``` r
> mean(Nile)
[1] 919.35
```

Here `mean` is an example of an R *function*, and in this case Nile is
an *argument* -- fancy way of saying "input" -- to that function.  That
output, 919.35, is called the *return value* or simply *value*.  The act
of running the function is termed *calling* the function.

Another point to note is that we didn't need to call R's `print`
function.  We could have typed,

``` r
> print(mean(Nile))
```

Function calls in R (and other languages) work "from the inside out."
Here we are asking R to find the mean of the Nile data, then print the
result.

But whenever we are at the R `>` prompt, any expression we type will be
printed out anyway, so there is no need to call `print`.

Since there are only 100 data points here, it's not unwieldy to print
them out.  Again, all we have to do is type ``Nile,'' no need to call
**print**:

``` r
> Nile
Time Series:
Start = 1871 
End = 1970 
Frequency = 1 
  [1] 1120 1160  963 1210 1160 1160  813 1230 1370 1140  995  935 1110  994 1020
 [16]  960 1180  799  958 1140 1100 1210 1150 1250 1260 1220 1030 1100  774  840
 [31]  874  694  940  833  701  916  692 1020 1050  969  831  726  456  824  702
 [46] 1120 1100  832  764  821  768  845  864  862  698  845  744  796 1040  759
 [61]  781  865  845  944  984  897  822 1010  771  676  649  846  812  742  801
 [76] 1040  860  874  848  890  744  749  838 1050  918  986  797  923  975  815
 [91] 1020  906  901 1170  912  746  919  718  714  740
```

Now you can see how the row labels work.  There are 15 numbers per row
here, so the second row starts with the 16th, indicated by `[16]`.  The
third row starts with the 31st output number, hence the `[31]` and so
on.

Note that a set of numbers such as `Nile` is called a *vector*.

### A first graph

R has great graphics, not only in base R but also in wonderful
user-contributed packages, such as `ggplot2` and `lattice`.  But
we'll stick with base-R graphics for now, and save the more powerful yet
more complex `ggplot2` for a later lesson.

We'll start with a very simple, non-dazzling one, a no-frills histogram:

``` r
> hist(Nile)
```

No return value for the `hist` function (there is one, but it is
seldom used, and we won't go into it here), but it does create the
graph.

![alt text](https://raw.githubusercontent.com/matloff/fasteR/master/inst/images/Nile.png)


> **Your Turn:**  The `hist` function draws 10 bins for this dataset
> in the histogram by default, but you can choose other values, by
> specifying an optional second argument to the function, named
> `breaks`.  E.g.  
> ``` r
> > hist(Nile,breaks=20)
> ```
> 
> would draw the histogram with 20 bins.  Try plotting using several
> different large and small values of the number of bins.
> 
> **Note:**  The `hist` function, as with many R functions, has many
> different options, specifiable via various arguments.  For now, we'll
> just keep things simple, and resist the temptation to explore them
> all.
R has lots of online help, which you can access via `?`.  E.g. typing

``` r
> ?hist
```

will tell you to full story on all the options available for the
**hist** function.  Again, there are far too many for you to digest for
now (most users don't ever find a need for the more esoteric ones), but
it's a vital resource to know.

> **Your Turn:**  Look at the online help for `mean` and `Nile`.

## <a name="vecidxs"> </a> Lesson 3:  Vectors and Indices

Say we want to find the mean river flow after year 1950.  

The above output said that the `Nile` series starts in 1871.  That
means 1951 will be the 81st year, and the 100th will be 1970.  How do we
designate the 81st through 100th elements in this data?

Individual elements can be accessed using *subscripts* or *indices*
(singular is *index*), which are specified using brackets, e.g. 

``` r
> Nile[2]
[1] 1160
```

for the second element (the output we saw earlier shows that the second
element is indeed 1160).  The value 2 here is the index.

The `c` ("concatenate") function builds a vector, stringing several
numbers together.  E.g. we can get the 2nd, 5th and 6th elements of
**Nile**:

``` r
> Nile[c(2,5,6)]
[1] 1160 1160 1160
```

If we wish to build a vector of *consecutive* numbers, we can use the
"colon" notation:

``` r
> Nile[c(2,3,4)]
[1] 1160  963 1210
> Nile[2:4]
[1] 1160  963 1210
```

As you can see, 2:4 is shorter way to specify the vector c(2,3,4).


So, 81:100 means all the numbers from 81 to 100.  Thus
**Nile[81:100]** specifies the 81st through 100th elements in the `Nile`
vector.

Then to answer the above question on the mean flow during 1951-1971, we
can do

``` r
> mean(Nile[81:100])
[1] 877.05
```

> **NOTE:** Observe how the above reasoning process worked.  We had a
> goal, to find the mean river flow after 1950.  We knew we had some tools
> available to us, namely the `mean` function and R vector indices.  We
> then had to figure out a way to combine these tools in a manner that
> achieves our goal, which we did.  
> 
> This is how use of R works in general.  As you go through this tutorial,
> you'll add more and more to your R "toolbox."  Then for any given goal,
> you'll rummage around in that toolbox, and eventually figure out the
> right set of tools for the goal at hand.  Sometimes this will require
> some patience, but you'll find that the more you do, the more adept you
> become.

If we plan to do more with that time period, we should make a copy of
it:

``` r
> n81100 <- Nile[81:100]
> mean(n81100)
[1] 877.05
> sd(n81100)
[1] 125.5583
```

The function `sd` finds the standard deviation.  

Note that we used R's *assignment operator* here to copy ("assign")
those particular  `Nile` elements to `n81100`.  (In most situations,
you can use `=` instead of `<-`, but why worry about what the exceptions
might be?  They are arcane, so it's easier just to always use `<-`.
And though "keyboard shortcuts" for this are possible, again let's just
stick to the basics for now.)

Note too that though we will speak of the above operation as having
"extracted" the 81st through 100th elements of `Nile`, we have merely
made a copy of those elements.  The original vector `Nile` remains
intact.

> <span style="color:red">Tip:</span>
> We can pretty much choose any name we want; `n81100` just was chosen
> to easily remember this new vector's provenance.  (But names can't
> include spaces, and must start with a letter.)

Note that `n81100` now is a 21-element vector.  Its first element is
now element 81 of `Nile`:

``` r
> n81100[1]
[1] 744
> Nile[81]
[1] 744
```

Keep in mind that although `Nile` and `n81100` now have identical
contents, they are *separate* vectors; if one changes, the other will
not.


> **Your Turn:** Devise and try variants of the above, say finding the
> mean over the years 1945-1960.


Another oft-used function is `length`, which gives the number of
elements in the vector, e.g.

``` r
> length(Nile)
[1] 100
```

Can you guess the value of `length(n81100)`?  Type this expression in
at the `>` prompt to check your answer.

Leave R by typing `q()` or ctrl-d.  (Answer no to saving the workspace.)

### Recap: What have we learned in these first two lessons?

* Starting and existing R.

* Some R functions:  `mean`, `hist`, `length`.

* R vectors, and vector indices.

* Extracting vector subsets.

* Forming vectors, using `c()` and `:`.

Not bad for Lesson 1!  And needless to say, you'll be using all of these
frequently in the subsequent lessons and in your own usage of R.

## <a name="less2"> </a> Lesson 4:  More on Vectors

Continuing along the Nile, say we would like to know in how many years
the level exceeded 1200.  Let's first introduce R's `sum` function:

``` r
> sum(c(5,12,13))
[1] 30
```

Here the `c` function built a vector consisting of
5, 12 and 13.  That vector was then fed into the `sum` function,
returning 5+12+13 = 30.

By the way, the above is our first example of *function composition*,
where the output of one function, `c` here, is fed as input into
another, `sum` in this case.

We can now use this to answer our question on the `Nile` data:

``` r
> sum(Nile > 1200)
[1] 7
```

The river level exceeded 1200 in 7 years.

**But how in the world did that work?**  Bear with me a bit here.  Let's
look at a small example first:

``` r
> x <- c(5,12,13)
> x
[1]  5 12 13
> x > 8
[1] FALSE  TRUE  TRUE
> sum(x > 8)
[1] 2
```

First, notice something odd here, in the expression `x > 8`. Here
**x** is a vector, 3 elements in length, but 8 is just a number.  It
would seem that it's nnonsense to ask whether a vector is greater than a
number; they're different animals.

But R makes them "the same kind" of animal, by extending that number 8
to a 3-element vector 8,8,8.  This is called *recycling*.  This sets up
an element-by-element comparison:  Then, the 5 in `x` is compared to
the first 8, yielding FALSE i.e. 5 is NOT greater than 8.  Then 12 is
compared to the second 8, yielding TRUE, and then the comparison of 13
to the third 8 yields another TRUE.  So, we get the vector
FALSE,TRUE,TRUE.

Fine, but how will `sum` add up some TRUEs and FALSEs?  The
answer is that R, like most computer languages, treats TRUE and FALSE as
1 and 0, respectively.  So we summed the vector (0,1,1), yielding 2.

Getting back to the question of the number of years in which the Nile
flow exceeded 1200, let's look at that expression again:

``` r
> sum(Nile > 1200)
```

Since the vector `Nile` has length 100, that number 1200 will be
recycled into a vector of one hundred copies of 1200.  The `>`
comparison will then yield 100 TRUEs and FALSEs, so summing gives us the
number of TRUEs, exactly what we want.

> **Your Turn:** Try a few other experiments of your choice using `sum`.
> I'd suggest starting with finding the sum of the first 25 elements in
> `Nile`.  You may wish to start with experiments on a small vector, say
> (2,1,1,6,8,5), so you will know that your answers are correct.
> Remember, you'll learn best nonpassively.  Code away!

A question related to *how many* years had a flow above 1200 is *which*
years had that property.  Well, R actually has a `which` function:

``` r
> which(Nile > 1200)
[1]  4  8  9 22 24 25 26
```

So the 4th, 8th, 9th etc. elements in `Nile` had the queried property.
(Note that those were years 1875, 1879 and so on.)

In fact, that gives us another way to get the count of the years with
that trait:

``` r
> which1200 <- which(Nile > 1200)
> which1200
[1]  4  8  9 22 24 25 26
> length(which1200)
[1] 7
```

Of course, as usual, my choice of the variable name `which1200` was
arbirary, just something to help me remember what is stored in that
variable.

R's `length` function does what it says, i.e. finding the length of a
vector.  In our context, that gives us the count of years with flow
above 1200.

And, what were the river flows in those 7 years?

``` r
> which1200 <- which(Nile > 1200)
> Nile[which1200]
[1] 1210 1230 1370 1210 1250 1260 1220
```


Finally, something a little fancier.  We can combine steps above:

``` r
> Nile[Nile > 1200]
[1] 1210 1230 1370 1210 1250 1260 1220
```

We just "eliminated the middle man," `which1200`.  The R interpreter
saw our `Nile > 1200`, and thus generated the corresponding TRUEs and
FALSEs.  The R interpreter then treated those TRUEs and 
FALSEs as subscripts in `Nile`, thus extracting the desired data.

Now, we might add here, "Don't try this at home, kids."  For
beginners, it's really easier and more comfortable to break things into
steps.  Once, you become experienced at R, you may wish to start
skipping steps.  

Less bold is the notion of negative indices, e.g.

``` r
> x <- c(5,12,13,8)
> x[-1]  
[1] 12 13  8
```

Here we are asking for all of `x` *except* for `x[1]`.  Can you
guess what `x[c(-1,-4)]` evaluates to?  Guess first, then try it out.

### Recap:  What have we learned in this lesson?

Here you've refined your skillset for R vectors, learning R's recycling
feature, and two tricks that R users employ for finding counts of things.

Once again, as you progress through this tutorial, you'll see that these
things are used a lot in R.

# fasteR: Fast Lane to Learning R! 

![alt text](https://raw.githubusercontent.com/matloff/prVis/master/data/SwissRoll/SWwithY.png)

## *"Becoming productive in R, as fast as possible"*

### Norm Matloff, Prof. of Computer Science, UC Davis; [my bio](http://heather.cs.ucdavis.edu/matloff.html)

(See notice at the end of this document regarding copyright.)

This site is for those who know nothing of R, and maybe even nothing of
programming, and seek *QUICK, PAINLESS!* entree to the world of R.

* **FAST**:  You'll already be doing good stuff in R -- useful data analysis
-- in your very first lesson.

* **For nonprogrammers:**  If you're comfortable with navigating
the Web and viewing charts, you're fine.  This tutorial is aimed 
at you, not experienced C or Python coders.

* **Motivating:**  Every lesson centers around a *real problem* to be
solved, on *real data*.  The lessons do *not* consist of a few toy
examples, unrelated to the real world.  The material is presented in a
conversational, story-telling manner.

* **Just the basics, no frills or polemics:** 

    - Notably, in the first few lessons, we do NOT use Integrated
      Development Environments (IDEs).  RStudio, ESS etc. are great, but
you shouldn't be burdened with learning R *and* learning an IDE at the
same time, a distraction from the goal of becoming productive in R as
fast as possible.  

     Note that even the excellent course by [R-Ladies
Sydney](https://threadreaderapp.com/thread/1119025557830684673.html),
which does start with RStudio, laments that RStudio can be
**"way too overwhelming."**  

     So, in the initial lessons,  we stick to the R command line, and
focus on data analysis, not tools such as IDEs, which we will cover as
an intermediate-level topic.  (Some readers of this tutorial may already
be using RStudio or an external editor, and the treatment here will
include special instructions for them when needed.)

    - Coverage is mainly limited to base R. So for instance the popular
      but self-described "opinionated" Tidyverse is not treated, partly
due to its controversial nature (I am a
[skeptic](http://github.com/matloff/TidyverseSkeptic)), but again mainly
because it would be an obstacle to your becoming productive in R
quickly. 

    While you can learn a few simple things in Tidy quickly, thinking
you are learning a lot, those things are quite limited in scope, and
Tidy learners often find difficulty in applying R to real world data.
<span style="color:red"> Our tutorial here is aimed at learners whose
goal is to USE the R system productively in their own data analysis.
</span>  

* **Nonpassive approach:**  Passive learning, just watching the screen, is NO
learning.  There will be occasional **Your Turn** sections, in which you the 
learner must devise and try your own variants on what has been presented.
Sometimes the tutorial will be give you some suggestions, but even then,
you should cook up your own variants to try.  <span style="color:red"> 
Remember:  You get out what you put in!</span>  The more actively you
work the **Your Turn** sections, the more powerful you will be as an R
coder.

## Table of Contents

**PART I**
* [Lesson 1: Getting Started](#overview)
* [Lesson 2: First R Steps](#firstr)
* [Lesson 3: Vectors and Indices](#vecidxs)
* [Lesson 4: More on Vectors](#less2)
* [Lesson 5: On to Data Frames!](#less3)
* [Lesson 6: The R Factor Class](#less4)
* [Lesson 7: Extracting Rows/Columns from Data Frames](#extractdf)
* [Lesson 8: More Examples of Extracting Rows, Columns](#moreextract)
* [Lesson 9: The tapply Function](#tapply)
* [Lesson 10: Data Cleaning](#less5)
* [Lesson 11: The R List Class](#less6)
* [Lesson 12: Another Look at the Nile Data](#less7)
* [Lesson 13: Pause to Reflect](#pause1)
* [Lesson 14: Introduction to Base R Graphics ](#less8)
* [Lesson 15: More on Base Graphics ](#less9)
* [Lesson 16: Writing Your Own Functions](#less10)
* [Lesson 17: `For` Loops](#less11)
* [Lesson 18: Functions with Blocks](#ftnbl)
* [Lesson 19: Text Editing and IDes](#edt)
* [Lesson 20: If, Else, Ifelse](#ifelse)
* [Lesson 21: Do Pro Athletes Keep Fit?](#keepfit)
* [Lesson 22: Linear Regression Analysis, I](#linreg1)
* [Lesson 23: S3 Classes](#s3)
* [Lesson 24: Baseball Player Analysis (cont'd.)](#less15)
* [Lesson 25: R Packages, CRAN, Etc.](#cran)

**PART II**
* [Lesson 26: A Pause, Before Going on to Advanced Topics](#advanced)
* [Lesson 27: A First Look at ggplot2](#gg2first)
* [Lesson 28: Should You Use Functional Programming?](#appfam)
* [Lesson 29 Simple Text Processing, I](#txt)
* [Lesson 30: Simple Text Processing, II](#txt1)
* [Lesson 31: Linear Regression Analysis, II](#linreg2)
* [Lesson 32: Working with the R Date Class](#dates)
* [Lesson 33: Tips on R Coding Style and Strategy](#style)
* [Lesson 34: The Logistic Model](#logit)
* [Lesson 35: Files and Directories](#fd)
* [Lesson 36: R `while` Loops](#whl)
* [To Learn More](#forMore)
* [Thanks](#thanks)
* [Appendix: Installing and Using RStudio](#rstudio)


## <a name="overview"> </a> Lesson 1:  Getting Started

For the time being, the main part of this online course will be this
**README.md** file.  It is set up as a potential R package, though, and
I may implement that later.

The color figure at the top of this file was generated by our
[**prVis** package](https://github.com/matloff/prVis/),
run on a famous dataset called *Swiss Roll*.

### Please note again:  

* Nonpassive learning is absolutely key!  So even if the output of an R
  command is shown here, run the command yourself in your R console, by
copy-and-pasting from this document into the R console.  <span
style="color:red">You will get out of this tutorial what you put
in.</span>  

* Similarly, the **Your Turn** sections are absolutely crucial.  Devise
  your own little examples, and try them!  "When in doubt, Try it
out!" is a motto I devised for teaching.  If you are unclear or
curious about something, try it out!  Just devise a little experiment,
and type in the code.  Don't worry -- you won't "break" things.

* <span style="color:red">Tip:</span>  I cannot *teach* you how to
program.  I can merely give you the tools, e.g. R vectors, and some
examples.  For a given desired programming task, then, you must
creatively put these tools together to attain the goal.  Treat it like a
puzzle!  I think you'll find that if you stick with it, you'll find
you're pretty good at it.  After all, we can all work puzzles.

### Starting out:

You'll need to [install
R](https://www.datacamp.com/community/tutorials/installing-R-windows-mac-ubuntu),
from [the R Project site](https://www.r-project.org).  Start up R,
either by clicking an icon or typing `R` in a terminal window.  We are
not requiring RStudio here, but if you already have it, start it; you'll
be typing into the R console, the Console pane.

As noted, this tutorial will be "bare bones."  In particular, there is
no script to type your command for you.  Instead, you will either
copy-and-paste from the text here into the R console, or type them there
by hand.  (Note that the code lines here will all begin with the R
interactive prompt, `>`; that should not be typed.)

This is a Markdown file.  You can read it right there on GitHub, which
has its own Markdown renderer. Or you can download it to your own
machine in Chrome and use the Markdown Reader extension to view it (be
sure to enable Allow Access to File URLs).  

When you end your R session, exit by typing `quit()`.

Good luck!  And if you have any questions, feel free to e-mail me, at
matloff@cs.ucdavis.edu

## <a name="firstr"> </a> Lesson 2: First R Steps

The R command prompt is `>`.  Again, it will be shown here, but you don't type
it.  It is just there in your R window to let you know R is inviting you
to submit a command.  (If you are using RStudio, you'll see it in the
Console pane.) 

So, just type `1+1` then hit Enter.  Sure enough, it prints out 2 (you
were expecting maybe 12108?):

``` r
> 1 + 1
[1] 2
```
But what is that `[1]` here?  It's just a row label.  We'll go into that
later, not needed quite yet.

### Example: Nile River data

R includes a number of built-in datasets, mainly for illustration
purposes.  One of them is **Nile**, 100 years of annual flow data on the
Nile River.

Let's find the mean flow:

``` r
> mean(Nile)
[1] 919.35
```

Here **mean** is an example of an R *function*, and in this case Nile is
an *argument* -- fancy way of saying "input" -- to that function.  That
output, 919.35, is called the *return value* or simply *value*.  The act
of running the function is termed *calling* the function.

Another point to note is that we didn't need to call R's **print**
function.  We could have typed,

``` r
> print(mean(Nile))
```

Function calls in R (and other languages) work "from the inside out."
Here we are asking R to find the mean of the Nile data, then print the
result.

But whenever we are at the R `>` prompt, any expression we type will be
printed out anyway, so there is no need to call **print**.

Since there are only 100 data points here, it's not unwieldy to print
them out.  Again, all we have to do is type `Nile`, no need to call
**print**:

``` r
> Nile
Time Series:
Start = 1871 
End = 1970 
Frequency = 1 
  [1] 1120 1160  963 1210 1160 1160  813 1230 1370 1140  995  935 1110  994 1020
 [16]  960 1180  799  958 1140 1100 1210 1150 1250 1260 1220 1030 1100  774  840
 [31]  874  694  940  833  701  916  692 1020 1050  969  831  726  456  824  702
 [46] 1120 1100  832  764  821  768  845  864  862  698  845  744  796 1040  759
 [61]  781  865  845  944  984  897  822 1010  771  676  649  846  812  742  801
 [76] 1040  860  874  848  890  744  749  838 1050  918  986  797  923  975  815
 [91] 1020  906  901 1170  912  746  919  718  714  740
```

Now you can see how the row labels work.  There are 15 numbers per row
here, so the second row starts with the 16th, indicated by `[16]`.  The
third row starts with the 31st output number, hence the `[31]` and so
on.

Note that a set of numbers such as **Nile** is called a *vector*.

### A first graph

R has great graphics, not only in base R but also in wonderful
user-contributed packages, such as **ggplot2** and **lattice**.  But
we'll stick with base-R graphics for now, and save the more powerful yet
more complex **ggplot2** for a later lesson.

We'll start with a very simple, non-dazzling one, a no-frills histogram:

``` r
> hist(Nile)
```

No return value for the **hist** function (there is one, but it is
seldom used, and we won't go into it here), but it does create the
graph.

![alt text](https://raw.githubusercontent.com/matloff/fasteR/master/inst/images/Nile.png)


> **Your Turn:**  The **hist** function draws 10 bins for this dataset
> in the histogram by default, but you can choose other values, by
> specifying an optional second argument to the function, named
> **breaks**.  E.g.  
> ``` r
> > hist(Nile,breaks=20)
> ```
> 
> would draw the histogram with 20 bins.  Try plotting using several
> different large and small values of the number of bins.
> 
> **Note:**  The **hist** function, as with many R functions, has many
> different options, specifiable via various arguments.  For now, we'll
> just keep things simple, and resist the temptation to explore them
> all.
R has lots of online help, which you can access via `?`.  E.g. typing

``` r
> ?hist
```

will tell you to full story on all the options available for the
**hist** function.  Again, there are far too many for you to digest for
now (most users don't ever find a need for the more esoteric ones), but
it's a vital resource to know.

> **Your Turn:**  Look at the online help for **mean** and **Nile**.

## <a name="vecidxs"> </a> Lesson 3:  Vectors and Indices

Say we want to find the mean river flow after year 1950.  

The above output said that the **Nile** series starts in 1871.  That
means 1951 will be the 81st year, and the 100th will be 1970.  How do we
designate the 81st through 100th elements in this data?

Individual elements can be accessed using *subscripts* or *indices*
(singular is *index*), which are specified using brackets, e.g. 

``` r
> Nile[2]
[1] 1160
```

for the second element (the output we saw earlier shows that the second
element is indeed 1160).  The value 2 here is the index.

The **c** ("concatenate") function builds a vector, stringing several
numbers together.  E.g. we can get the 2nd, 5th and 6th elements of
**Nile**:

``` r
> Nile[c(2,5,6)]
[1] 1160 1160 1160
```

If we wish to build a vector of *consecutive* numbers, we can use the
"colon" notation:

``` r
> Nile[c(2,3,4)]
[1] 1160  963 1210
> Nile[2:4]
[1] 1160  963 1210
```

As you can see, 2:4 is shorter way to specify the vector c(2,3,4).


So, 81:100 means all the numbers from 81 to 100.  Thus
**Nile[81:100]** specifies the 81st through 100th elements in the **Nile**
vector.

Then to answer the above question on the mean flow during 1951-1971, we
can do

``` r
> mean(Nile[81:100])
[1] 877.05
```

> **NOTE:** Observe how the above reasoning process worked.  We had a
> goal, to find the mean river flow after 1950.  We knew we had some tools
> available to us, namely the **mean** function and R vector indices.  We
> then had to figure out a way to combine these tools in a manner that
> achieves our goal, which we did.  
> 
> This is how use of R works in general.  As you go through this tutorial,
> you'll add more and more to your R "toolbox."  Then for any given goal,
> you'll rummage around in that toolbox, and eventually figure out the
> right set of tools for the goal at hand.  Sometimes this will require
> some patience, but you'll find that the more you do, the more adept you
> become.

If we plan to do more with that time period, we should make a copy of
it:

``` r
> n81100 <- Nile[81:100]
> mean(n81100)
[1] 877.05
> sd(n81100)
[1] 125.5583
```

The function **sd** finds the standard deviation.  

Note that we used R's *assignment operator* here to copy ("assign")
those particular  **Nile** elements to **n81100**.  (In most situations,
you can use `=` instead of `<-`, but why worry about what the exceptions
might be?  They are arcane, so it's easier just to always use `<-`.
And though "keyboard shortcuts" for this are possible, again let's just
stick to the basics for now.)

Note too that though we will speak of the above operation as having
"extracted" the 81st through 100th elements of **Nile**, we have merely
made a copy of those elements.  The original vector **Nile** remains
intact.

> <span style="color:red">Tip:</span>
> We can pretty much choose any name we want; "n81100" just was chosen
> to easily remember this new vector's provenance.  (But names can't
> include spaces, and must start with a letter.)

Note that **n81100** now is a 21-element vector.  Its first element is
now element 81 of **Nile**:

``` r
> n81100[1]
[1] 744
> Nile[81]
[1] 744
```

Keep in mind that although **Nile** and **n81100** now have identical
contents, they are *separate* vectors; if one changes, the other will
not.


> **Your Turn:** Devise and try variants of the above, say finding the
> mean over the years 1945-1960.


Another oft-used function is **length**, which gives the number of
elements in the vector, e.g.

``` r
> length(Nile)
[1] 100
```

Can you guess the value of **length(n81100)**?  Type this expression in
at the '>' prompt to check your answer.

Leave R by typing 'q()' or ctrl-d.  (Answer no to saving the workspace.)

### Recap: What have we learned in these first two lessons?

* Starting and existing R.

* Some R functions:  **mean**, **hist**, **length**.

* R vectors, and vector indices.

* Extracting vector subsets.

* Forming vectors, using **c()** and ":".

Not bad for Lesson 1!  And needless to say, you'll be using all of these
frequently in the subsequent lessons and in your own usage of R.

## <a name="less2"> </a> Lesson 4:  More on Vectors

Continuing along the Nile, say we would like to know in how many years
the level exceeded 1200.  Let's first introduce R's **sum** function:

``` r
> sum(c(5,12,13))
[1] 30
```

Here the ***c*** function built a vector consisting of
5, 12 and 13.  That vector was then fed into the **sum** function,
returning 5+12+13 = 30.

By the way, the above is our first example of *function composition*,
where the output of one function, ***c*** here, is fed as input into
another, **sum** in this case.

We can now use this to answer our question on the **Nile** data:

``` r
> sum(Nile > 1200)
[1] 7
```

The river level exceeded 1200 in 7 years.

**But how in the world did that work?**  Bear with me a bit here.  Let's
look at a small example first:

``` r
> x <- c(5,12,13)
> x
[1]  5 12 13
> x > 8
[1] FALSE  TRUE  TRUE
> sum(x > 8)
[1] 2
```

First, notice something odd here, in the expression **x > 8**. Here
**x** is a vector, 3 elements in length, but 8 is just a number.  It
would seem that it's nnonsense to ask whether a vector is greater than a
number; they're different animals.

But R makes them "the same kind" of animal, by extending that number 8
to a 3-element vector 8,8,8.  This is called *recycling*.  This sets up
an element-by-element comparison:  Then, the 5 in **x** is compared to
the first 8, yielding FALSE i.e. 5 is NOT greater than 8.  Then 12 is
compared to the second 8, yielding TRUE, and then the comparison of 13
to the third 8 yields another TRUE.  So, we get the vector
FALSE,TRUE,TRUE.

Fine, but how will **sum** add up some TRUEs and FALSEs?  The
answer is that R, like most computer languages, treats TRUE and FALSE as
1 and 0, respectively.  So we summed the vector (0,1,1), yielding 2.

Getting back to the question of the number of years in which the Nile
flow exceeded 1200, let's look at that expression again:

``` r
> sum(Nile > 1200)
```

Since the vector **Nile** has length 100, that number 1200 will be
recycled into a vector of one hundred copies of 1200.  The '>'
comparison will then yield 100 TRUEs and FALSEs, so summing gives us the
number of TRUEs, exactly what we want.

> **Your Turn:** Try a few other experiments of your choice using **sum**.
> I'd suggest starting with finding the sum of the first 25 elements in
> **Nile**.  You may wish to start with experiments on a small vector, say
> (2,1,1,6,8,5), so you will know that your answers are correct.
> Remember, you'll learn best nonpassively.  Code away!

A question related to *how many* years had a flow above 1200 is *which*
years had that property.  Well, R actually has a **which** function:

``` r
> which(Nile > 1200)
[1]  4  8  9 22 24 25 26
```

So the 4th, 8th, 9th etc. elements in **Nile** had the queried property.
(Note that those were years 1875, 1879 and so on.)

In fact, that gives us another way to get the count of the years with
that trait:

``` r
> which1200 <- which(Nile > 1200)
> which1200
[1]  4  8  9 22 24 25 26
> length(which1200)
[1] 7
```

Of course, as usual, my choice of the variable name "which1200" was
arbirary, just something to help me remember what is stored in that
variable.

R's **length** function does what it says, i.e. finding the length of a
vector.  In our context, that gives us the count of years with flow
above 1200.

And, what were the river flows in those 7 years?

``` r
> which1200 <- which(Nile > 1200)
> Nile[which1200]
[1] 1210 1230 1370 1210 1250 1260 1220
```


Finally, something a little fancier.  We can combine steps above:

``` r
> Nile[Nile > 1200]
[1] 1210 1230 1370 1210 1250 1260 1220
```

We just "eliminated the middle man," **which1200**.  The R interpreter
saw our "Nile > 1200", and thus generated the corresponding TRUEs and
FALSEs.  The R interpreter then treated those TRUEs and 
FALSEs as subscripts in **Nile**, thus extracting the desired data.

Now, we might add here, "Don't try this at home, kids."  For
beginners, it's really easier and more comfortable to break things into
steps.  Once, you become experienced at R, you may wish to start
skipping steps.  

Less bold is the notion of negative indices, e.g.

``` r
> x <- c(5,12,13,8)
> x[-1]  
[1] 12 13  8
```

Here we are asking for all of **x** *except* for **x[1]**.  Can you
guess what **x[c(-1,-4)]** evaluates to?  Guess first, then try it out.

### Recap:  What have we learned in this lesson?

Here you've refined your skillset for R vectors, learning R's recycling
feature, and two tricks that R users employ for finding counts of things.

Once again, as you progress through this tutorial, you'll see that these
things are used a lot in R.
