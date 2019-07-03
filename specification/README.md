Jakarta EE Platform Specification
=================================

This project generates the Jakarta EE Platform Specification
the Jakarta EE Web Profile Specification, and the Managed Beans
Specification.

> NOTE:  The Managed Bean Specification is not being generated presently.
> A skeletal Specification based on the Javadoc will be necessary.

Building
--------

Prerequisites:

* JDK8+
* Maven 3.0.3+

Run the full build:

`mvn install`

Locate the html files:
- `target/generated-docs/Platform-spec-<version>.html`
- `target/generated-docs/WebProfile-spec-<version>.html`
- `target/generated-docs/ManagedBeans-spec-<version>.html`

Locate the PDF files:
- `target/generated-docs/Platform-spec-<version>.pdf`
- `target/generated-docs/WebProfile-spec-<version>.pdf`
- `target/generated-docs/ManagedBeans-spec-<version>.pdf`
