=========================
 Generate your changelog
=========================

|ci| |release| |badge| |coverage|

|pre| |reuse| |cov| |pylint|

|tag| |license| |python| |contributors|


**Use your commit log as the data for a nicely formatted and configurable changelog file**


This updated fork of gitchangelog is currently tested on Python 3.7+ on
Linux, Macos, and Windows (Python 2.7 support has been removed).

.. note:: The updated version of gitchangelog works best with the updated
          pystache version `available here`_  (as well as on pypi now).
          If pip fails to install pystache from Pypi, you can install it
          using the full github URL of the wheel or sdist on the GH release
          page; check the `new upstream first`_, otherwise the newest test
          release is here::

            pip install https://github.com/VCTLabs/pystache/releases/download/v0.6.2/pystache-0.6.2.tar.gz

          Please file a github issue here if you encounter any problems.

.. _available here: https://github.com/VCTLabs/pystache
.. _new upstream first: https://github.com/PennyDreadfulMTG/pystache


Features
========

- fully driven by a config file that can be tailored with your changelog
  policies. (see for example the `reference configuration file`_)
- filter out commits/tags based on regexp matching
- refactor commit summary, or commit body on the fly with replace regexp
- classify commit message into sections (ie: New, Fix, Changes...)
- any output format supported thanks to templating, you can even choose
  your own preferred template engine (mako, mustache, full python ...).
- support your merge or rebase workflows and complicated git histories
- support full or incremental changelog generation to match your needs.
- support easy access to `trailers key values`_ (if you use them)
- support of multi-authors for one commit through ``Co-Authored-By`` `trailers key values`_
- now available as a `github action`_ for use in release workflows
- default github release action Markdown config and ``get-rcpath`` script
  to find it (see the `gitchangelog.rc.github.release file`_)

.. _github action: https://github.com/sarnold/gitchangelog-action
.. _gitchangelog.rc.github.release file: https://github.com/sarnold/gitchangelog/blob/master/src/gitchangelog/gitchangelog.rc.github.release
.. _trailers key values: https://git.wiki.kernel.org/index.php/CommitMessageConventions


Requirements
============

``gitchangelog`` is compatible with Python 3.6 and higher on
Linux/BSD/MacOSX and Windows (the CI tests run on everything except BSD).

Please submit an issue if you encounter incompatibilities.


Installation
============


full package
------------

The updated gitchangelog is *not* published on PyPI, thus use one of the
following to install the latest gitchangelog on any platform::

  $ pip install https://github.com/sarnold/gitchangelog/releases/download/3.1.0/gitchangelog-3.1.0-py3-none-any.whl

or use this command to install from sdist::

  $ pip install https://github.com/sarnold/gitchangelog/releases/download/3.0.10/gitchangelog-3.0.10.tar.gz

The full package provides the ``gitchangelog.py`` executable as well as:

- a `reference configuration file`_ that provides system wide defaults for
  all values, and a `github.release file`_ for use in CI scripts
- some example templates in the ``mustache`` and ``mako`` templating engine language.
  Ideal to bootstrap your variations.


from source
-----------

If you'd rather work from the source repository, it supports the common
idiom to install it on your system in a virtual env::

  $ python3 -m venv env
  $ source env/bin/activate
  $ pip install -e .[test]
  $ pytest -v .
  $ deactivate

The alternative to python venv is the ``tox`` test driver.  If you have it
installed already, use the following commands to run the test environments
from the gitchangelog source directory.

Use a pip dev install; this can be a convenient way to work on the source
version::

  $ tox -e dev

To run tests using default system Python::

  $ tox -e py

To run pylint::

  $ tox -e lint


Sample
======

The default output is ReSTructured text, so it should be readable in ASCII.

Here is a small sample of the ``gitchangelog`` changelog at work.

