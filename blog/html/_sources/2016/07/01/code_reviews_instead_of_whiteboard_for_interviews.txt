Code reviews instead of whiteboard for interviews
=================================================


Of late I've been thinking a lot about interviews. After being part of this
community (or industry if you fancy it) for more than 15 years, I've had my
share of sitting on both sides of the table. A lot has changed in all these
years with the tools we work with as well as the way we approach problems.

However, in all these years not a whole lot has changed in the way we interview
(or approach interviewing). Sure, we have better tools and have questioned
ourselves about the methodology but at some point we all end up defaulting to
focusing on the candidates ability to write good code. This ability though is
just a small part of how we work on a daily basis.

The other day I was reviewing a colleague’s patchset and although the code by
itself was clean and functional, it was the approach that my colleague had
taken which bothered me a bit. So I made my comments and submitted a -1 on the
patchset. As is customary when it is easier to just speak about it than reply
thru’ the tool (we use gerrit), my colleague walked over to my desk and we
spent a good half hour or so discussing the approach. That’s when I got to
wondering why don’t we just do more of this during interviews.


* We can quickly weed out people who can’t write code just by testing their
  ability to comprehend code. If they can’t recognize well known datastuctures
  or algorithms by looking at the code, they probably won’t be able to write it
  either.

* Hearing someone review some piece of code gives invaluable insight into just
  how they think. The colleague I mentioned earlier was new to the company and
  among other things that we spoke about, we seemed to disagree on whether or
  not it is a good idea to introduce new *patterns/paradigms* into existing
  codebase. I am of the opinion that code should appear as though written by a
  single author even if it has been worked on by different people. His was that
  introducing newer patterns improves the quality of the code. While I agreed to
  an extent with him, I would vote against this if it violates the principle of
  least surprise [#]_.

* Hearing someone review some piece of code gives invaluable insight into
  aspects of their personality. Like for instance their sense of ‘code smell’,
  their attitude or towards performance trade-offs in a very real practical
  sense, their ability (/experience) in spotting subtle bugs and just as
  importantly the manner in which they express their opinions.

* You end up treating the candidates as peers instead of making them feel
  *uneasy* or *defensive* by asking questions they probably could answer when
  they had just graduated.

So, with these in mind, I am thinking about a scenario where we could possibly
use some of our more accessible (isolated) code snapshots which have under gone
several revisions during interviews. It might be interesting to see whether we
can get the same comments as the rest of the team had made.

Of course, what I’m advocating is not to do away with approaches that judge
coding ability but to take a more practical/mature approach to interviewing
your peer.

I’m very interested in hearing whether anyone has tried this at their workplace
and what other everyday aspects of work do you suppose we can and should
incorporate into our interviewing process ?


.. [#] Yeah, I know that this apply to UI rather than code, but IMHO, one ought
       to consider fellow developers as *users* of ones code.

*Note*: This originally was written as a quick `medium post`_ with comments
requested at `Hacker News`_

.. _medium post: https://medium.com/@lonetwin/code-reviews-instead-of-whiteboard-for-interviews-e0b66f8db71b#.ifyy5otso
.. _Hacker News: https://news.ycombinator.com/item?id=12018965

.. author:: default
.. categories:: none
.. tags:: interviews
.. comments::
