
# How to Make the Most of Your Computer Science/Data Science/Statistics Major

## What no one else will tell you. :-)

## Prof. Norm Matloff, University of California, Davis CS Dept.

![alt text](https://raw.githubusercontent.com/matloff/prVis/master/data/SwissRoll/SWwithY.png)

## Purpose of this document

Computer Science, Data Science and Statistics (CSDSStat) are
fascinating, ever-growing fields.  It's an exciting
time to be in tech -- but how to make the most of this opportunity?  

We'll cover a variety topics, so let's get started!  

## My background

Different people may have different views on the topics here.  Thus
we must begin with my explaining the background affecting my views.

My PhD is in pure math, and I am a founder of both the CS and Stat
Departments at my university.  My current research areas are machine
learning, fair data analysis, and missing values.  

I've been fortunate to be recognized for my work.  I've won the
university-wide Distinguished Teaching Award, Outstanding Adviser Award,
and Distinguished Public Service Award.  My book, *Statistical
Regression and Classification: from Linear Models to Machine Learning*
was the 2017 recipient of the Ziegal Award, given by the statistics 
journal *Technometrics*.  

I am quite active in the R programming language.  I've published a
number of books that use R, and have written various packages on CRAN
and GitHub.  I've served as Editor-in-Chief of the *R Journal* and
the *Journal of Statistical Software*.  I've written a rather popular 
[R tutorial](http://github.com/matloff/fasteR), and a
[criticism of the R tidyverse](http://github.com/matloff/TidyverseSkeptic)
that many have found cogent.


My time in industry was long, long ago, but I have always kept close
ties to the real world.  I frequently interact with people in Silicon
Valley, and keep close tabs on the job market. Syndicated columnist
Joyce Lain Kennedy features my advice on career issues in her books,
*Resumes for Dummies*, *Job Hunting for Dummies* and *Cover Letters for
Dummies*. 

Of course, the material here represents my own views only, and does not
imply endorsement by my university or department.  And again, others may
have different opinions.

## What do CSDSStat graduates do?

* Many in CS--and in fact many from DS, Stat and virtually any tech
  field--become software engineers.  Note that most software engineers
are young, say below age 35.  There is considerable age discrimination
in all tech fields, but much more so in this particular one.

* Data scientists:  Analyzing, graphing and predicting data.  Wide
  variation here, in terms of job responsibilities, possible need for an
advanced degree and so on.  If for instance the job title involves
"machine learning," and advanced degree is almost certainly required.

* Database analysts:  A big bank would quickly go out of business if its
  software and hardware couldn't keep up with the huge daily olume of checks,
credit card transaction and so on.  Making the database speedy is thus
of huge importance.

* Data security specialists:  How to foil the Bad Guys?  This requires a
  finely intricate knowledge of computer systems, especially computer
networks.

## The high value of computer systems knowledge

If you *any* kind of work with computers, the deeper your knowledge of
computer systems, the better.  Some examples:

* I was recently using an R package that at one point gave me an error
  message, "Non-numeric data encountered."  It seemed odd, because the
variable in question *was* numeric, wage income in dollars.  R is
written in the C language (as is Python), which distinguishes between
integers like 3 and real numbers such as 8.1, so I immediately realized
and solved the problem.  Advice:  If you are in DS/Stat, take C/C++ even
if not required.

* R and Python are *interpreted* languages.  In some cases, this can
  make them run slowly.  With Big Data, execution speed may be
imperative, and the solution may be to write code that it mainly
R/Python but also partly C/C++.  Again, skill in the latter is
important.

* Illustrative story:  Once the daughter of family friends of ours
  received a scholarship to study the Chinese language in China. (She
was not Asian, by the way.)  She returned home with lots of pictures on
her laptop.  Unfortunately, her little sister dropped the machine, and
it would not reboot.  The pictures were lost!  But with my knowledge of
OS--boot up, file systems and so on--I was able to recover most of the
pics.

* Large software applications, e.g. the bank database example above,
generally place a premium on speed.  This in turn requires a firm
understanding of high level hardware and low-level software.

* Computer security requires a keen knowledge of operating systems,
  especially network operation.  For a great read and a glimpse into how
hackers exploit holes in the OS, read *The Cuckoo's Nest*, by Cliff
Stoll.  There's also a bit at the very beginning of the film *A Social
Network*, the story of the founding of Facebook.

If you are required to take a course in assembly language, do NOT treat
this as "just another language."  *It is your window into 
computer systems*, a way to learn abouy computer architecture and OS..

By the time you graduate, you who are in CS, and ideally those of you in
DSStat, should be able to answer questions like
(these are just examples):

* How does an OS boot up?

* How can a computer have several processes going at once?  (And are
  there really running simultaneously?)

* How does a file system work?

Most or all of these matters will NOT be covered in typical OS and
computer architecture classes.  You should have enough curiosity to
think about them and track down the answers if you can't figure them out
yourself.

## Windows vs. Mac vs. Linux

Windows is a great OS for non-tech people. But most CSDSStat
people and their employers use some form of Unix,
either a Mac or Linux.  Use your Unix system for *all of your daily
computer work* -- not just coding, but also e-mail, essay writing,
Website building and so on.

If you want to retain Windows for video games or whatever, that's fine
-- set up your system to dual-boot the two systems.  In fact, the
setting up of this will itself be a valuable learning experience.  Don't
use the Linux subsystem in Windows.  It lacks many capabilities.

## Coursework is not enough

**THIS IS AN EXTREMELY IMPORTANT POINT.**

Sadly, typical courses won't give you the true, practical insight you
need to effectively do CSDSStat work.  Examples:

* As noted above, it's good to understand OS, e.g. in terms of how a
  machine boots up.  Yet this almost certainly will not be covered in an
OS class, let alone in computational courses in DSStat.

* In a DSStat course, you will learn about stat methods that assume a
  normal/Gaussian distribution.  But you almost certainly won't be
taught that no such assumptions exist in real life (e.g. no one is 100
feet tall or has a negative height), or whether the assumptions
matter.

The remedy:  Learn nonpassively.  Question what you learn.  Fill in the
gaps, first by trying to reason them out, then by consulting with your
instructors, then finally--of course--by going to the Internet.

## The impact of grade inflation

These days, many instructors not only give absurdly high grades--at my
university, I've seen a number of courses in which 1/3 of the students
get A+ grades!--but also are very undemanding.  Their lectures lack
depth, and avoid the more difficult concepts.  Exams are simply
warmed-over homework problems.

You should seek out the professors who will challenge you, but if you
get some easy ones, don't fool yourself into thinking that that A/A+
grade means you have good knowledge of the subject matter.  Again, go
back what is expected of you, as explained above.

## Textbooks

Following up on the above point:

Most professors choose their textbooks very carefully, but naively and
wrongly assume the students actually read them.

Read the textbook!  Read it for deep understanding.  If you see a page
consisting only of prose, with no code, no equations, and no figures, do
not conclude there is no content!  On the contrary, *that page may be one
of the most important ones in the book*.  You actually should spend extra
time on such pages.

Pause often for thought.  Your reading will likely cause you to have
lots of questions.  Indeed, if you have no questions, you probably have not
been reading critically.  Think hard in trying to answer the questions
yourself, and ask your professor or TAs about the rest.

## "No pain, no gain"

What does this old saying mean, in the CSDSStat context?  It does NOT
mean "Work yourself to death."  It does NOT mean "Take 5 courses per
semester/quarter," and so on.

What it does mean is to give your work long, hard thought.  Can't see
how to even get started on your programming assignment?  Don't
immediately seek your TA!  Think more and more on it.  Let it percolate
in your mind.  Go for a long walk to mull it over.  **This is where you
become a good programmer.**  If you don't go through this, you likely
never do well in a coding interview.

It also follows that if the problem statement for your assignment gives
you an outline of the code structure, the instructor is not doing you a
favor.  Try to take courses from professors who challenge you.

The same point holds for mathematical courses, whether in a CS, Math or
Stat Department.

## Avoid taking many courses in your major on a P/NP grading basis

Frankly, this looks bad to a potential employer or graduate admissions
committee.  It suggests that the student put in only minimal work in
those P/NP courses, and even has the connotation that the student is
"gaming the system."

## The field of machine learning is mathematical modeling, not programming

Machine learning (ML) is NOT a branch of software engineering.  Your ML
course will almost certainly have you do some coding, but if you
conclude that ML is about choosing which function to call, and knowing
the functions arguments, you've missed the point entirely.

ML is also not about plugging into formulas.  It is an art, not a
science.  There is no formulaic solution to problems, especially
overfitting.  Professor Yaser Abu-Mostafa of Caltech, a prominent ML
figure, once summed it up: 

> The ability to avoid overfitting is what separates professionals from
> amateurs in ML.

(https://www.youtube.com/watch?v=EQWr3GGCdzw)

My Google query on ``overfitting'' yielded 6,560,000 results!  Again,
careful thought about the subject matter is key.

## Classes to take whether required or not

* Computer networks: The basis for most computer applications today

* Database:  The "information" in "Information Technology"

* Computer security:  If your school doesn't offer one, suggest that
  they do

* Economics:  Affects everything in your life; take a whole year of it
  if you can

* Advanced statistics:  See below

## Get a summer internship

It generally is not easy to get these, but they are highly worth the
effort.  They get you out of the student mental ruts like "Can I get
partial credit?" and "Will this be on the final exam?"  

You're not in school here.  You're part of a team.  If you're writing
code, make sure it is valuable to the employer.  Make doubly sure that
your code WORKS, including on edge cases, and that the code is clear
(see the points above about comments).
  
Be punctual (even if your permanent-position co-workers are not).  Don't
be shy about speaking up in meetings.  Make sure to ask questions about
what you don't understand (though first make your best effort to figure
out the answers on your own).

Your employer hired you in part because they may want to hire you after
you graduate, so this is really like a very extended interview.  Keep
this in mind, but on the other hand, don't let this fact pressure you.
You are there to learn, and hopefully to enjoy.  A post-graduation job
offer might be nice, but treat that as a bonus.

## Learn probability and statistics

The Accreditation Board for Engineering Technology, which accredits
engineering-oriented curricula at most major universities, requires that
students get background in both probability and statistics.  It's so
important that many university CS Departments, including mine, teach
their own in-house prob/stat courses with CS applications.

These fields, especially in the form of machine learning and data
science, are key elements of any computer scientist's intellectual
toolkit.  And beyond your profession, these fields should be integral
parts of any educated person's analytical abilities; they pervade such a
wide variety of the human interprise.

Note that I didn't phrase the above section title as "Take probability
and statistics classes."  Yes, take the courses, but make sure you
really understand what's going on.  Don't just plug into formulas.

And, QUESTION the material.  If your stat instructor teaches you some
procedure requiring a normal (Gaussian) distribution but doesn't discuss
the implications (e.g. that normal distributions don't occur in real
life, though they may be good approximations in some cases), then he/she
is failing in their responsibility to educate you.  The same is true if
they teach you *p-values* without explaining their dangers.  (In a
famous 2016 position statement, the American Statistical Association
discouraged the use of p-values.)

## Develop your speaking and writing skills

I know, you're saying, "Yes, yes, we've been told about this ever since
high school."  But it's even more of a key issue for CS people.

Craig Barrett, former CEO of Intel, once famously remarked, "The
half-life of an engineer is only a few years."  In other words, if say
you begin your career as a software engineer, you will likely find that
after 5-10 years, you are asked to transition into management or some
other "talking job."  Though there are of course exceptions, the odds
are that the further along you are in your career, the less time you
spend doing explicitly technical things, and the more time you spend
talking and writing.  If you've ever visited a company that produces
software, you probably noticed that most of the coders are in their 20s
or early 30s; this is no coincidence.

And though, yes, coursework in writing and speaking helps to some
extent, *you can only grow by working on these things yourself*.  When
you are writing something, ask yourself what you can do to make your
thoughts clearer.  And if you have a fear of speaking out in the group,
overcome it!

If you did not grow up speaking English, don't worry about your accent.
Just work on expressing yourself well.  Engage in campus club or
volunteer activities where you can really grow verbally.

## Don't neglect the social aspect

Success in the real world stems perhaps 20% from technical ability and
80% skill in interpersonal relations.  Don't be a hermit.  Join the CS
Club.  Volunteer to help out in your department's or your university's
annual Open House.  Know what's going on in the outside world.  Read
something other than science fiction or fantasy.

## Possibly engage in undergraduate research

If done well, assisting a professor with her research
can have huge salutatory effects.  But this is only the case if the work
is nontrivial, with the student being encouraged to engage in
independent, creative analysis.  The student typically has up to then
done only narrow, highly structured, "sanitized" work in his coursework.
So, research work, in which student plays a role in not only *solving* a
problem but also *defining* it in the first place, can have a
transformative impact on the student.

On the other hand, if the student is just assigned to do straightforword
coding, say, then the value of research is essentially nil.

## Seeking and interviewing for jobs

Job hunting (including for internships) can be a full-time job in its
own right.  Your campus employment center will help (including via the
job fairs they sponsor on campus), and you can scan the Web.  Use your
social network too!

You should maintain a GitHub repo containing code for your more
important projects.  It's best that they be independent projects, i.e.
not for a class, but the latter type is useful too.  This is your
portfolio, just as an artist has a portfolio of his/her artwork.  It's
possible that you may be asked about these projects in interviews.  Be
prepared to answer design-oriented questions.  Why did you set up your
data structures in a certain way?  What if the goal of the code had been
slightly different?  What would you have to change?

When you have an interview (first on the phone or Zoom, later on-site),
prepare by researchng the nature of the employer.  Practice mock
interviews with friends.  Did you get an A in your Programming Language
course (or Statistical Regression Analysis or whatever)?  Great, but can
you talk about it cogently?  If the job involves coding, again,
practice with friends!  Give each other little coding tasks, which you
try to code on a whiteboard in front of them.  

By the way, during the real interview, don't worry if you don't answer
everything perfectly, e.g. could not fully complete a coding task.  The
interviewers want to see how you think.

And no matter how introverted you are, don't just sit there "like a bump
on a log"!  Speak up!  Venture opinions!  Ask questions!

## Graduate school

"Should I go to grad school?"  This is one of the most common questions
I get from students.

To answer, I tell them an old joke:  A man is walking on a dock and
passes a huge yacht.  He asks the owner how much the yacht costs.  The
owner answers, "If you have to ask, then you can't afford it."  The
point is that, for the most part, you will only gain from grad school if
you really want to do it; if you have to ask whether to pursue
graduate study, then you "can't afford it," in terms of
time and money spent etc.  This is true both for a Master's degree and a
PhD.

Master's degree quality varies tremendously from school to school.  If
you get a CS Bachelor's degree from a research-oriented
university, and later get a Master's from a non-research school, you may
find that the latter's Master's curriculum is similar to, maybe even
inferior to, your undergrad material.

On the other hand, one should not necessarily talk about whether the CS
graduate program at University X is "good."  It depends on the research
area.  X may be very good in, say, computer security but weak in machine
learning.  So take your field(s) of interest into account.

In applying to grad school, note that letters of recommendation tend to
be crucial, even more than grades and test scores.  See
[these sample letters](http://heather.cs.ucdavis.edu/~matloff/LettersOfRec.html)

Once you get to grad school, you'll notice immediately that the climate
has changed from the undergrad world.  Your classmates will now consist
of people who have a genuine intellectual curiosity about CS, which may
not have been the case for many of your undergrad friends.  In class,
you are now expected to be much more active, questioning and
independent-thinking.
