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
  
  FIXME Maybe `check-manifest <https://pypi.python.org/pypi/check-manifest>`_ is also interesting.

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

Before uploading it, you should [have registered](http://python-packaging-user-guide.readthedocs.org/en/latest/distributing/#register-your-project) your project.

# Registering a project in the Cheeseshop

You can generate your project's metadata with:

  ./venv-3.4-setup/bin/python setup.py egg_info

And then check if ./PROJECT.egg-info/PKG-INFO contains the right metadata.

If so, proceed to register the package. For each package, run:

  ./venv-py3.4/bin/twine register -r test dist/PROJECT-1.0.0-py3-none-any.whl

You should have generated the Wheels, Tarballs, etc. before (e.g. with `setup.py sdist bdist bdist_wheel`). You will run `twine register` for each file you want to register. Example, if you have run `setup.py sdist bdist bdist_wheel`, you will get 3 files: the source tarball, the binary distribution and the wheels distrib file. This may help:

  for i in dist/\*; do twine register -r test $i; done;

`-r test` is meant to use the *entry* in the `~/.pypirc` config file, which points in my case, to the [Test Cheeseshop](https://testpypi.python.org).

After registering the project, you can check the website, e.g. https://testpypi.python.org, to see if everything was uploaded properly.

