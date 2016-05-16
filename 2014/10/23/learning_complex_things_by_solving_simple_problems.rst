Learning complex things by solving simple problems
==================================================

Keeping things organized is not one of my strengths and this is evident by
looking at the filesystems on any of the myriad storage devices in my
possession.

The folders and files struggle to maintain a sense of perceivable order and
intent for being where they are and named as they have been. Beyond the lack of
structure and confusing names though, the thing that bothers me the most is the
fact that I seem to over time, collect multiple copied of these blasted
byte-collections for no good reason.

I'm a byte hoarder and worse still, I can't seem to organize my hoard.

Although, I do try. Sometimes. Like for instance when I wrote `finddup`_ [#]_

Now, although `finddup` started off as being just a tool to allow me to regain
some space (and order, in the bit-chaos) on my harddisk, it has turned out to
be a wonderful journey of discovery into the concepts of `Locality-sensitive hashing`_
and `Soundex`_ algorithms. All this because I was dissatisfied with the way I
implemented the ``fuzzy`` option.

I won't attempt to explain these concepts here in this post, since firstly, I
am not sure I understand them well enough yet and secondly since there already
are so many good resources that explain these. However, I do hope to update the
``fuzzy`` matching option of `finddup` to make use of LSH. That way, I can
implement it and in the process understand it as well.

What I do what to emphasize here tho' is this -- trying to solve simple
problems can teach you a great many new things if you challenge yourself to
find better or even different ways to solve those problems.

Remember that future me !


.. author:: default
.. categories:: none
.. tags:: none
.. comments::

.. _finddup: https://github.com/lonetwin/finddup
.. [#] Re-wrote actually, not sure how many times I've written the simple
   filename matching and md5sum matching versions of this.
.. _Locality-sensitive hashing: http://en.wikipedia.org/wiki/Locality-sensitive_hashing
.. _Soundex: http://en.wikipedia.org/wiki/Soundex
