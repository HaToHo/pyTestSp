===========
Service Provider (SP) based on pysaml2 (https://github.com/rohe/pysaml2.git) by Roland Hedberg.
===========
The SP works with a metadata file that contains multiple Identity Providers (IdP).

For documentation how the SP can be configured look at pysaml2.


The extension from pysaml2
---------------------------

In the file who.ini add the parameter:
idp_query_param = IdPEntityId

This allows the plugin to look for the a specific entity id for an IdP on the query string.

http://localhost:8087?IdpEntityId=http://localhost:1212/myIdpEntityId.xml

In this case the IdP with entity id http://localhost:1212/myIdpEntityId.xml will be used.

In the case no IdP i chosen:

http://localhost:1212/

The SP will return a page where the end user may choose the IdP to use in a drop down.

This is performed by the method chooseIdp in sp.py.