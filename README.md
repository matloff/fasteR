
# fasterR: Fast Lane to Learning R!

![alt text](https://raw.githubusercontent.com/matloff/prVis/master/inst/data/SwissRoll/SWwithY.png)

### Professor of Computer Science, UC Davis
### [my bio](http://heather.cs.ucdavis.edu/matloff.html)

## Overview:

The site is for those who know nothing of R or even of programming, and
seek a quick, painless entree to the world of R.

* *FAST*:  You'll already be doing good stuff -- useful data analysis
--- in R in your very first lesson.

* No prerequisites:  If you're comfortable with navigating the Web,
you're fine.  This tutorial is aimed at you, not experienced
C or Python coders.

* No polemics:  You won't be made to feel guilty for not using an
instructor's favorite R tool or style, including mine. :-)

* No frills:  E.g. no IDEs (Integrated Development Environments);
  RStudio, ESS etc. are great, but you shouldn't be burdened with
learning R *and* an IDE at the same time.  This can come later,
optionally.

* Nonpassive approach:  Passive learning, just watching the screen is NO
learning.  There will be occasional **Your Turn** sections, in which you the 
learner must try your own variants on what has been presented.
Sometimes the tutorial will be give you some suggestions, but even then,
you should cook up your own variants to try.

* Contribute your own lessons!:  Yes, "your name in lights"; see below.

Please note again:  You will just be using R from the command line here.
Most tutorials, say the excellent one by [R-Ladies
Sydney](https://threadreaderapp.com/thread/1119025557830684673.html),
start with RStudio, a very attractive, many-featured IDE.  But even the
R-Ladies tutorial laments that RStudio can be "overwhelming."  Here we
stick to the R command line, and focus on data analysis, not advanced
tools.

## Contribute your own lessons!

If there is any interest, it would be fun for some useRs out there to
contribute lessons here.  Both experts **and novices** are encouraged,
especially the latter!  Maybe do one with a friend.  I'll help you
through the kinks, and your name will be displayed with your contribution.

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

Here **mean** is an example of an R *function*, and in this case Nile is
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
packages, such as **ggplot2** and **lattice**.  But we'll start with a
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
Individual elements can be accessed using *subscripts* or *indices*,
which are specified using brackets, e.g. 

``` r
> Nile[2]
[1] 1160
```

for the second element (which we see above is indeed 1160).

The **c** ("concatenate") function builds a vector, strings several
numbers together.  E.g. we can get the 2nd, 5th and 6th:

``` r
> Nile[c(2,5,6)]
[1] 1160 1160 1160
```

And 80:100 means all the numbers from 80:10.  So can do

``` r
> mean(Nile[80:100])
[1] 877.6667
```

If we plan to do more with that time period, we should make a copy of
it:

``` r
> n80100 <- Nile[80:100]
> mean(n80100)
[1] 877.6667
> sd(n80100)
[1] 122.4117
```

The function **sd** finds the standard deviation.  Note that we used R's
*assignment operator* here to copy the **Nile** element to **n80100**.

We can pretty much choose any name we want; "n80100" just was chosen
to easily remember this new vectors's provenance.  (But names can't
include spaces, and must start with a letter.)

Note that **n80100** now is a 21-element vector.  Its first element is
now element 80 of **Nile**:

``` r
> n80100[1]
[1] 890
> Nile[80]
[1] 890
```

<blockquote>

**Your Turn:** Devise and try variants of the above, say finding the
mean over the years 1945-1960.

</blockquote>

Leave R by typing 'q()' or ctrl-d.  (Answer no to saving the workspace.)

## Lesson 2:  More on vectors

Continuing along the Nile, say we would like to know in how many years
the level exceeded 1200.  Let's first introduce R's **sum** function:

``` r
> sum(c(5,12,13))
[1] 30
```

Here the ***c*** function built a vector consisting of 5, 12 and 13, and
that vector was then fed into the **sum** function, returning 5+12+13 = 30.

By the way, the above is our first example of *function composition*,
where the output of one function, ***c*** here, is fed as input into
another, **sum** in this case.

We can now use this to answer our question on the **Nile** data:

``` r
> sum(Nile > 1200)
[1] 7
```

But how in the world did that work?  Bear with me a bit here.

``` r
> x <- c(5,12,13)
> x > 8
[1] FALSE  TRUE  TRUE
> sum(x > 8)
[1] 2
```

First, that 8 was *recycled* into 3 8s, i.e. the vector (8,8,8), in
order to have the same length as **x**.  Then, the 5 was compared to the
first 8, yielding FALSE i.e. 5 is NOT greater than 8.  Then 12 was
compared to the second 8, then 13 with the third.  So, we got the vector
FALSE,TRUE,TRUE)

Fine, but how will **sum** add up some TRUEs and FALSEs?  The
answer is that R, like most computer languages, treats TRUE and FALSE as
1 and 0, respectively.  So we summed the vector (0,1,1), yielding 2.

<blockquote>

**Your Turn:** Try a few other experiments of your choice using **sum**.
I'd suggest starting with finding the sum of the first 25 elements in
**Nile**.  You may wish to start with experiments on a small vector, say
(2,1,1,6,8,5), so you will know that your answers are correct.
Remember, you'll learn best nonpassively.  Code away!

</blockquote>

## Lesson 3:  On to data frames!

Right after vectors, the next major workhorse of R is the *data frame*.
It's a rectangular table consisting of one row for each data point.

Say we have height, weight and age on each of 100 people.  Our data
frame would have 100 rows and 3 columns.  The entry in, e.g., the second
row and third column would be the age of the second person in our data. 

As our first example, consider the **ToothGrowth** dataset built-in to
R.  Again, you can read about it in the online help (the data turn out
to be on guinea pigs, with orange juice or Vitamin C as growth agents).
Let's take a quick look from the command line.

``` r
> head(ToothGrowth)
   len supp dose
1  4.2   VC  0.5
2 11.5   VC  0.5
3  7.3   VC  0.5
4  5.8   VC  0.5
5  6.4   VC  0.5
6 10.0   VC  0.5
```

R's **head** function displays (by default) the first 6 rows of the
given dataframe.  We see there are length, supplement and dosage
columns.  

To avoid writing out the long word "ToothGrowth" repeatedly, let's
make a copy.

``` r
> tg <- ToothGrowth
```

How large is the dataset?

``` r
> dim(tg)
[1] 60  3
```

Ah, 60 rows and 3 columns (60 guinea pigs, 3 measurements each).

Dollar signs are used to denote the individual columns.  E.g. we can
print out the mean length; **tg$len** is the tooth length column, so

``` r
> mean(tg$len)
[1] 18.81333
```

Subscripts in data frames are pairs, specifying row and column numbers.
To get the element in row 3, column 1:

``` r
> tg[3,1]
[1] 7.3
```
which matches what we saw above.  Or, use the fact that **tg$len** is a
vector:

``` r
> tg$len[3]
[1] 7.3
```

The element in row 3, column 1 in the *data frame* **tg** is element 3 in
the *vector* *tg$len*.




