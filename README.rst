======================
django-collapsing-menu
======================

A template tag for generating a collapsing menu with django using jquery and bootstrap.

Installation
============

Use ``pip`` to install from repository::

	-e hg+ssh://hg@bitbucket.org/aashe/django-collapsing-menu#egg=django-collapsing-menu-dev

Add ``collapsing_menu`` to your settings.py file::

	INSTALLED_APPS = (
	    ...
	    'collapsing_menu',
	    ...
	)

Usage
=====

Template Tag
------------

The template tag accepts an outline object from within the context::

	{% load collapsing_menu %}
	{% show_collapsing_menu outline %}

Menu Outline
------------

This outline object must be added to the context by the view, and have the following structure::

	[
		{
			'title': title,
			'url': url,
			'children':
			[
				{
					'title': title,
					'url': url,
					'children':
					[
						{
							'title': title,
							'url': url
						}
					]
				}
			]
		}
	]

Menu items, at each level, can have the following properties
      
*Required*
      
``title``: the name displayed for the link
          
*Optional*::
      
``url``

``bookmark``: the bookmark on the page to scroll too... this could be in the url property but sometimes this is displayed differently

``attrs``: a dictionary attributes to apply to this item (applied to the <li> by default)

``children_attrs``: a dictionary of attributes to apply to the <ul> for children
