Customization
=============

Settings
~~~~~~~~

You can customize the application using ``settings.py``.

==================================================== ============= ================================
Name                                                 Default       Description
==================================================== ============= ================================
``ENDLESS_PAGINATION_PER_PAGE``                      10            How many objects are normally displayed in a page 
                                                                   (overwriteable by templatetag).
---------------------------------------------------- ------------- --------------------------------
``ENDLESS_PAGINATION_PAGE_LABEL``                    'page'        The querystring key of the page 
                                                                   number (e.g. ``http://example.com?page=2``).
---------------------------------------------------- ------------- --------------------------------
``ENDLESS_PAGINATION_ORPHANS``                       0             See Django *Paginator* definition of orphans.
---------------------------------------------------- ------------- --------------------------------
``ENDLESS_PAGINATION_LOADING``                       'loading'     If you use the default ``show_more`` template, 
                                                                   here you can customize the content of the 
                                                                   loader hidden element. Html is safe here, 
                                                                   e.g. you can show your pretty animated gif
                                                                   ``ENDLESS_PAGINATION_LOADING = """<img src="/static/img/loader.gif" alt="loading" />"""``.
---------------------------------------------------- ------------- --------------------------------
``ENDLESS_PAGINATION_PREVIOUS_LABEL``                '&lt;&lt;'    Default label for *previous* page link.
---------------------------------------------------- ------------- --------------------------------
``ENDLESS_PAGINATION_NEXT_LABEL``                    '&gt;&gt;'    Default label for *next* page link.
---------------------------------------------------- ------------- --------------------------------
``ENDLESS_PAGINATION_ADD_NOFOLLOW``                  *False*       Set to *True* if your SEO alchemist  
                                                                   wants search engines not to follow 
                                                                   pagination links.
---------------------------------------------------- ------------- --------------------------------
``ENDLESS_PAGINATION_PAGE_LIST_CALLABLE``            *None*        Callable that returns pages to be displayed.
                                                                   If *None* a default callable is used 
                                                                   (that produces :doc:`digg_pagination`).
                                                                   See :doc:`templatetags_reference` for
                                                                   information about wtiring custom callables.
---------------------------------------------------- ------------- --------------------------------                                
``ENDLESS_PAGINATION_DEFAULT_CALLABLE_EXTREMES``     3             Deafult number of *extremes* displayed when
                                                                   :doc:`digg_pagination` is used with 
                                                                   default callable.
---------------------------------------------------- ------------- --------------------------------                                
``ENDLESS_PAGINATION_DEFAULT_CALLABLE_AROUNDS``      2             Deafult number of *arounds* displayed when
                                                                   :doc:`digg_pagination` is used with 
                                                                   default callable.
---------------------------------------------------- ------------- --------------------------------                                
``ENDLESS_PAGINATION_TEMPLATE_VARNAME``              'template'    Template variable name used by 
                                                                   ``page_template`` decorator.
                                                                   You can change this value if you are 
                                                                   going to decorate generic views using
                                                                   a different variable name for the template
                                                                   (e.g. ``template_name``).
==================================================== ============= ================================
     
     
Template and css
~~~~~~~~~~~~~~~~

You can override the default template for ``show_more`` templatetag following
some rules:

- *more* link is showed only if variable ``querystring`` is not False
- the container (most external html element) class is *endless_container*
- the *more* link and the loader hidden element live inside the container
- the *more* link class is *endless_more*
- the *more* link rel attribute is ``{{ querystring_key }}``
- the loader hidden element class is *endless_loading*

Application comes with English, Italian and German i18n.