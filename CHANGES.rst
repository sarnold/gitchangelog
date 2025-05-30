Changelog
=========


3.2.2 (2024-03-18)
------------------

Changes
~~~~~~~
- Expand doc sources, revert short changes file, switch theme. [Stephen
  L Arnold]

  * reorganize sections and use readme include file
  * use PyData Sphinx theme, remove sidebar, get version back
- Try partial changelog with only sections, add CHANGES.rst to docs.
  [Stephen L Arnold]

  * add sphinx_git extension and display HEAD commit data as a
    workaround for missing the version in the sidebar
- Cleanup extra license file, replace with symlink. [Stephen L Arnold]


3.2.1 (2025-03-31)
------------------

New
~~~
- Add pre-commit config, cleanup bits, update CHANGES.rst. [Stephen L
  Arnold]

  * move old change data to HISTORY.rst, start CHANGES.rst after v3.0.4
- Add reuse tool, use reuse cfg and LICENSES dir for compliance.
  [Stephen Arnold]

Changes
~~~~~~~
- Update .gitchangelog.rc tag filter, regenerate changelog. [Stephen L
  Arnold]

  * update the readme with a later log example
- Test coverage bits and windows in CI. [Stephen L Arnold]

  * remove bash-ism from check command to be more platform-agnostic
- Update changelog bits with new regex and full changes cmd. [Stephen L
  Arnold]

  * (re)generate CHANGES.rst file
- Add tox shared env extension, update readme and project files.
  [Stephen L Arnold]
- Update workflow action and python version, add base automation.
  [Stephen L Arnold]
- Misc config updates, flags arg in publish callable needs discussion.
  [Stephen Arnold]

Fixes
~~~~~
- Add missing workflow trigger. [Stephen L Arnold]

  * callable workflow files require the ``workflow_call`` key


3.2.0 (2024-03-18)
------------------

Changes
~~~~~~~
- Remove merges from .gitchangelog.rc and regenerate file. [Steve
  Arnold]

  * add 'changes' command to to tox file

Fixes
~~~~~
- Use tz-aware timestamps for author/tagger dates iin Python 3.12.
  [Steve Arnold]

  * silence deprecation warnings and stop breaking tests
- Cleanup package configs, readme, and changes for package QA. [Steve
  Arnold]

  * add ignore regex to .gitchangelog.rc to remove ci/dependabot commits
  * update changes and tox files again
- Complete version cleanup, migrate to setuptools_scm, buff some lint.
  [Steve Arnold]

  * cleanup old version references, bump pystache to latest Pypi release
  * revert matrix artifacts in ci, upload a single build instance
  * cleanup/migrate flake8 configs and tox file
- Try a matrix name for v4 workflow artifacts. [Steve Arnold]
- Replace deprecated pkg_resources and update workflows. [Steve Arnold]

Other
~~~~~
- Update CHANGES.rst for release. [Steve Arnold]


3.1.2 (2022-10-30)
------------------

Changes
~~~~~~~
- Update changes file for new release. [Stephen L Arnold]

Fixes
~~~~~
- Restore missing percentage in coverage display, update changes.
  [Stephen L Arnold]
- Add missing import for exception handler, use correct version.
  [Stephen L Arnold]
- Upgrade workflow actions, add org membercheck to coverage. [Stephen L
  Arnold]

  * removes a bunch of GH Check annotations/warnings


3.1.1 (2022-10-03)
------------------

New
~~~
- Enable pep8speaks, add config fi;e. [Stephen L Arnold]

Changes
~~~~~~~
- Add readme note about no more Python 2.7 support. [Stephen L Arnold]
- Extend Popen timeout and wrap in try/except block. [Stephen L Arnold]

  * 15 sec is not long enough on some GH ci runners
  * follow subprocess docs and kill/drain process output

Fixes
~~~~~
- Update packaging and pytest env, restore missing bits. [Stephen L
  Arnold]

  * add Popen kill to git invocation, remove ResourceWarnings hidden
    by default pytest cfg
  * make sure pytest does not filter any warnings
  * make sure version attribute matches new version imports
  * retore missing CHANGES file and workflow env var

Other
~~~~~
- Update changes file for release. [Stephen L Arnold]


3.1.0 (2022-10-01)
------------------

New
~~~
- Add gh workflow to run sphinx doc build and deploy to gh-pages.
  [Stephen L Arnold]

