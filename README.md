
# fasterR: Fast Lane to Learning R!

The site is for those who know nothing of R or even of programming, and
seek a quick, painless entree to the world of R.

* *FAST*:  You'll already be doing good stuff in R on your first try.

* No prerequisites:  If you're comfortable with navigating the Web,
you're fine.  This tutorial is aimed at you, not experienced
C or Python coders.

* No polemics:  You won't be made to feel guilty for not using an
instructor's favorite R tool or style, including mine. :-)

* No frills:  E.g. no IDEs; RStudio, ESS etc. are great, but you
shouldn't be burdened with learning R *and* an IDE at the same time.

* Nonpassive approach:  Passive learning, just watching the screen is NO
learning.  There will be occasional Your Turn sections, in which you the 
learner must try your own variants on what has been presented.
Sometimes the tutorial will be give you some suggestions, but even then,
you should cook up your own variants to try.

## Contribute your own lesson!

If there is any interest, it would be fun for some useRs out there to
contribute lessons here.  Both experts and novices are encouraged!
(Please check with me.  Note the rules above.  I will be the arbiter here.)

## Getting started:

You'll need to install R, from [the R Project site](https://www.r-project.org).
Start up R, either by clicking an icon or typing 'R' in a terminal
window.  

As noted, this tutorial will be "bare bones."  In particular, there is
no script to type your command for you.  Instead, you will either
copy-and-paste from the test here, or type by hand.

## First R steps:

The R command prompt is '>'.  It will be shown here, but you don't type
it.

So, just type '1+1'.  Sure enough, it prints out 2:

```R
> 1 + 1
[1] 2
```
But what is that '[1]' here?  It's just a row label.  We'll go into that
later, not needed now.

R includes a number of built-in datasets, mainly for illustration
purposes.  One of them is **Nile**, 100 years of annual flow data on the
Nile River.

Let's find the mean flow:

``` R
> mean(Nile)
[1] 919.35
```

Here **mean** is an example of an R *function*, and in this case Mile is
an *argument* -- fancy way of saying "input" -- to that function.  That
output, 919.35, is called the **return value** or simply *value*.

Since there are only 100 data points here, it's not unwieldy to print
them out:

``` R
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

Now you can see how the row labels work.  There are 15 numbers per row,
here, so the second row starts with the 16th, indicated by '[16]'.

R has great graphics, not only in base R but also in user-contributed
packages, such as **ggplot2** and **lattice**.  But will start with a
very simple, non-dazzling one, a no-frills histogram:

``` r
> hist(Nile)
```

No return value for the **hist** function, but it does create the graph
(not shown here; it should be on your screen).

<blockquote>


**Your Turn:**  The **hist** function draws 10 bins in the histogram by
default, but you can choose other values.  E.g.

``` r
> hist(Nile,breaks=20)
```

would draw the histogram with 20 bins.  Try plotting using
several different large and small values of the number of bins.

</blockquote>

R has lots of online help, which you can access via '?'.  E.g. typing

``` r
> ?hist
```

will tell you to full story on all the options available for the
**hist** function.  Note, there are far too many for you to digest for
now, but it's a vital resource to know.

<blockquote>


**Your Turn:**  Look at the online help for **mean** and **Nile**.

</blockquote>

Now, one more new thing for this first lesson.  Say we want to find the
mean flow after year 1950.  Since 1971 is the 100th year, 1951 is the 80th.
How do we designate the 80th through 100th elements in the **Nile**
data?

First, note that a set of numbers such as **Nile** is called a *vector*.
Individual elements can be accessed using *subscripts* or *indices*;
e.g. 

``` r
> Nile[2]
[1] 1160
```

The **c** ("concatenate") function strings several numbers together.
E.g. we can get the 2nd, 5th and 6th:

``` r
> Nile[c(2,5,6)]
[1] 1160 1160 1160
```

And 80:100 means all the numbers from 80:10.  So can do

``` r
> mean(Nile[80:100])
[1] 877.6667
```

<blockquote>

**Your Turn:** Devise and try variants of the above, say finding the
mean over the years 1945-1960.

</blockquote>

Leave R by typing 'q()' or ctrl-d.  (Answer no to saving the workspace.)
