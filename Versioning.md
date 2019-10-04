# Versioning

This document describes the versioning rules used by the Jakarta EE project.

We apply version numbers to two of the JESP-defined artifacts -
specification document and technology
compatibility kit (TCK). At the completion of an update to a
technology, both artifacts will have the same base version number.
The specification will have a version number in the single dot
_major.minor_ format.
The TCK will have a version number in the two dot format _major.minor.micro_,
with a micro version number of zero.

Between JCP updates, each of these artifacts may also be updated,
following these rules:

### Specification document

Updates to a specification document that do not change the meaning of
the specification are called "errata". (See [JCP Processes](JCP Processes)
for details.) An errata update to a specification document is indicated
by including a "Rev level" after the specification version number.  For
example, if an initial specification numbered "1.0" is updated by an
errata, the updated document would be given a number of "1.0 Rev a".  A
subsequent errata update would be "1.0 Rev b".  Note that since an
errata typically does not require a change to any compatible implementation
or the TCK, a Rev level is **never** applied to those artifacts.

To summarize...

For a spec of version X.Y, the spec document will be version "X.Y" for
the initial release or "X.Y Rev L", where "L" is a letter nominally
starting with "a" and incrementing as more errata are approved via
the Jakarta EE Specification Process.

### Technology Compatibility Kit

Any update to a TCK corresponding to a particular specification version
will increment the micro version number of the TCK.
In particular, updates to the exclude list of the TCK will result in a
new version of the TCK with an updated micro version number.

## Schema and DTD versioning

Schema and DTD files (both standard-defined and product-specific) are
named using a base name appropriate for the descriptor and an extension
appropriate for the type (.dtd or .xsd). The base name should be all
lower case with words separated by dashes (e.g., "web-app").

The file name also **must** include a version number after the base name,
separated from the base name by an underscore. If the version of the
spec is "X.Y", the file name version number would be "X_Y". For the
Jakarta EE platform version "X", the file name version would be simply "X".

Updates to the product-specific descriptor schema or DTD files that
happen between spec updates must include a revision number after the
version number, separated by a dash.

Examples:
* javaee_6.xsd - the main schema file for Java EE 6
* web-app_3_0.xsd - the web application descriptor defined by Servlet 3.0
* glassfish-web-app_3_0-1.dtd - an updated version of the
  GlassFish-specific web application descriptor corresponding to Servlet 3.0.

We haven't been consistent in whether the first version of a product-specific
descriptor should include a revision of "-0" or just omit the revision number.
