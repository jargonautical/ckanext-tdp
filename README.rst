==========================================
ckanext-tdp: The data place customisations
==========================================
This CKAN extension contains all the default customisations for the dataplace,
which will be provided on all CKAN instances we host.

* The Dataplace flavoured styling, with customisable color an hero image
* Updated homepage layout, with dataset spotlight (most viewed, recently 
  updated & added) and partner logo's

-------------
Configuration
-------------
A couple of configuration can be passed through the configuration.

.. code::

  ckanext.tdp.stylesheet_name: default
  ckanext.tdp.primary_colour: #FF530D
  ckanext.tdp.hero_image_url: https://url.to/image.jpg

* `stylesheet_name` is an option when we generate a custom stylesheet for
  a client. For default CKAN styling, this setting can be left out an will
  default to the `default` stylesheet
* `primary_colour` determines the color of the CKAN instance, this needs to be
  set as a hex color value.
* `hero_image_url` is the URL to the hero image. It is strongly preferred to
  self-host this image, and provide a HTTPS url to avoid browser warnings for
  potential insecure content.

------------
Styling
------------

Modular CSS architecture is used, loosely based on SMACSS(https://smacss.com/)
Using PostCSS(https://github.com/postcss/postcss) and the Post CSS CLI(https://www.npmjs.com/package/postcss-cli).

~~~~~~~~~~
Developing
~~~~~~~~~~

CSS and Styles

Run ``npm install``

To build the CSS use ``npm run build``

To watch the CSS for changes and automatically trigger a build, use ``npm run watch``

PostCSS Is using Sugarss syntax https://github.com/postcss/sugarss and linted with stylelint https://github.com/stylelint/stylelint
Source mapping is enabled to assist with debugging - this will be built with the CSS.

------------
Contributing
------------

Navigate to the public folder ``docker-ckan/src/ckanext-tdp/ckanext/tdp/public``
Run ``npm run lint`` - ensure no errors are produced before committing work.

---------

.. You should enable this project on travis-ci.org and coveralls.io to make
   these badges work. The necessary Travis and Coverage config files have been
   generated for you.

.. image:: https://travis-ci.org//ckanext-tdp.svg?branch=master
    :target: https://travis-ci.org//ckanext-tdp

.. image:: https://coveralls.io/repos//ckanext-tdp/badge.svg
  :target: https://coveralls.io/r//ckanext-tdp

.. image:: https://pypip.in/download/ckanext-tdp/badge.svg
    :target: https://pypi.python.org/pypi//ckanext-tdp/
    :alt: Downloads

.. image:: https://pypip.in/version/ckanext-tdp/badge.svg
    :target: https://pypi.python.org/pypi/ckanext-tdp/
    :alt: Latest Version

.. image:: https://pypip.in/py_versions/ckanext-tdp/badge.svg
    :target: https://pypi.python.org/pypi/ckanext-tdp/
    :alt: Supported Python versions

.. image:: https://pypip.in/status/ckanext-tdp/badge.svg
    :target: https://pypi.python.org/pypi/ckanext-tdp/
    :alt: Development Status

.. image:: https://pypip.in/license/ckanext-tdp/badge.svg
    :target: https://pypi.python.org/pypi/ckanext-tdp/
    :alt: License

=============
ckanext-tdp
=============

.. Put a description of your extension here:
   What does it do? What features does it have?
   Consider including some screenshots or embedding a video!


------------
Requirements
------------

For example, you might want to mention here which versions of CKAN this
extension works with.


------------
Installation
------------

.. Add any additional install steps to the list below.
   For example installing any non-Python dependencies or adding any required
   config settings.

To install ckanext-tdp:

1. Activate your CKAN virtual environment, for example::

     . /usr/lib/ckan/default/bin/activate

2. Install the ckanext-tdp Python package into your virtual environment::

     pip install ckanext-tdp

3. Add ``tdp`` to the ``ckan.plugins`` setting in your CKAN
   config file (by default the config file is located at
   ``/etc/ckan/default/production.ini``).

4. Restart CKAN. For example if you've deployed CKAN with Apache on Ubuntu::

     sudo service apache2 reload


---------------
Config Settings
---------------

Document any optional config settings here. For example::

    # The minimum number of hours to wait before re-checking a resource
    # (optional, default: 24).
    ckanext.tdp.some_setting = some_default_value


------------------------
Development Installation
------------------------

To install ckanext-tdp for development, activate your CKAN virtualenv and
do::

    git clone https://github.com//ckanext-tdp.git
    cd ckanext-tdp
    python setup.py develop
    pip install -r dev-requirements.txt


-----------------
Running the Tests
-----------------

To run the tests, do::

    nosetests --nologcapture --with-pylons=test.ini

To run the tests and produce a coverage report, first make sure you have
coverage installed in your virtualenv (``pip install coverage``) then run::

    nosetests --nologcapture --with-pylons=test.ini --with-coverage --cover-package=ckanext.tdp --cover-inclusive --cover-erase --cover-tests


---------------------------------
Registering ckanext-tdp on PyPI
---------------------------------

ckanext-tdp should be availabe on PyPI as
https://pypi.python.org/pypi/ckanext-tdp. If that link doesn't work, then
you can register the project on PyPI for the first time by following these
steps:

1. Create a source distribution of the project::

     python setup.py sdist

2. Register the project::

     python setup.py register

3. Upload the source distribution to PyPI::

     python setup.py sdist upload

4. Tag the first release of the project on GitHub with the version number from
   the ``setup.py`` file. For example if the version number in ``setup.py`` is
   0.0.1 then do::

       git tag 0.0.1
       git push --tags


----------------------------------------
Releasing a New Version of ckanext-tdp
----------------------------------------

ckanext-tdp is availabe on PyPI as https://pypi.python.org/pypi/ckanext-tdp.
To publish a new version to PyPI follow these steps:

1. Update the version number in the ``setup.py`` file.
   See `PEP 440 <http://legacy.python.org/dev/peps/pep-0440/#public-version-identifiers>`_
   for how to choose version numbers.

2. Create a source distribution of the new version::

     python setup.py sdist

3. Upload the source distribution to PyPI::

     python setup.py sdist upload

4. Tag the new release of the project on GitHub with the version number from
   the ``setup.py`` file. For example if the version number in ``setup.py`` is
   0.0.2 then do::

       git tag 0.0.2
       git push --tags
