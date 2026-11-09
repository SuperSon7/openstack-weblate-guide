===============================
OpenStack Weblate walkthrough
===============================

`Read the illustrated guide <doc/source/openstack-weblate-guide.rst>`_
to sign in with OpenInfraID, translate a documentation string, and confirm
the save in Weblate's History tab. The guide is in English and uses Korean
as the target language. Its eleven screenshots follow a translation in the
``i18n / master / doc`` component.

For offline reading, download the
`standalone HTML guide <openstack-weblate-guide.html>`_ and open it in a
browser. It includes the images.

Integrating with the I18n Contributor Guide
-------------------------------------------

This repository contains a proposed addition to the OpenStack I18n
Contributor Guide. Its layout follows the
`upstream source tree
<https://opendev.org/openstack/i18n/src/commit/8ea7bcd3e62733684d7196fe997840f47c1d4711/doc/source>`_.
The instructions below assume that this repository and an OpenStack
``i18n`` checkout are sibling directories.

From the root of the ``i18n`` checkout, run::

   cp ../openstack-weblate-guide/doc/source/openstack-weblate-guide.rst doc/source/
   cp -R ../openstack-weblate-guide/resources/weblate resources/
   git apply --check ../openstack-weblate-guide/i18n-navigation.patch
   git apply ../openstack-weblate-guide/i18n-navigation.patch
   tox -e docs

The patch adds an entry after ``contributing`` in the existing
``doc/source/index.rst`` toctree and a link in the Translations section
of ``doc/source/contributing.rst``. The new page uses the title convention
documented in `About this guide
<https://docs.openstack.org/i18n/latest/about.html#titles>`_.
It refers to screenshots in ``resources/weblate/`` using relative paths
from ``doc/source/``, following the pattern used for the existing I18n mascot.

Verification
------------

On November 9, 2026, the proposed page and navigation changes were tested
in an ``openstack/i18n`` checkout at
``8ea7bcd3e62733684d7196fe997840f47c1d4711``.
``tox -e docs`` passed, and doc8 reported zero errors. A separate English
HTML build with ``sphinx-build -W -b html`` passed using the upstream
configuration and OpenStack theme. Both navigation links and all eleven
screenshot files resolved in the generated site. The translated builds
reported warnings in other existing documents.

The `published I18n guide <https://docs.openstack.org/i18n/latest/>`_
still includes Zanata instructions, including the translator registration
steps. This walkthrough documents the Weblate session performed on
November 2, 2026. The saved translation can be inspected in
`Weblate <https://openstack.weblate.cloud/translate/i18n/master/doc/ko_KR/?checksum=037c76b713c5302c>`_.
