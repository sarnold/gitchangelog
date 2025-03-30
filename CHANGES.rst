3.2.1.dev4+g74ac484.d20250330
-----------------------------

New
~~~
- Add reuse tool, use reuse cfg and LICENSES dir for compliance.
  [Stephen Arnold]

Changes
~~~~~~~
- Add tox shared env extension, update readme and project files.
  [Stephen L Arnold]
- Update workflow action and python version, add base automation.
  [Stephen L Arnold]
- Misc config updates, flags arg in publish callable needs discussion.
  [Stephen Arnold]


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
- Re-package get-rcpath helper script, install to bin directory.
  [Stephen L Arnold]
- Add default compact reference config for github release action.
  [Stephen L Arnold]

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
- Bump version 3.0.4-3 -> 3.0.4-4 for release. [Stephen L Arnold]
- README.rst: add github action feature bullet. [Stephen L Arnold]
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
