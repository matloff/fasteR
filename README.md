
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

For the time being, the main part of this online course will be this
**README.md** file.  It is set up as a potential R package, though, and
I may implement that later.

## Please note again:  

* You will just be using R from the command line here.  Most tutorials,
say the excellent one by [R-Ladies
Sydney](https://threadreaderapp.com/thread/1119025557830684673.html),
start with RStudio, a very attractive, many-featured IDE.  But even the
R-Ladies tutorial laments that RStudio can be "overwhelming."  Here we
stick to the R command line, and focus on data analysis, not advanced
tools.

* The **Your Turn** sections are absolutely crucial.  Devise your own
little examples, and try them out!

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
(In most situations, you can use "=" instead of "<-", but why worry
about what the exceptions might be?  They are arcane, so it's easier
just to always Use "<-".)

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
the *vector* **tg$len**.

<blockquote>

**Your Turn:** Devise your own little examples with the **ToothGrowth**
data.  For instance, write code that finds the number of cases in which
the length was less than 16.  Also, try some examples with another
built-in R dataset, **faithful**.  This one involves the Old Faithful
geyser in Yellowstone National Park in the US.  The first column gives
duration of the eruption, and the second has the waiting time since the
last eruption.

</blockquote>

## Lesson 4:  Data cleaning

Most real-world data is "dirty," i.e. filled with errors.  The famous
[New York taxi trip
dataset](https://data.cityofnewyork.us/Transportation/2017-Yellow-Taxi-Trip-Data/biws-g3hs),
for instance, has one trip destination whose lattitude and longitude
place it in Antartica! The presence of such data on one's statistical
analysis can be anywhere from mild to disabling.  Let's see below how one
might ferret out bad data.  And along the way, we'll cover several new R
concepts.

We'll use the famous Pima Diabetes dataset.  Various versions exist, but
we'll use the one that is included in **faraday**, an R package compiled
by Julian Faraway, author of several popular books on statistical
regression analysis in R.

I've placed the data file, **Pima.csv**, on
[my Web site](http://heather.cs.ucdavis.edu/FasteR/data/Pima.csv). Here
is how you can read it into R:

``` r
> pima <- read.csv('http://heather.cs.ucdavis.edu/FasteR/data/Pima.csv',header=TRUE)
```

The dataset is in a CSV ("comma-separated values") file.  Here we read
it, and assigned the resulting data frame to a variable we chose to name
**pima**.

Note that second argument, 'header=TRUE'.  A header in a file, if one
exists, states what names the columns in the data frame are to have.  If
the file doesn't have one, set **header** to FALSE.  You can always add
names to your data frame later (future lesson).

It's always good to take a quick look at a new data frame:

``` r
> head(pima)
  pregnant glucose diastolic triceps insulin  bmi diabetes age test
1        6     148        72      35       0 33.6    0.627  50    1
2        1      85        66      29       0 26.6    0.351  31    0
3        8     183        64       0       0 23.3    0.672  32    1
4        1      89        66      23      94 28.1    0.167  21    0
5        0     137        40      35     168 43.1    2.288  33    1
6        5     116        74       0       0 25.6    0.201  30    0
> dim(pima)
[1] 768   9
```

768 people in the study, 9 variables measured on each.

Since this is a study of diabetes, let's take a look at the glucose
variable.

``` r
> table(pima$glucose)

  0  44  56  57  61  62  65  67  68  71  72  73  74  75  76  77  78  79  80  81 
  5   1   1   2   1   1   1   1   3   4   1   3   4   2   2   2   4   3   6   6 
 82  83  84  85  86  87  88  89  90  91  92  93  94  95  96  97  98  99 100 101 
  3   6  10   7   3   7   9   6  11   9   9   7   7  13   8   9   3  17  17   9 
102 103 104 105 106 107 108 109 110 111 112 113 114 115 116 117 118 119 120 121 
 13   9   6  13  14  11  13  12   6  14  13   5  11  10   7  11   6  11  11   6 
122 123 124 125 126 127 128 129 130 131 132 133 134 135 136 137 138 139 140 141 
 12   9  11  14   9   5  11  14   7   5   5   5   6   4   8   8   5   8   5   5 
142 143 144 145 146 147 148 149 150 151 152 153 154 155 156 157 158 159 160 161 
  5   6   7   5   9   7   4   1   3   6   4   2   6   5   3   2   8   2   1   3 
162 163 164 165 166 167 168 169 170 171 172 173 174 175 176 177 178 179 180 181 
  6   3   3   4   3   3   4   1   2   3   1   6   2   2   2   1   1   5   5   5 
182 183 184 186 187 188 189 190 191 193 194 195 196 197 198 199 
  1   3   3   1   4   2   4   1   1   2   3   2   3   4   1   1 
```

Uh, oh!  5 women in the study had glucose level 0.  Presumably this is
not physiologically possible.

Let's consider a version of the glucose data that excludes these 0s.

``` r
> pg <- pima$glucose
> pg1 <- pg[pg > 0]
> length(pg1)
[1] 763
```

As before, the expression "pg > 0" creates a vector of TRUEs and FALSEs.
The filtering "pg[pg > 0]" will only pick up the TRUE cases, and sure
enough, we see that **pg1** has only 763 cases, as opposed to the
original 768.

Did removing the 0s make much difference?  Turns out it doesn't:

``` r
> mean(pg)
[1] 120.8945
> mean(pg1)
[1] 121.6868
```

But still, these things can in fact have  major impact in many
statistical analyses.

R has a special code for missing values, NA, for situations like this.
Rather than removing the 0s, it's better to recode them as NAs.  Let's
do this, back in the original dataset so we keep all the variables in
one object:

``` r
> pima$glucose[pima$glucose == 0] <- NA
```

Note the double-equal sign!  If we wish to test whether, say, **a** and
**b** are equal, the expression must be "a == b", not "a = b"; the
latter would do "a <- b".

As a check, let's verify that we now have 5 NAs in the glucose variable:

``` r
> sum(is.na(pima$glucose))
[1] 5
```

Here the built-in R function **is.na** will return a vector of TRUEs and
FALSEs.  Recall that those values can always be treated as 1s and 0s.
Thus we got our count, 5.

Let's also check that the mean comes out right:

``` r
> mean(pima$glucose)
[1] NA
```

What went wrong?  By default, the **mean** function will *not* skip over
NA values; thus the mean was reported as NA too.  But we can instruct
the function to skip the NAs:

``` r
> mean(pima$glucose,na.rm=TRUE)
[1] 121.6868
```

<blockquote>

**Your Turn:**  Determine which other columns in **pima** have
suspcious 0s, and replace them with NA values.

</blockquote>
