======
Design
======

Constraints
------------

This section outlines the design constraints that django-admin2 follows:

* There will be nothing imported from ``django.contrib.admin``.
* The original bootstrap/ theme shall contain no UI enhancements beyond the original ``django.contrib.admin`` UI. (However, future themes can and should be experimental.)
* External package dependencies are allowed but should be very limited.
* Building a django-admin2 theme cannot involve learning Python, which explains why we are not using tools like django-crispy-forms. (One of our goals is to make it easier for designers to explore theming django-admin2).

Backend Goals
---------------

Rather than creating yet another project that skins ``django.contrib.admin``, our goal is to rewrite ``django.contrib.admin`` from the ground up using Class-Based Views, better state management, and attention to all the lessons learned from difficult admin customizations over the years. 

While the internal API for the backend may be drastically different, the end goal is to achieve relative parity with existing functionality in an extendable way.

Clean code with substantial documentation is also a goal:

* Create a clearly understandable/testable code base.
* All classes/methods/functions documented.
* Provide a wealth of in-line code documentation.

REST API Goals
----------------

There are a lot of various cases that are hard to handle with pure HTML projects, but are trivial to resolve if a REST API is available. For example, using unmodified ``django.contrib.admin`` on projects with millions of database records combined with foreign key lookups. In order to handle these cases, rather than explore each edge case, ``django-admin2`` provides a RESTFUL API as of version 0.2.0.

Goals:

* Provide a extendable self-documenting API (django-rest-framework).
* Reuse components from the HTML view.
* Backwards compatibility: Use a easily understood API versioning system so we can expand functionality of the API without breaking existing themes.

UI Goals
---------

1. Replicate the old admin UI as closely as possible in the bootstrap/ theme. This helps us ensure that admin2/ functionality has parity with admin/.

2. Once (1) is complete and we have a stable underlying API, experiment with more interesting UI variations.

