F5 Sphinx Theme
===============

Introduction
------------
This repo contains the `sphinx <http://www.sphinx-doc.org/en/stable/index.html>`_ theme used for project documentation hosted on the `clouddocs.f5.com <http://clouddocs.f5.com>`_ site.

This theme should not be used without modification for project documentation that is not hosted on `clouddocs.f5.com <http://clouddocs.f5.com>`_.

Setup and Configuration
-----------------------
1. Download or ``git clone`` the f5-sphinx-theme.
2. ``pip install .`` from the f5-sphinx-theme base directory.
3. ``pip install -r requirements.txt`` to ensure dependencies are present.
4. Add ``f5-sphinx-theme`` to the "import" section of your project's ``conf.py`` (replace any existing theme import). ::

    import f5_sphinx_theme

5. Configure the ``html_theme`` and ``html_theme_theme_path()`` as shown below. ::

    html_theme = 'f5_sphinx_theme'
    html_theme_path = f5_sphinx_theme.get_html_theme_path()

6. (Optional) Configure the ``html_sidebars`` option. See the `sphinx documentation <http://www.sphinx-doc.org/en/stable/config.html#confval-html_sidebars>`_ for more information. ::

    html_sidebars = {'**': ['searchbox.html', 'localtoc.html', 'globaltoc.html']}

7. (Optional) Configure the ``html_theme_options{}`` dictionary. The ``site_name`` and ``next_prev_link`` options are supported. ::

    html_theme_options = {
                            'site_name': 'My Site Name',
                            'next_prev_link': False
                         }

Depending on your publication/deployment process, you may have to re-build your documentation for the changes to take effect.

Customizing CSS and Assets
--------------------------
The css styling for the project uses two css files: 

- ``f5.css`` contains F5's core bootstrap customizations and fonts. 
- ``custom.css`` can be used for any modifications you'd like to make for your documentation to make content easier to navigate and reference. Bear in mind that all mods must still comply with the F5 Corporate Branding strategy and requirements.

After customizing the ``custom.css`` file, you'll have to uninstall the theme and reinstall it to apply your changes.

::

    pip uninstall f5-sphinx-theme
    pip install .

Integrated Styling Tools
------------------------
The ``f5-sphinx-theme`` is set up to use the Font Awesome integration provided in the `sphinxjp.theme.basicstrap <https://github.com/tell-k/sphinxjp.themes.basicstrap>`_ Sphinx theme/extension. [#sphinxjp]_

To use this extension in your project:

#. Add ``sphinxjp.themes.basicstrap`` to the ``extensions`` section of your project's ``conf.py``.
#. Add ``sphinxjp.themes.basicstrap`` to your project's ``requirements.txt`` file.

To add a Font Awesome icon to your docs: ::

   :fonticon:`fa fa-<icon_name>`

.. [#sphinxjp] ``sphinxjp.themes.basicstrap`` is licensed under the `MIT license <https://opensource.org/licenses/mit-license.php>`_.

Copyright
---------
Copyright 2017 F5 Networks, Inc.

License
-------

Apache V2.0
~~~~~~~~~~~

Licensed under the Apache License, Version 2.0 (the "License"); you may
not use this file except in compliance with the License. You may obtain
a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