Current ``git log`` output so you can get an idea of the log history::

  d7f3f2b (tag: 2.4.0) new: add optional positional argument ``REVLIST`` to allow incremental changelog output (fixes #26)
  16987b5 new: dev: use now ``argparse`` for command line parsing.
  8654238 new: doc: added full use case to remove sectionning and reminder in reference file. (fixes #21) !minor
  e9759c2 (tag: 2.3.0) fix: pkg: coverage would complain about not being able to read config file.
  55b0a17 fix: nasty hidden bug that would break python3 (fixes #27)
  dc279a0 fix: pkg: added missing markdown template in ``data_files``. (fixes #35)
  fc5ce46 (tag: 2.2.1) fix: pkg: ``data_files`` where inconsistently placed depending on way of install. (fixes #34)
  adbd14d fix: doc: ``ìnclude_merge`` options was wrongly typed in sample config files (reported by @tuukkamustonen, fixed #29).
  32e77a2 fix: doc: updated doc to reflec that there are no support of windows for now. (fixes #28)
  b2b154b fix: pkg: update package.
  4560798 fix: dev: removed obsolete code. !minor
  ba79b40 chg: doc: rephrasing and minor changes !minor
  c13d758 fix: remove commit's meta-information footer from changelog output. (fixes #25)

And here is the ``gitchangelog`` output::

  2.4.0 (2015-11-10)
  ------------------

  New
  ~~~
  - Add optional positional argument ``REVLIST`` to allow incremental
    changelog output (fixes #26) [Valentin Lab]

    See use cases documentations for more information.
  - Use now ``argparse`` for command line parsing. [Valentin Lab]

    This is to prepare introduction of more complex command parsing
    required by incremental changelog generation for instance.


  2.3.0 (2015-09-25)
  ------------------

  Fixes
  ~~~~~
  - Nasty hidden bug that would break python3 (fixes #27) [Valentin Lab]

    Actually this bug was revealed by python3 random hashes (thanks to
    @rschoon for the hint) and could be reproduced on python2.7 with ``-R``
    mode.

    The ``git show`` command actually will behave differently if given a tag
    reference and print random unexpected information before using the
    format string. This would prefix a lot of mess to the first field being
    asked in the format string.

    And this first field is dependent on the internal order of a dict, and
    this order is not important as such, and so nothing was done on this
    part.

    On python2.7, somehow, it would always be the same order that revealed
    to have no consequence (probably one of the rare field not used in
    current changelogs).

    Python3 or Python2.7 -R would shuffle this order and then trigger the
    error whenever this prefix would be appended to actually important
    fields that went into some further processing (as casted to int for
    the timestamp for instance).


  2.2.1 (2015-06-09)
  ------------------

  Fixes
  ~~~~~
  - Fix: doc: ``ìnclude_merge`` options was wrongly typed in sample config
    files (reported by @tuukkamustonen, fixed #29). [Valentin Lab]
  - Updated doc to reflec that there are no support of windows for now.
    (fixes #28) [Valentin Lab]

    Actually windows will fail on ``subprocess`` call. (see #28)
  - Remove commit's meta-information footer from changelog output. (fixes
    #25) [Valentin Lab]

    Some various tools (thinking of Gerrit) might leave some
    meta-information in the footer of your commit message's body that you do
    not want to be repeated in your changelog. So all values in the footer
    are removed (This concerns ``Change-Id``, ``Acked-by``, ``CC``,
    ``Signed-off-by``, ``Bug`` ... and any other value).

And the rendered full result is directly used to generate the HTML webpage of
the `changelog of the PyPI page`_.


Usage
=====

The `reference configuration file`_ is delivered within the ``gitchangelog``
package and is used to provide defaults to settings. If you didn't
install the package and used the standalone file, then chances are that
``gitchangelog`` can't access these defaults values. This is not a problem
as long as you provided all the required values in your config file.

The recommended location for ``gitchangelog`` config file is the root
of the current git repository with the name ``.gitchangelog.rc``.
However you could put it elsewhere, and here are the locations checked
(first match will prevail):

- in the path given thanks to the environment variable
  ``GITCHANGELOG_CONFIG_FILENAME``
- in the path stored in git config's entry ``gitchangelog.rc-path`` (which
  could be stored in system location or per repository)
- (RECOMMENDED) in the root of the current git repository with the name
  ``.gitchangelog.rc``

Then, you'll be able to call ``gitchangelog`` in a GIT repository and it'll
print changelog on its standard output.


Configuration file format
-------------------------

The `reference configuration file`_ is quite heavily commented and is quite
simple.  You should be able to use it as required.

.. _reference configuration file: https://github.com/sarnold/gitchangelog/blob/master/src/gitchangelog/gitchangelog.rc.reference
.. _github.release file: https://github.com/sarnold/gitchangelog/blob/master/src/gitchangelog/gitchangelog.rc.github.release

The changelog of gitchangelog is generated with itself and with the reference
configuration file. You'll see the output in the `changelog of the PyPI page`_.

.. _changelog of the PyPI page: http://pypi.python.org/pypi/gitchangelog


Output Engines
--------------

At the end of the configuration file, you'll notice a variable called
``output_engine``. By default, it's set to ``rest_py``, which is the
legacy python engine to produce the ``ReSTructured Text`` output format
that is shown in above samples. If this engine fits your needs, you
won't need to fiddle with this option.

To render the template, ``gitchangelog`` will generate a data structure that
will then be rendered thanks to the output engine. This should help you get
the exact output that you need.

As people might have different needs and knowledge, a templating
system using ``mustache`` is available. ``mustache`` templates are
provided to render both ``ReSTructured Text`` or ``markdown`` formats. If
you know ``mustache`` templating, then you could easily add or modify
these existing templates.

A ``mako`` templating engine is also provided. You'll find also a ``mako``
template producing the same ``ReSTructured Text`` output than the legacy one.
It's provided for reference and/or further tweak if you would rather use `mako`_
templates.


Mustache
~~~~~~~~

The ``mustache``  output engine uses `mustache templates`_.

The `mustache`_ templates are powered via `pystache`_ the python
implementation of the `mustache`_ specifications. So `mustache`_ output engine
will only be available if you have `pystache`_ module available in your python
environment.

There are `mustache templates`_ bundled with the default installation
of gitchangelog. These can be called by providing a simple label to the
``mustache(..)`` output_engine, for instance (in your ``.gitchangelog.rc``)::

  output_engine = mustache("markdown")

Or you could provide your own mustache template by specifying an
absolute path (or a relative one, starting from the git toplevel of
your project by default, or if set, the
``git config gitchangelog.template-path``
location) to your template file, for instance::

  output_engine = mustache(".gitchangelog.tpl")

And feel free to copy the bundled templates to use them as bases for
your own variations. In the source code, these are located in
``src/gitchangelog/templates/mustache`` directory, once installed they
are in ``templates/mustache`` directory starting from where your
``gitchangelog.py`` was installed.


.. _mustache: http://mustache.github.io
.. _pystache: https://pypi.python.org/pypi/pystache
.. _mustache templates: http://mustache.github.io/mustache.5.html


Mako
~~~~

The ``makotemplate`` output engine templates for ``gitchangelog`` are
powered via `mako`_ python templating system. So `mako`_ output engine
will only be available if you have `mako`_ module available in your
python environment.

There are mako_ templates bundled with the default installation of
gitchangelog. These can be called by providing a simple label to the
``makotemplate(..)`` output_engine, for instance (in your ``.gitchangelog.rc``)::

  output_engine = makotemplate("markdown")

Or you could provide your own mako template by specifying an absolute
path (or a relative one, starting from the git toplevel of your project
by default, or if set, the ``git config gitchangelog.template-path``
location) to your template file, for instance::

  output_engine = makotemplate(".gitchangelog.tpl")

And feel free to copy the bundled templates to use them as bases for
your own variations. In the source code, these are located in
``src/gitchangelog/templates/mako`` directory, once installed they
are in ``templates/mako`` directory starting from where your
``gitchangelog.py`` was installed.

.. _mako: http://www.makotemplates.org


Changelog data tree
~~~~~~~~~~~~~~~~~~~

This is a sample of the current data structure sent to output engines::

  {'title': 'Changelog',
   'versions': [{'label': '%%version%% (unreleased)',
                 'date': None,
                 'tag': None
                 'sections': [{'label': 'Changes',
                               'commits': [{'author': 'John doe',
                                            'body': '',
                                            'subject': 'Adding some extra values.'},
                                           {'author': 'John Doe',
                                            'body': '',
                                            'subject': 'Some more changes'}]},
                              {'label': 'Other',
                               'commits': [{'author': 'Jim Foo',
                                            'body': '',
                                            'subject': 'classic modification'},
                                           {'author': 'Jane Done',
                                            'body': '',
                                            'subject': 'Adding some stuff to do.'}]}]},
                {'label': 'v0.2.5 (2013-08-06)',
                 'date': '2013-08-06',
                 'tag': 'v0.2.5'
                 'sections': [{'commits': [{'author': 'John Doe',
                                            'body': '',
                                            'subject': 'Updating Changelog installation.'}],
                               'label': 'Changes'}]}]}


Merged branches history support
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Commit attribution to a specific version could be tricky. Suppose you have
this typical merge tree (spot the tags!)::

  * new: something  (HEAD, tag: 0.2, develop)
  *   Merge tag '0.1.1' into develop
  |\
  | * fix: out-of-band hotfix  (tag: 0.1.1)
  * | chg: continued development
  |/
  * fix: something  (tag: 0.1)
  * first commit  (tag: 0.0.1, master)

Here's a minimal draft of gitchangelog to show how commit are
attributed to versions::

  0.2
    * new: something.
    * Merge tag '0.1.1' into develop.
    * chg: continued development.

  0.1.1
    * fix: out-of-band hotfix.

  0.1
    * fix: something.


.. note:: You can automatically remove all merge commits from gitchangelog
          output by using ``include_merge = False`` in the ``.gitchangelog.rc``
          file.


Use cases
=========


No sectioning
-------------

If you want to remove sectioning but keep anything else, you should
probably use::

  section_regexps = [
      ('', None)
  ]

  subject_process = (strip | ucfirst | final_dot)

This will disable sectioning and won't remove the prefixes
used for sectioning from the commit's summary.


Incremental changelog
---------------------

Also known as partial changelog generation, this feature allows to
generate only a subpart of your changelog, and combined with
configurable publishing actions, you can insert the result inside
an existing changelog. Usually this makes sense:

- When wanting to switch to ``gitchangelog``, or change your
  conventions:

  - part of your history is not following conventions.
  - you have a previous CHANGELOG you want to blend in.

- You'd rather commit changes to your changelog file for each release:

  - For performance reason, you can then generate changelog only for
    the new commit(s) and save the result.
  - Because you want to be able to edit it to make some minor
    edition if needed.


Generating partial changelog is as simple as ``gitchangelog REVLIST``.
Examples follow::

  ## will output only tags between 0.0.2 (excluded) and 0.0.3 (included)
  gitchangelog 0.0.2..0.0.3

  ## will output only tags since 0.0.3 (excluded)
  gitchangelog ^0.0.3 HEAD

  ## will output all tags up to 0.0.3 (included)
  gitchangelog 0.0.3


Additionally, ``gitchangelog`` can figure out automatically which
revision is the last for you (with some little help). This is done by
specifying the ``revs`` config option. This config file option will be
used as if specified on the command line.

Here is an example that fits the current changelog format::

  revs = [
      Caret(
          FileFirstRegexMatch(
              "CHANGELOG.rst",
              r"(?P<rev>[0-9]+\.[0-9]+(\.[0-9]+))\s+\([0-9]+-[0-9]{2}-[0-9]{2}\)\n--+\n")),
  ]

This will look into the file ``CHANGELOG.rst`` for the first match of
the given regex and return the match of the ``rev`` regex sub-pattern
it as a string. The ``Caret`` function will simply prefix the given
string with a ``^``. As a consequence, this code will prevent
recreating any previously generated changelog section (more information
about the `REVLIST syntax`_ from ``git rev-list`` arguments.)

.. _REVLIST syntax: https://git-scm.com/docs/git-rev-list#_description

Note that the data structure provided to the template will set the
``title`` to ``None`` if you provided no REVLIST through command-line
or the config file (or if the revlist was equivalently set to
``["HEAD", ]``).  This a good way to make your template detect it is
in "incremental mode".

By default, this will only output to standard output the new sections
of your changelog, you might want to insert it directly in your existing
changelog. This is where ``publish`` parameters will help you. By default
it is set to ``stdout``, and you might want to set it to::

  publish = FileInsertAtFirstRegexMatch(
      "CHANGELOG.rst",
      r'/(?P<rev>[0-9]+\.[0-9]+(\.[0-9]+)?)\s+\([0-9]+-[0-9]{2}-[0-9]{2}\)\n--+\n/',
      idx=lambda m: m.start(1)
  )

The full recipe could be::

  OUTPUT_FILE = "CHANGELOG.rst"
  INSERT_POINT = r"\b(?P<rev>[0-9]+\.[0-9]+)\s+\([0-9]+-[0-9]{2}-[0-9]{2}\)\n--+\n"
  revs = [
          Caret(FileFirstRegexMatch(OUTPUT_FILE, INSERT_POINT)),
          "HEAD"
  ]

  action = FileInsertAtFirstRegexMatch(
      OUTPUT_FILE, INSERT_POINT,
      idx=lambda m: m.start(1)
  )


Alternatively, you can use this other recipe, using ``FileRegexSubst``, that has
the added advantage of being able to update the unreleased part if you had it already
generated and need a re-fresh because you added new commits or amended some commits::

  OUTPUT_FILE = "CHANGELOG.rst"
  INSERT_POINT_REGEX = r'''(?isxu)
  ^
  (
    \s*Changelog\s*(\n|\r\n|\r)        ## ``Changelog`` line
    ==+\s*(\n|\r\n|\r){2}              ## ``=========`` rest underline
  )

  (                     ## Match all between changelog and release rev
      (
        (?!
           (?<=(\n|\r))                ## look back for newline
           %(rev)s                     ## revision
           \s+
           \([0-9]+-[0-9]{2}-[0-9]{2}\)(\n|\r\n|\r)   ## date
             --+(\n|\r\n|\r)                          ## ``---`` underline
        )
        .
      )*
  )

  (?P<rev>%(rev)s)
  ''' % {'rev': r"[0-9]+\.[0-9]+(\.[0-9]+)?"}

  revs = [
      Caret(FileFirstRegexMatch(OUTPUT_FILE, INSERT_POINT_REGEX)),
      "HEAD"
  ]

  publish = FileRegexSubst(OUTPUT_FILE, INSERT_POINT_REGEX, r"\1\o\g<rev>")


As a second example, here is the same recipe for mustache markdown format::

  OUTPUT_FILE = "CHANGELOG.rst"
  INSERT_POINT_REGEX = r'''(?isxu)
  ^
  (
    \s*\#\s+Changelog\s*(\n|\r\n|\r)        ## ``Changelog`` line
  )

  (                     ## Match all between changelog and release rev
      (
        (?!
           (?<=(\n|\r))                ## look back for newline
           \#\#\s+%(rev)s                     ## revision
           \s+
           \([0-9]+-[0-9]{2}-[0-9]{2}\)(\n|\r\n|\r)   ## date
        )
        .
      )*
  )

  (?P<tail>\#\#\s+(?P<rev>%(rev)s))
  ''' % {'rev': r"[0-9]+\.[0-9]+(\.[0-9]+)?"}

  revs = [
      Caret(FileFirstRegexMatch(OUTPUT_FILE, INSERT_POINT_REGEX)),
      "HEAD"
  ]

  publish = FileRegexSubst(OUTPUT_FILE, INSERT_POINT_REGEX, r"\1\o\n\g<tail>")


Making Changes & Contributing
=============================

We use the `gitchangelog-action`_ to generate our GitHub Release page, as
well as the gitchangelog commit message prefix "tag" modifiers to help
it categorize/filter commits for a tidier changelog. Please use the
appropriate ACTION modifiers in any Pull Requests.

.. _gitchangelog-action: https://github.com/sarnold/gitchangelog-action

This repo is also pre-commit_ enabled for various linting and format
checks.  The checks run automatically on commit and will fail the
commit (if not clean) with some checks performing simple file corrections.

If other checks fail on commit, the failure display should explain the error
types and line numbers. Note you must fix any fatal errors for the
commit to succeed; some errors should be fixed automatically (use
``git status`` and ``git diff`` to review any changes).

See the following pages for more information on using gitchangelog and pre-commit.

.. inclusion-marker-1

* generate-changelog_
* pre-commit-config_
* pre-commit-usage_

.. _generate-changelog:  docs/source/dev/generate-changelog.rst
.. _pre-commit-config: docs/source/dev/pre-commit-config.rst
.. _pre-commit-usage: docs/source/dev/pre-commit-usage.rst
.. inclusion-marker-2

You will need to install pre-commit before contributing any changes;
installing it using your system's package manager is recommended,
otherwise install with pip into your usual virtual environment using
something like::

  $ sudo emerge pre-commit  --or--
  $ pip install pre-commit

then install it into the repo you just cloned::

  $ git clone https://github.com/sarnold/gitchangelog
  $ cd gitchangelog/
  $ pre-commit install

It's usually a good idea to update the hooks to the latest version::

    pre-commit autoupdate


SBOM and license info
=====================

Licensed under the `BSD License`_ as documented in ``REUSE.toml``.

This project is now compliant with the REUSE Specification Version 3.3,
and the corresponding license information for all files can be found in
the ``REUSE.toml`` configuration file with license text(s) in the
``LICENSES/`` folder.

Related metadata can be (re)generated with the following tools and
command examples.

* reuse-tool_ - REUSE_ compliance linting and sdist (source files) SBOM generation
* sbom4python_ - generate SBOM with full dependency chain

Commands
--------

Use tox to create the environment and run the lint command::

  $ tox -e reuse                      # to run reuse lint   --or--
  $ tox -e reuse -- spdx > sbom.txt   # generate sdist files sbom

Note you can pass any of the other reuse commands after the ``--`` above.

Use the above environment to generate the full SBOM in text format::

  $ source .tox/reuse/bin/activate
  $ sbom4python --system --use-pip -o <file_name>.txt

Be patient; the last command above may take several minutes. See the
doc links above for more detailed information on the tools and
specifications.

.. _pre-commit: https://pre-commit.com/index.html
.. _reuse-tool: https://github.com/fsfe/reuse-tool
.. _REUSE: https://reuse.software/spec-3.3/
.. _sbom4python: https://github.com/anthonyharrison/sbom4python
.. _BSD License: LICENSES/


.. |ci| image:: https://github.com/sarnold/gitchangelog/actions/workflows/ci.yml/badge.svg
    :target: https://github.com/sarnold/gitchangelog/actions/workflows/ci.yml
    :alt: CI Status

.. |coverage| image:: https://github.com/sarnold/gitchangelog/actions/workflows/coverage.yml/badge.svg
    :target: https://github.com/sarnold/gitchangelog/actions/workflows/coverage.yml
    :alt: Coverage workflow

.. |badge| image:: https://github.com/sarnold/gitchangelog/actions/workflows/pylint.yml/badge.svg
    :target: https://github.com/sarnold/gitchangelog/actions/workflows/pylint.yml
    :alt: Pylint Status

.. |release| image:: https://github.com/sarnold/gitchangelog/actions/workflows/release.yml/badge.svg
    :target: https://github.com/sarnold/gitchangelog/actions/workflows/release.yml
    :alt: Release Status

.. |cov| image:: https://raw.githubusercontent.com/sarnold/gitchangelog/badges/master/test-coverage.svg
    :target: https://github.com/sarnold/gitchangelog/
    :alt: Test coverage

.. |pylint| image:: https://raw.githubusercontent.com/sarnold/gitchangelog/badges/master/pylint-score.svg
    :target: https://github.com/sarnold/gitchangelog/actions/workflows/pylint.yml
    :alt: Pylint score

.. |reuse| image:: https://api.reuse.software/badge/git.fsfe.org/reuse/api
    :target: https://api.reuse.software/info/git.fsfe.org/reuse/api
    :alt: REUSE status

.. |license| image:: https://img.shields.io/pypi/l/gitchangelog?color=blue
    :target: https://github.com/sarnold/gitchangelog/blob/master/LICENSE
    :alt: License

.. |tag| image:: https://img.shields.io/github/v/tag/sarnold/gitchangelog?color=blue&include_prereleases&label=latest%20release
    :target: https://github.com/sarnold/gitchangelog/releases
    :alt: GitHub tag (latest SemVer, including pre-release)

.. |python| image:: https://img.shields.io/badge/python-3.6+-blue.svg
    :target: https://www.python.org/downloads/
    :alt: Python

.. |pre| image:: https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white
   :target: https://github.com/pre-commit/pre-commit
   :alt: pre-commit

.. |contributors| image:: https://img.shields.io/github/contributors/sarnold/gitchangelog
   :target: https://github.com/sarnold/gitchangelog
   :alt: Contributors