Changes
~~~~~~~
- Update readme and both release and local rc files. [Stephen L Arnold]

  * update readme with new upstream pystache pointer, cleanup
  * release default needs v tag prefix in tag_regexps


3.0.10 (2022-09-26)
-------------------

New
~~~
- Add basic sphinx docs sources, update packaging, cleanup docstrings.
  [Stephen L Arnold]

  * make a docs build using readme and sphinx-apidoc module
  * remove section headers from docstrings (not allowed)
  * update packaging deps and manifest/tox files

Changes
~~~~~~~
- Add post-release docs build to release workflow. [Stephen L Arnold]
- Update readme, reformat license file, cleanup more lint. [Stephen L
  Arnold]
- Add coverage and pylint ci workflows. [Stephen L Arnold]
- Modernize/refactor source, packaging, tests. [Stephen L Arnold]

  * remove more py2 cruft/old cfg files, refactor problematic tests
  * update package deps to point to latest pystache sdist
  * workaround for upstream pystache version and pypi install issues
  * update ci workflows and status

Fixes
~~~~~
- Add more tool configs, cleanup some lint, update tox file. [Stephen L
  Arnold]
- Use namespace paths for data files, remove symlink. [Stephen L Arnold]

  * src layout needs full namespace paths in setup.cfg
  * single file install is no longer an option, so remove the symlink
    and readme reference to it

Other
~~~~~
- Update readme/install notes for latest pystache install issues.
  [Stephen L Arnold]


3.0.9 (2022-04-13)
------------------

Fixes
~~~~~
- Cleanup some readme typos. [Stephen L Arnold]

Other
~~~~~
- Add python 3.10 to workflow matrix/tox (no more nose, should be Green)
  [Stephen L Arnold]
- Replace nose with pytest, update tool configs. [Stephen L Arnold]
- Bump version for patch release, need clean deps for gitchangelog-
  action. [Stephen L Arnold]
- Switch pystache dep back to pypi, cleanup tox file. [Stephen L Arnold]


3.0.8 (2021-11-15)
------------------

Fixes
~~~~~
- Make pystache dependency concrete until pypi is updated. [Stephen L
  Arnold]

  * update tox commands, add requirements file
- Correct typo in utility doc-string. [Stephen L Arnold]

Other
~~~~~
- Bump version for patch release, cleanup help msg. [Stephen L Arnold]


3.0.7 (2021-02-28)
------------------

Changes
~~~~~~~
- Add/adjust some options in codecov.yml. [Stephen L Arnold]

