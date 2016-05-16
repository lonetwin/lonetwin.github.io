Auto-install missing python modules
===================================

I just learned about a neat little python feature introduced in python 3.3 that
lets you hook into python's default ``import`` machinery. First a demo:

|demo|

Ok, so how's that done ? Well, there are 2 parts to it. Firstly creating the
import hook. This is exploiting the new ``importlib`` feature for registering a
`MetaPathFinder`_ class:

|implemetation|

The standard lib documentation is very detailed in explaining the *how* of this
mechanism but if you'd like to understand the why and explore other
reasons/benefits of being able to hook into the import mechanism you should take
some time to read the related PEPs.




The second part to this ensuring that it's loaded into your environment. The has
been done in the demo defining the hook above in the `PYTHONSTARTUP`_ file.

If you liked this neat little trick and are interested in other such useful
hacks, do check out my `custom python startup`_. Comments and suggestion are always
appreciated.


.. _MetaPathFinder: https://docs.python.org/3/library/importlib.html#importlib.abc.MetaPathFinder
.. _PYTHONSTARTUP: https://docs.python.org/2/using/cmdline.html#envvar-PYTHONSTARTUP
.. _custom python startup: https://gist.github.com/lonetwin/5902720

.. |demo| raw:: html

    <script type="text/javascript" src="https://asciinema.org/a/c7ijc2luvvqksxcn69dip0g92.js" id="asciicast-c7ijc2luvvqksxcn69dip0g92" async></script>

.. |implemetation| raw:: html

    <script src="https://gist.github.com/lonetwin/b97e7b35634f7229773dece3735cfb58.js"></script>

.. author:: default
.. categories:: none
.. tags:: none
.. comments::
