Working with multiple python packages in "editable" mode
========================================================

Like a lot of pythonistas, I prefer doing my python development in `virtual
environments`_. Furthermore, I prefer `virtualenvwrapper`_ to manage my virtual
environments. This ensures isolation of the environment and the packages that
the project depends upon and this works extremely well for self contained
projects.

Once in the while though, I need to create a dependency to a package that is
being worked on in a different virtualenv. In other words, I need to
simultaneously work in *editable* mode on 2 different packages from 2 different
virtualenvs.

One of the ways to do this *cleanly* is to ``pip install`` the dependency into
your virtualenv. However, each time you update the code for the dependency
package, you also need to ``pip upgrade`` the package in your virtualenv. This
becomes a pain if your dependency is a library that is shared across more than
one virtualenv.

The other way to solve this is to also install the dependency in an *editable*
mode, using ``pip install -e``. However, with this approach again, you might end
up having to constantly keep the source repo for the dependency package synced
across all the virtualenvs that use it.

In both cases, you have multiple copies of the dependency lying around in your
virtualenvs. How do you optimize this so that:

a. There is just one copy of the dependency package.
b. All virtualenvs get the latest changes in the dependency package without
   having to do anything special.
c. Does not interfere or break the isolation of the virtualenv setup (ie: both,
   the dependency package and the dependent package are still in their own
   virtualenv)

A good clean way I recently discovered is using `add2virtualenv`_

Perhaps a session capture is much better to explain this than loads of
descriptive text::

    [steve@lonelap ~]$ mkvirtualenv dependency
    New python executable in dependency/bin/python2
    Also creating executable in dependency/bin/python
    Installing setuptools, pip...done.
    [steve@lonelap (dependency)]$ echo 'print("Everyone needs me")' > dependency.py
    [steve@lonelap (dependency)]$ deactivate

    [steve@lonelap ~]$ mkvirtualenv project
    New python executable in project/bin/python2
    Also creating executable in project/bin/python
    Installing setuptools, pip...done.
    [steve@lonelap (project)]$ echo "import dependency" > my_project.py
    [steve@lonelap (project)]$ echo "print('I am using dependency from %s' % dependency.__file__)" >> my_project.py
    [steve@lonelap (project)]$ python my_project.py
    Traceback (most recent call last):
      File "my_project.py", line 1, in <module>
    	import dependency
    ImportError: No module named dependency
    [steve@lonelap (project)]$ add2virtualenv ~/src/venvs/dependency
    [steve@lonelap (project)]$ python my_project.py
    Everyone needs me
    I am using dependency from /home/steve/src/venvs/dependency/dependency.pyc
    [steve@lonelap (project)]$ deactivate

    [steve@lonelap ~]$ workon dependency
    [steve@lonelap (dependency)]$ echo "print('Dependency is now updated')" >> dependency.py
    [steve@lonelap (dependency)]$ deactivate

    [steve@lonelap ~]$ workon project
    [steve@lonelap (project)]$ python my_project.py
    Everyone needs me
    Dependency is now updated
    I am using dependency from /home/steve/src/venvs/dependency/dependency.py
    [steve@lonelap (project)]$



.. _virtual environments: http://docs.python-guide.org/en/latest/dev/virtualenvs/
.. _virtualenvwrapper: https://virtualenvwrapper.readthedocs.io/en/latest/index.html
.. _add2virtualenv: https://virtualenvwrapper.readthedocs.io/en/latest/command_ref.html#add2virtualenv





.. author:: default
.. categories:: python
.. tags:: pip, virtualenvwrapper
.. comments::