Fixes
~~~~~
- Setup.py deps and install instructions (#2) [Steve Arnold]

  * allow last pypi version of pystache in install_requires
  * doc: update readme install instructions
  * dev: update pragmas, add missing one for win32/py2

Other
~~~~~
- Bump version for release. [Stephen L Arnold]


3.0.6 (2021-02-27)
------------------

Changes
~~~~~~~
- Switch repo paths in readme. [Stephen L Arnold]

Fixes
~~~~~
- Update default release cfg, cleanup typos, go back to master. [Stephen
  L Arnold]

Other
~~~~~
- Bump version for release, update readme. [Stephen L Arnold]
- Get-rcpath and CI/config updates (#1) [Steve Arnold]

  * test: add more steps for tests/check
  * test: update tox gh-matrix and flesh out coverage bits
  * refactor get-rcpath to use pkg_resources instead of gh env path
  * update release workflow to use new gcl action


3.0.5 (2021-01-19)
------------------

New
~~~
- Ci: shiny version bump for packaging and add some new wheels. [Stephen
  L Arnold]

Changes
~~~~~~~
- Note about gitchangelog.rc.github.release config, cleanup. [Stephen L
  Arnold]
- Ci: add wheel check and disable appveyor ci. [Stephen L Arnold]
- Ci: export shell var PYTHONIOENCODING to utf-8. [Stephen L Arnold]

Fixes
~~~~~
- Ci: use pep517 builder to get the right wheel install deps. [Stephen L
  Arnold]
- Ci: add the nose traverse-namespace setting for windows py38+ [Stephen
  L Arnold]

Other
~~~~~
- Bump version in readme example and drop appveyor badge. [Stephen L
  Arnold]


3.0.4-4 (2020-12-09)
--------------------

New
~~~
- Re-package get-rcpath helper script, install to bin directory.
  [Stephen L Arnold]

Other
~~~~~
- Bump version 3.0.4-3 -> 3.0.4-4 for release. [Stephen L Arnold]
- README.rst: add github action feature bullet. [Stephen L Arnold]


3.0.4-3 (2020-12-08)
--------------------

New
~~~
- Add default compact reference config for github release action.
  [Stephen L Arnold]

Other
~~~~~
- Bump version and fix README tab whitespace error. [Stephen L Arnold]
- Bug: revert windows-latest due to env code page errors. [Stephen L
  Arnold]
- Try msys install latest git to workaround the encoding test issue.
  [Stephen L Arnold]
- Restore pager cfg, leave one more artifact, then revert windows-
  latest. [Stephen L Arnold]
- One more try with msys2 mingw64 env and git pkg (may not like tox)
  [Stephen L Arnold]
- Restore the git config checkout cmds for crlf/i18n. [Stephen L Arnold]
- Fix checkout step (needs commit data) and shorten install list.
  [Stephen L Arnold]
- Try msys install latest git to workaround the encoding test issue.
  [Stephen L Arnold]


3.0.4-2 (2020-11-20)
--------------------
- Bump version 3.0.4-1 -> 3.0.4-2 and update readme. [Stephen L Arnold]
- Go back to github windows disabled. [Stephen L Arnold]
- Try the input git config setting just for kicks. [Stephen L Arnold]
- Disable windows until the github windows image has more git. [Stephen
  L Arnold]
- Recover "working" config (except the windows test runner/encoding
  errors) [Stephen L Arnold]
- Keep git history for install check, update README.rst. [Stephen L
  Arnold]
- Allow py27 for a while longer, update tox and setup.cfg. [Stephen L
  Arnold]
- Modify CI commands to follow the appveyor pattern. [Stephen L Arnold]
- Migrate CI to github actions. [Stephen L Arnold]


3.0.4-1 (2020-11-08)
--------------------
- Bump version 3.0.4 -> 3.0.4-1 and fix badge url. [Stephen L Arnold]
- Restore pystache support for testing, use github url for source.
  [Stephen L Arnold]
- Appveyor.yml: cleanup pip install a bit. [Stephen L Arnold]
- Use .travis scripts (borrowed from simplejson) to sort out osx
  pythons. [Stephen L Arnold]
- Update INSTALL snippet and add osx to travis build matrix. [Stephen L
  Arnold]
- README.rst: sync content, add venv/tox sections, remove mustache refs.
  [Stephen L Arnold]
- Dev: add/document test and ci deps as extras_require, cleanup old
  files. [Stephen L Arnold]
- Dev: add support for 'pN' version suffix for post/patch releases.
  [Stephen L Arnold]
- README.rst: revert appveyor tokenized url for github project path.
  [Stephen L Arnold]
- README.rst: switch to tokenized appveyor badge url. [Stephen L Arnold]
- README.rst: restore appveyor badge, replace with org in github urls.
  [Stephen L Arnold]
- Appveyor.yml: install test deps with pip since we don't have tox.
  [Stephen L Arnold]
- Appveyor.yml: update install cmds and python version, re-enable.
  [Stephen L Arnold]
- .gitchangelog.rc: remove cruft to fix --debug arg. [Stephen L Arnold]

  * use git describe directly instead of (alredy removed) shell wrapper
- Add a .codeclimate.yml config file. [Stephen L Arnold]
- Clean out pytest, restore upstream nose config and use nosetest.
  [Stephen L Arnold]

  * also restore internal coverage command runner in test/common.py
- Force travis to install system pkg for (optional) runtime dep.
  [Stephen L Arnold]
- Setup.cfg: add missing mako dep and add linting to CI tests. [Stephen
  L Arnold]
- Revert "move version var to module level and read it via attr in
  setup.cfg" [Stephen L Arnold]

  This reverts commit fa496a29ac95e98a564c4fe38ca50e52f0de7383.
- Move version var to module level and read it via attr in setup.cfg.
  [Stephen L Arnold]
- Force setuptools upgrade in travis env. [Stephen L Arnold]
- README.rst: point license badge at pypi so it actually works. [Stephen
  L Arnold]

  * github fails to indentify it as BSD so github badge type fails
  * also switch travis urls to travis-ci.com <sigh>
- README.rst: swap out upstream badges for local ones. [Stephen L
  Arnold]
- Disable old CI and add new baseline travis.org cfg. [Stephen L Arnold]
- Add legacy tox.ini and .gitignore with python stuffs. [Stephen L
  Arnold]
- Setup.cfg: fleash out minimum settings for proper PEP 517 install.
  [Stephen L Arnold]
- Remove last vestiges of mustache support and tests (long stale
  upstream) [Stephen L Arnold]
- Create PEP 517/518 compliant setup.cfg and set last version (3.0.4)
  [Stephen L Arnold]


3.0.4 (2018-03-17)
------------------

Fixes
~~~~~
- Conform to PEP479 as required by python 3.7 (fixes #101) [Valentin
  Lab]


3.0.3 (2017-04-23)
------------------

Fixes
~~~~~
- API cli change not documented about implicit ``HEAD`` removed in
  revision list specifier. (fixes #81) [Valentin Lab]

  In 2.5.1, ``gitchangelog show ^3.0.0`` command would implicitly add a
  ``HEAD`` in the revlist specifiers, effectively being equivalent to
  ``0.0.3..HEAD``.

  This behavior is removed in 3.0.0+ to stick to ``git rev-list REVLIST``
  syntax.  As a consequence, ``gitchangelog ^3.0.0`` won't select any
  revision and thus will cast an error about no commits matching revlist.


3.0.2 (2017-04-21)
------------------

Fixes
~~~~~
- [mustache/markdown] template is now compatible with incremental
  changelog generation patterns. (fixes #80) [Valentin Lab]


3.0.1 (2017-03-17)
------------------

Fixes
~~~~~
- Support of commits with empty message. (fixes #76) [Valentin Lab]


3.0.0 (2017-03-17)
------------------

New
~~~
- Template path can now be specified in ``git config``. (fixes #73)
  [Valentin Lab]
- Support of already compiled regex object in config file. [Valentin
  Lab]
- Added ``FileRegexSubst`` to allow updatable incremental recipe.
  [Valentin Lab]

  With the added function and recipe as an example, you can update a
  current unreleased changelog additionaly to the traditional incremental
  behavior. ``FileRegexSubst`` might prove itself to be more powerfull
  tahn ``FileInsertAtFirstRegexMatch`` if you handle fairly complex regexes.
- Configurable ``publish`` action to allow more automated changelog
  scenarios (fixes #39) [Valentin Lab]

  In particular, projects using incremental changelog generation can now
  fully automate the process by using a ``publish`` action that inserts
  new sections in an existing changelog file.
- Added ``absolute_import`` stance. [Valentin Lab]
- Added information on single package installation. [Valentin Lab]
- Major cleaning drived by coverage stats. [Valentin Lab]
- Add some usefull values in config environment. [Valentin Lab]
- ``unreleased_version_label`` can now be computed on the fly. [Valentin
  Lab]

  This can let you rename the first section about non yet tagged commit
  more precisely. For instance by using the commit hash or any git
  property.
- Full tested windows support added. [Valentin Lab]
- Replaced ``cat`` construct by platform compatible
  ``file_put_contents(..)``. [Valentin Lab]
- Reference config file is not anymore required. (fixes #54) [Valentin
  Lab]
- New ``revs`` config file option allowing dynamically setting target
  rev-list. (fixes #61) [Valentin Lab]

  With this option, incremental changelog become more streamlined. With
  prior behavior, you had to know which was the last version prior to
  calling ``gitchangelog``. Now, calling ``gitchangelog`` alone can generate
  the exact last missing part thanks to this new config option.
- Added ``sha1_short`` to commit data for output engines. (fixes #49)
  [Valentin Lab]
- Templates now support direct path to files (fixes #46, fixes #63).
  [Héctor Pablos, Valentin Lab]

  Note that relative paths will be searched from the git toplevel.
- Provide helpers to integrate ``Co-Authored-By`` trailer value. (fixes
  #69) [Valentin Lab]

  You can use now ``commit["authors"]`` in templates to get a list of all
  authors of a commit. See the mako template ``restructuredtext.tpl`` for
  example of usage. Mustache templates gets also their own baked in joined
  list of authors through ``commit["author_names_joined"]``.
- Provide complete access on commit API to templates (fixes #18)
  [Valentin Lab]
- Supports trailer key values support. [Valentin Lab]
- Windows compatibility. [Jean-Baptiste Lab, Laurent LAPORTE, Michele,
  Valentin Lab]

Changes
~~~~~~~
- Use tagger date when tags are annotated instead of commit date. (fixes
  #60) [Valentin Lab]
- Included ``file_put_contents(..)`` in main ``gitchangelog.py``.
  [Valentin Lab]

  We will need this one in the next commits.
- Remove usage of shell in git commands. [Valentin Lab]
- Remove multi-commands in tests to move towards windows compatibility.
  [Valentin Lab]

  Introduction of a single entrypoint for casting git commands.
- Removed the need of the ``show`` positional argument. [Valentin Lab]
- Suppression of the obsolete ``gitchangelog init`` command. [Valentin
  Lab]
- Use iterators for reducing memory footprint when possible. (fixes #19)
  [Valentin Lab]

  Note that ``rest_py`` engines will fully leverage iterators in the
  data structure by outputing content as it is generated, limiting
  overall footprint even more. Templates engines, on the other end,
  will render the full changelog in memory anyway before printing it.

Fixes
~~~~~
- Separated tests in multiple files with tailored smaller setups.
  [Valentin Lab]
- Support closed or closing pipes on gitchangelog's stdout gracefully.
  [Valentin Lab]

  Python would output some angry comments for instance when using::

       gitchangelog | head

  Now it is much more graceful and will let the process finish earlier
  without complaining.
- Remove message for ``assertNoDiff(..)`` as it prevents showing the
  actual diff. [Valentin Lab]
- Coverage stances are now compatible with windows. [Valentin Lab]
- Allow testing with unicode in python 2.7 on windows. [Valentin Lab]
- Prevent ``IOError (Errno 0)`` in windows with python 2.7 when using
  codepage 65001. [Valentin Lab]

  This is same problem (and work-around) as
  http://stackoverflow.com/questions/7078232 . It seems to be a bug in
  code page 65001 (utf-8) on windows.
- Force output encoding to 'utf-8' on windows for tests. [Valentin Lab]
- Protect correctly arguments for cross-platform compatibility.
  [Valentin Lab]
- Settings environment variable in a platform compatible way. [Valentin
  Lab]
- Avoid writing files with windows endlines in tests. [Valentin Lab]

  This is to prevent double endlines ending when first writing to
  template, then rendering the template.
- Windows end of lines must be ignored when diffing. [Valentin Lab]
- Removed all use of ``difflib`` as it is now integrated in
  ``unittest``. [Valentin Lab]
- Windows would not be able to delete git temporary directory in tests.
  [Valentin Lab]
- Windows compatibility issues with identifiers using '^'. [Valentin
  Lab]

  This uncovered an unexpected auto-correcting bug about empty revs
  specifiers that was fixed.
- Windows support of ``$tprog``'s calls in tests. [Valentin Lab]
- Too broad catching of ``ShellError`` exception. [Valentin Lab]
- Revlist would not work as expected on windows. [Valentin Lab]

  Windows does not support single quotes in command line as linux
  does. Fortunately there is no requirements on singles quotes so they
  were removed everywhere, ensuring a better windows compatibility.
- Using revlists could display unwanted commits or no commits. [Valentin
  Lab]

  This was happening when specifying revisions that didn't match
  commits tagged by tags matching the ``tag_filter_regexp``.
- Ability to specify rev-lists for partial changelogs creation was not
  working on windows. [Valentin Lab]
- Encoding issues prevented log to be outputed on specific windows
  versions. [Valentin Lab]
- Fixed encoding issue when reading UTF-8 git logs with a different
  default locale. [Valentin Lab]

  Windows platform were more likely to get hit by this bug as their
  default code page is not ``utf-8``. It was fixed by using an explicit
  encoding when reading git logs. The default value for this encoding
  can now be set in the ``gitchangelog``'s config file, per-repository.
  Although, this option should be only set in pathological configuration
  as the default behavior is to use ``git config i18n.logOutputEncoding``
  when set, or if not set, ``utf-8``, which is the default log encoding
  of git.


2.5.1 (2015-11-11)
------------------

Fixes
~~~~~
- Reference config is used for defaults. [Tuukka Mustonen]
- Error message when called in non-git directories was not correctly
  displayed on python 3. [Valentin Lab]
- ``--debug`` argument would generate command line arguments parsing
  errors on python 2.7.  (fixes #66) [Valentin Lab]


2.5.0 (2016-10-16)
------------------

New
~~~
- Hide unexpected traceback per default and allow them to be displayed
  if wanted. [Valentin Lab]
- New lines fixes in current default ReST format (fixes #62) [Stavros
  Korokithakis]

  These were modified:

  - no new line between list element, except when there's some
    body message to display, then use only one new line at the
    beginning of the body to issues with possible lists in body.
  - one new line before section titles.
  - two new lines before versions titles.

Fixes
~~~~~
- Output warning on stderr in some weird cases (fixes #52) [Valentin
  Lab]

  If no tag are found in the repository, or no tag matches the filter
  regex, or if all commits are ignored... this will lead to disturbing but
  legit outputs from ``gitchangelog``. So as to help diagnose what is
  going on, additional warnings are then printed when edge cases are
  encountered.
- [mustache/restructuredtext] avoid HTML-escaping content of variables
  (fixes #64) [Mark Milstein]


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


2.2.0 (2015-01-27)
------------------

New
~~~
- Added a ``body`` and an sole ``Other`` section to reference tests.
  [Valentin Lab]
- Provide support for older config file format. [Valentin Lab]
- Added 'octobercms-plugin' mako template. (fixes #16) [Valentin Lab]
- Added a new test to run at least once all provided templates.
  [Valentin Lab]
- Added ``body_process`` and ``subject_process`` options. (fixes #22)
  [Valentin Lab]

  These options superseeds ``replace_regexps`` and ``body_split_regexp``
  as they provide a full control over text transformation of the subject
  or the body of the commit before they get included in the changelog.
- Added ``include_merge`` option to filter out merge commit. [Casey
  Duquette]
- Support to provide unlimited revisions for ``.log()``. [Valentin Lab]
- Added a simple changelog format for tests. [Valentin Lab]

  This formats is intended not to change, and to quickly visualize and
  compare changelogs output.
- Limit test imprints. [Valentin Lab]

  Removed the specific pre-configured log history from common git case.
  Offer a common just inited git case.
- Added a ``raw_renderer`` for test. [Valentin Lab]

  This should be used to restrict the perimeter of tests. This mainly
  removes the formatting concerns out when needed.

Changes
~~~~~~~
- Produce a more linear commit history (fixes #14) [Casey Duquette]

  Instead of retrieving the git log ordered by date, retrieve the log as
  a difference between tags to produce a more accurate view of changes
  between releases.

  For instance, imagine this git graph::

    * 6c0fd62 (HEAD, tag: sprint-6, origin/smoke, smoke, develop)
    *   5292a28 Merge back to develop
    |\
    | * 6612fce (tag: sprint-5.1, origin/master, origin/HEAD, master) super important hotfix
    * | 7d6286f more development work
    * | 8c1e3d6 continued development work
    * | fa3d4bd development work
    |/
    * ec1a19c (tag: sprint-5)

  Previously, commits ``fa3d4bd``, ``8c1e3d6``, ``7d6286f`` that
  occurred on the develop branch before the hotfix that led to tagging
  ``sprint-5.1``, were captured in the changelog under release
  ``sprint-5.1`` because of the order of the commits. But it is obvious
  that these commits were not included in a release until
  ``sprint-6``. The new method of calculating the changelog will capture
  this and reflect it properly, assigning those changes to ``sprint-6``.
- Provide a helper to get ``GitCommit`` objects out of ``GitRepos``.
  [Valentin Lab]

Fixes
~~~~~
- Last commit was omitted (fixes #23). [Valentin Lab]
- Bogus messages when template didn't exist. [Valentin Lab]

  Refactored out the common code and corrected the bad error message.
- Removed hypothetical memory exhaust while parsing ``git log``.
  [Valentin Lab]

  Parse stdout as it's produced by git log by chunks.
- Replacing standard exception is not so valuable and can hide real
  info. [Valentin Lab]

  ``wrap`` facility already provide a readable exception message. And
  the exception could come from other issues than bad identifier. Thus,
  we should keep the original message.


2.1.2 (2014-04-25)
------------------

Fixes
~~~~~
- Fail with error message when config path exists but is not a file.
  (fixes #11) [Casey Duquette]

  For example, the config file could be a directory.


2.1.1 (2014-04-15)
------------------

Fixes
~~~~~
- Removed exception if you had file which name that matched a tag's
  name. (fixes #9) [Valentin Lab]


2.1.0 (2014-03-25)
------------------

New
~~~
- Python3 compatibility. [Valentin Lab]
- Much greater performance on big repository by issuing only one shell
  command for all the commits. (fixes #7) [Valentin Lab]
- Added a complete reference test. [Valentin Lab]
- Add ``init`` argument to create a full ``.gitchangelog.rc`` in current
  git repository. [Valentin Lab]
- Remove optional first argument that could specify the target git
  repository to consider. [Valentin Lab]

  This is to remove duplicate way to do things. ``gitchangelog`` should be run
  from within a git repository.

  Any usage of ``gitchangelog MYREPO`` can be written ``(cd MYREPO;
  gitchangelog)``.
- Use a standard formatting configuration by default. [Valentin Lab]

  A default standard way of formatting is used if you don't provide
  any configuration file. Additionaly, any option you define in your
  configuration file will be added "on-top" of the default configuration
  values. This can reduce config file size or even remove the need of
  one if you follow the standard.

  And, thus, you can tweak the standard for your needs by providing only partial
  configuration file. See tests for examples.
- Remove user or system wide configuration file lookup. [Valentin Lab]

  This follows reflexion that you build a changelog for a repository and
  that the rules to make the changelog should definitively be explicit and
  thus belongs to the repository itself.

  Not a justification, but removing user and system wide configuration files
  also greatly simplifies testability.

Changes
~~~~~~~
- Moved commit's attribute retrieval out of ``__init__`` towards
  ``__getattr__``. [Valentin Lab]

  This allows to fetch attribute on demand. This won't have any performance hit yet as
  all GitCommit will trigger the full fetch at least once for now.

  But we now can initialize the GitCommit attributes with other means. And if we don't use
  an attribute that wasn't computed, we will spare a ``git show`` call.
- Code optimization. [Valentin Lab]

  To be noted, we don't seem to need more than identifiers in tags. The
  upcoming ``__getattr__`` implementation in GitCommit will remove
  useless ``git show`` computations for these commits it seems.
- Refactored out the formatting characters from GIT. [Valentin Lab]

  This is to prepare to clean __init__.py from any initilisation process.
  This will path the way to permit GitCommit being initilised with full
  values in the ``git log`` scenario coming in a few commits.
- Move the reversing python code towards git command line code.
  [Valentin Lab]

  Actual performance improvement is... un-noticeable. Questioning the if this
  is really a good patch because it introduce usage of advanced (recent) options

Fixes
~~~~~
- Encoding issues with non-ascii chars. [Valentin Lab]
- Avoid using pipes for windows compatibility and be more performant by
  avoiding to unroll full log to get the last commit. [Valentin Lab]
- Better support of exotic features of git config file format. (fixes
  #4) [Valentin Lab]

  git config file format allows ambiguous keys:

      [a "b.c"]
          d = foo
      [a.b "c"]
          e = foo
      [a.b.c]
          f = foo

  Are all valid. So code was simplified to use directly ``git config``.
  This simplification will deal also with cases where section could be
  attributed values:

      [a "b"]
          c = foo
      [a]
          b = foo

  By avoiding to parse the entire content of the file, and relying on
  ``git config`` implementation we ensure to remain compatible and not
  re-implement the parsing of this file format.
- Gitchangelog shouldn't fail if it fails to parse your git config.
  [Michael Hahn]


2.0.0 (2013-08-20)
------------------

New
~~~
- Added a ``mako`` output engine with standard ReSTructured text format
  for reference. [Valentin Lab]
- Added some information on path lookup scheme to find
  ``gitchangelog.rc`` configuration file. [Valentin Lab]
- Added templating system and examples with ``mustache`` template
  support for restructured text and markdown output format. [David
  Loureiro]
- Separated creation of the data structure and its rendering. [David
  Loureiro]

  This commit prepares for any templating system to take back the job of rendering.

Changes
~~~~~~~
- Removed ``pkg`` and ``dev`` commits from default sample changelog
  output. [Valentin Lab]

Fixes
~~~~~
- Some error message weren't written on stderr. [Valentin Lab]


1.1.0 (2012-05-03)
------------------

New
~~~
- New config file lookup scheme which adds a new possible default
  location ``.gitchangelog.rc`` in the root of the git repository.
  [Valentin Lab]
- ``GitRepos`` object now give access to directory informations and
  whole git config read access. [Valentin Lab]
- Added a new section to get a direct visual of ``gitchangelog`` output.
  Reworded some sentences and did some other minor additions. [Valentin
  Lab]

Changes
~~~~~~~
- Removed old ``gitchangelog.rc.sample`` in favor of the new documented
  one. [Valentin Lab]

Fixes
~~~~~
- The sample file was not coherent with the doc, and is now accepting
  'test' and 'doc' audience. [Valentin Lab]


1.0.2 (2012-05-02)
------------------

New
~~~
- Added a new sample file heavily documented. [Valentin Lab]

Changes
~~~~~~~
- Changed default config file name towards ``~/.gitchangelog.rc``
  instead of ``~/.git-changelog.rc``. [Valentin Lab]
- Added a link to PyPI in the doc. [Valentin Lab]

Fixes
~~~~~
- ``ignore_regexps`` where bogus and would match only from the beginning
  of the line. [Valentin Lab]
- Display author date rather than commit date. [Valentin Lab]


1.0.1 (2011-06-29)
------------------

Fixes
~~~~~
- ReST title consistency corrected in docs. [Valentin Lab]


1.0.0 (2011-06-29)
------------------

New
~~~
- Use ``GITCHANGELOG_CONFIG_FILENAME`` environ variable (if set) to get
  the default location of config file. [Valentin Lab]

Changes
~~~~~~~
- Extracted the main code in a function ``main`` [Valentin Lab]

Fixes
~~~~~
- Adds a period to subject message only if last char of subject is alpha
  numeric. [Valentin Lab]


0.1.4 (2011-06-29)
------------------

Changes
~~~~~~~
- Removed ``stdin`` from ``cmd()`` function. [Valentin Lab]
- Various small code enhancements and cleanup. [Valentin Lab]
- Forced MULTILINE regexps on ``paragraph_wrap`` which is used to wrap
  body of commit messages. [Valentin Lab]

Fixes
~~~~~
- Fixed the ``body_split_regexp`` to keep title words. [Valentin Lab]
- Corrected big bad bug due to ``Popen.wait()`` usage instead of
  ``Popen.communicate()`` [Valentin Lab]


0.1.3 (2011-06-29)
------------------

New
~~~
- Can now compare two commit. [Valentin Lab]
- Added ``LAST`` virtual identifier to get the last element coming from
  ``HEAD``. [Valentin Lab]

Fixes
~~~~~
- Last revision is now displayed in changelog. [Valentin Lab]

  new: dev: added new option ``tag_filter_regexp`` to filter tags we want to use in the changelog.


0.1.2 (2011-06-29)
------------------

New
~~~
- Sections in changelog are now in the order given in ``git-
  changelog.rc`` in the ``section_regexps`` option. [Valentin Lab]
- Added ``body_split_regexp`` option to attempts to format correctly
  body of commit. [Valentin Lab]
- Use a list of tuple instead of a dict for ``section_regexps`` to be
  able to manage order between section on find match. [Valentin Lab]
- New ``unreleased_version_label`` option in ``git-changelog.rc`` to
  change label of not yet released code. [Valentin Lab]
- Use ``git-changelog`` section in ``git config`` world appropriately.
  [Valentin Lab]

Changes
~~~~~~~
- Commented code to toggle doctest mode. [Valentin Lab]
- Cosmetic removal of trailing whitespaces. [Valentin Lab]

Fixes
~~~~~
- Doctests were failing on this. [Valentin Lab]
- Bad sorting of tags (alphanumerical). Changed to commit date sort.
  [Valentin Lab]
- Support of empty commit message. [Valentin Lab]
- ``git`` in later versions seems to fail on ``git config <key>`` with
  errlvl 255, that was not supported. [Valentin Lab]
- Removed Traceback when there were no tags at all in the current git
  repository. [Valentin Lab]


0.1.1 (2011-06-29)
------------------

New
~~~
- Added section classifiers (ie: New, Change, Bugs) and updated the
  sample rc file. [Valentin Lab]
- Added a succint ``--help`` support. [Valentin Lab]

Fixes
~~~~~
- Fixed case where exception was thrown if two tags are on the same
  commit. [Valentin Lab]


0.1.0 (2011-06-29)
------------------

New
~~~
- Added ``git-changelog`` which converts git log history to a changelog
  provided a config file. [Valentin Lab]
