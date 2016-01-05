# Checklist before making a new release of a Python project

Tags: python, release, checklist


# Prepare the environment

Install a venv for dev, with tox, py.test, setuptools, etc.

  cd hex2words/
  pyvenv venv-3.4-dev/
  ./venv-3.4-dev/bin/pip install -r requirements-dev.txt


# Make sure you have something to release

1. any Pull Request to Merge? any Issue to solve? any commit to push?
2. are these tasks introducing big or small changes? How do they affect your versioning schema (e.g. semantic versioning)?
3. do you have to bump any version?

  vim hex2words/version.py
  and change the version number

4. Did you update CHANGELOG.rst?


# Profit from automation to check everything runs as expected

1. Run tests for the project

  `PYTHONPATH='.' ./venv-3.4-setup/bin/py.test hex2words/`

2. Run tests for different platforms with tox

  ./venv-3.4-setup/bin/tox

3. Syntax checking:

  * pyflakes: `./venv-3.4-setup/bin/pyflakes hex2words/*.py`
  * pylint: `./venv-3.4-setup/bin/pylint hex2words/ | less`

4. Check your package:

  cd project-root/  # Where setup.py is.
  ./venv-3.4-setup/bin/pyroma .

5. Repeat till you are satisfied with your work.

# Last checks

1. Anything to commit after running the tests and updating the CHANGELOG?
2. Anything to tag (with signature) to the new version?

  GNUPGHOME='...' git tag -m 'version:1.2.3' -u <gpg-fpr> v1.2.3 <commit-hash>
  git push origin --tags

# Package and ship it.

1. Create a source distrib, binary distrib and a wheel distrib

  ./venv-3.4-setup/bin/python setup.py sdist bdist bdist_wheel

  This will create a `dist/` directory.

2. Upload them with twine: `./venv-3.4-setup/bin/twine dist/*`

  You will need credentials for the Cheeseshop in ~/.pypirc

