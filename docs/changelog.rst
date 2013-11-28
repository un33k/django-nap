=========
Changelog
=========

v0.13.7
=======

+ Added ReadTheDocs, and prettied up the docs

v0.13.6
=======

+ Overhauled testing
+ Added 'total_pages' to page meta.
+ Added Serialiser.obj_class

v0.13.5.1
=========

- Fix fix for b'' from last release, to work in py2

v0.13.5
=======

- Fix use of b'' for Py3.3 [thanks zzing]
+ Add options to control patterns

v0.13.4
=======

+ Added views publisher
+ Updated docs
+ Re-added support for ujson, if installed
- Return http.NotFound instead of raising it
+ Tidied up with pyflakes/pylint
+ Added Publisher.response_class property

v0.13.3
=======

- Make API return NotFound, instead of Raising it
- Remove bogus CSV Reader class

v0.13.2.1
=========

- Fixed typo
- Fixed resolving cache in mixin

v0.13.2
=======

+ Separate Publisher.build_view from Publisher.patterns to ease providing custom patterns
+ Added SimplePatternsMixin for Publisher
+ Added Publisher.sort_object_list and Publisher.filter_object_list hooks

v0.13.1
=======

- Fixed silly bug in inflate

v0.13.0
=======

# WARNING: API breakage
> Changed auto-discover to look for 'publishers' instead of 'seraliser'.
+ Added Field.null support
+ Now use the Field.default value
+ ValidationError handled in all field and custom inflator methods

v0.12.5.1
=========

- Fix mistake introduced in 0.12.3 which broke NewRelic support

v0.12.5
=======

+ Allow disabling of API introspection index
- Restored Django 1.4 compatibility

v0.12.4
=======

+ Split simplecsv and csv export into extras module
- Fixed filename generation in csv export action
- Fixed unicode/str issues with type() calls
+ Merged engine class directly into Publisher
+ Added fields.StringField

v0.12.3
=======

- Fix argument handling in Model*SerialiserFields
+ Added support for Py3.3 [thanks ioneyed]
+ Overhauled the MetaSerialiser class
+ Overhauled "sandbox" app
+ Added csv export action
- Tidied up with pyflakes

v0.12.2
=======

+ Support read_only in modelserialiser_factory

v0.12.1
=======

- Flatten url patterns so object_default can match without trailing /
- Fix class returned in permit decorator [Thanks emilkjer]
+ Allow passing an alternative default instead of None for Publisher.get_request_data
+ Added "read_only_fields" to ModelSerialiser [thanks jayant]

v0.12
=====

+ Tune Serialisers to pre-build their deflater/inflater method lists, removing work from the inner loop
+ Remove \*args where it's no helpful

v0.11.6.1
=========

- Renamed HttpResponseRedirect to HttpResponseRedirection to avoid clashing with Django http class

v0.11.6
=======

- Raise a 404 on paginator raising EmptyPage, instead of failing

v0.11.5.1
=========

- Fix arguments passed to execute method

v0.11.5
=======

+ Add Publisher.execute to make wrapping handler calls easier [also, makes NewRelic simpler to hook in]
+ Allow empty first pages in pagination
+ Added support module for NewRelic

v0.11.4
=======

+ Make content-type detection more forgiving

v0.11.3
=======

+ Make get_page honor limit parameter, but bound it to max_page_size, which defaults to page_size
+ Allow changing the GET param names for page, offset and limit
+ Allow passing page+limit or offset+limit

v0.11.2
=======

+ Added BooleanField
+ Extended tests
+ Force CSRF protection

v0.11.1
=======

+ Changed SerialiserField/ManySerialiserField to replace reduce/restore instead of overriding inflate/deflate methods
+ Fixed broken url pattern for object action
+ Updated fields documentation

v0.11
=====

# WARNING: API breakage
+ Changed deflate_object and deflate_list to object_deflate and list_deflate to avoid potential field deflater name conflict
+ Moved all model related code to models.py
+ Added modelserialiser_factory
+ Updated ModelSerialiserField/ModelManySerialiserField to optionally auto-create a serialiser for the supplied model

v0.10.3
=======

+ Added python2.6 support back [thanks nkuttler]
+ Added more documentation
+ Added Publisher.get_serialiser_kwargs hook
+ Publisher.get_data was renamed to Publisher.get_request_data for clarity

v0.10.2
=======

- Removed leftover debug print

v0.10.1
=======

+ Added Publisher introspection
+ Added LocationHeaderMixin to HTTP classes

v0.10
=====

+ Replaced http subclasses with Exceptional ones
+ Wrap call to handlers to catch Exceptional http responses
- Removed useless cruft form utils

v0.9.1
======

+ Started documentation
+ Added permit_groups decorator
+ Minor speedup in MetaSerialiser

v0.9
====

+ Added permit decorators
+ use string formatting not join - it's slightly faster
- Fixed var name bug in ModelSerialiser.restore_object
- Removed old 'may' auth API

v0.8
====

+ Added create/delete methods to ModelPublisher
+ Added http.STATUS dict/list utility class
# NOTE:  Because this uses OrderedDict nap is no longer python2.6 compatible
+ Renamed HttpResponse subclasses
+ Split out BasePublisher class

v0.7.1
======

+ Use first engine.CONTENT_TYPES as default content type for responses

v0.7
====

+ Added Engine mixin classes
+ Added MsgPack support
+ Added type-casting fields
- Removed custom JSON class

v0.6
====

+ Added index view to API
+ Make render_single_object use create_response
+ Allow create_response to use a supplied response class
- Fixed JSON serialising of date/datetime objects

v0.5
====

+ Added names to URL patterns
+ Added "argument" URL patterns

v0.4
====

+ Added next/prev flags to list meta-data
+ Added tests

v0.3
====

+ Changed to more generic extra arguments in Serialiser

v0.2
====

+ Pass the Publisher down into the Serialiser for more flexibility
+ Allow object IDs to be slugs
- Fixed bug in serialiser meta-class that broke inheritance
+ Handle case of empty request body with JSON content type
- Fixed variable names
+ Added SerialiserField and ManySerialiserField
+ Added Api machinery
+ Changed Serialiser to use internal Meta class
+ Added ModelSerialiser class

v0.1
====

+ Initial release, fraught with bugs :)