Multiple Versions of Django on Travis-CI
========================================
`Django`_ just released `1.4`_ today and we're wondering how best to
`Armstrong`_ against both versions using the amazing `Travis CI`_.  This script
repository contains a ``.travis.yml`` file that demonstrates one way of doing
that.

The steps are simple:

* Create a custom installation script (I've called it ``.travis_setup`` so it's
  hidden by default.
* Add ``env`` variables called ``DJANGO_VERSION`` to your yaml file.  Add one
  entry for each version you want to test (i.e., ``DJANGO_VERSION=1.4``,
  ``DJANGO_VERSION=1.3.1``, and so on).
* Inside the ``.travis_setup`` script make sure that you do ``pip install
  Django==$DJANGO_VERSION`` before installing your Django application.

Now you're set.  Travis-CI will kick off two builds, each with a different
version of Django.

Enjoy!

.. _Django: https://www.djangoproject.com/
.. _1.4: https://www.djangoproject.com/weblog/2012/mar/23/14/
.. _Armstrong: http://www.armstrongcms.org/
.. _Travis CI: http://travis-ci.org/
