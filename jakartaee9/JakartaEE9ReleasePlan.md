<!----- Conversion time: 1.477 seconds.

Using this Markdown file:

1. Cut and paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β17
* Thu Dec 19 2019 11:46:45 GMT-0800 (PST)
* Source doc: https://docs.google.com/open?id=18cwfYhEqv_msIdH1DSVDXJc-QaUJ6zjPgmG6JHfLRrA
----->

# Jakarta EE 9 Release Plan


## Scope

The goal of the Jakarta EE 9 release is to deliver a set of specifications functionally similar to Jakarta EE 8 but in the new Jakarta EE 9 namespace `jakarta.*`.

In addition, the Jakarta EE 9 release removes specifications from Jakarta EE 8 that were old, optional, or deprecated in order to reduce the surface area of the APIs to ensure that it is easier for new vendors to enter the ecosystem -- as well as reduce the burden on implementation, migration, and maintenance of these old APIs.

Predominantly, the project team sees Jakarta EE 9 as a tooling release:

*   A platform from which tooling vendors can create and update their tools to support the new `jakarta.* `namespace.
*   A platform that development teams can use as a stable target for testing migration of their applications to the new namespace.
*   A platform that runtime vendors can use to test and deliver options and capabilities that support migration and backwards compatibility with Jakarta EE 8.
*   A foundation for innovation that Jakarta EE specification projects can use to drive new features for release in Jakarta EE 10 and beyond.

The scope of the Jakarta EE 9 release takes into account the guidance resolution passed by the Jakarta EE Working Group Steering committee shown below:

> _**RESOLVED**, the Jakarta EE Steering Committee requests that the Jakarta EE Platform Project leadership deliver a Jakarta EE 9 Delivery Plan to the Steering Committee no later than **December 9, 2019**, for the Steering Committee to consider adopting as the roadmap for Jakarta EE 9, and that the Jakarta EE 9 Delivery Plan accommodates the following constraints:_
>
> *   _implements the big bang_
> *   _Includes an explicit means to identify and enable specifications that are unnecessary or unwanted to be deprecated or removed_
> *   _Moves all remaining specification APIs to the Jakarta namespace_
> *   _States that no new specifications are to be added, apart from specifications pruned from Java SE 8 where appropriate, unless those specifications clearly will not impact the target delivery date_


### Namespace Changes

To be included in the Jakarta EE 9 release a specification MUST move their API package names from the top level `javax `package to the top level `jakarta `package. Other changes SHOULD NOT be made to the APIs defined in the specification apart from changes required to support the complete removal of specifications that have been pruned from this release. Methods SHOULD be removed and schema documents updated when they refer to APIs pruned from Jakarta EE 9.  Any exceptions to this process will require individual Component Plan Reviews.


### Specification Documents

Individual specifications included within the scope of the Jakarta EE 9 Full Profile or Web Profile SHOULD convert the specification documents received by the Eclipse Foundation to the Jakarta namespace and refer to other Jakarta specifications and release these specification documents as part of the Jakarta EE 9 release.


### Backwards Compatibility

Jakarta EE 9 WILL NOT impose any backward compatibility requirements for compatible implementations to support the Jakarta EE 8 release. This is aligned with our goal of enabling new implementations to enter the ecosystem. However, we strongly believe that many products and tools will provide backwards compatibility and migration solutions for enabling older applications to run on Jakarta EE 9.


### Java SE Version

For inclusion in Jakarta EE 9, specification’s APIs MUST be compiled at the Java SE 8 source level.  Compatible Implementations of the Jakarta EE 9 Platform and Web Profile MUST certify compatibility on Java SE 8. Compatible Implementations MAY additionally certify and support later versions of the Java SE runtime.


### Individual Specification Versioning

As a move to the Jakarta EE namespace is a breaking change, all specifications included in the Jakarta EE 9 release MUST release a new major version of the specification document, APIs, and other artifacts. For example, semantic versioning at the specification level (ie. JPA 2.x -> 3.0), maven artifact level  and semantic versioning at the Package level (OSGI) if appropriate for the specification (ie. `jakarta.persistence` at 3.0.0)


## Specifications Included in Jakarta EE 9

The following details the specifications included within the Full Profile of Jakarta EE 9.


### Updated in Jakarta EE 9

List of existing specifications in Jakarta EE 9:

*   Jakarta Annotations
*   Jakarta Concurrency
*   Jakarta Messaging
*   Jakarta Persistence
*   Jakarta JSON Processing
*   Jakarta Dependency Injection
*   Jakarta Expression Language
*   Jakarta Bean Validation
*   Jakarta WebSocket
*   Jakarta Servlet
*   Jakarta Managed Beans
*   Jakarta Mail
*   Jakarta Authentication
*   Jakarta JSON Binding
*   Jakarta Server Pages
*   Jakarta Debugging Support for Other Languages
*   Jakarta Authorization
*   Jakarta Interceptors
*   Jakarta Contexts and Dependency Injection
*   Jakarta Batch
*   Jakarta RESTful Web Services
*   Jakarta Transactions
*   Jakarta Connectors
*   Jakarta Standard Tag Library
*   Jakarta Enterprise Beans
*   Jakarta Enterprise Web Services
*   Jakarta Security
*   Jakarta Server Faces
*   Jakarta EE 9 Full Platform
*   Jakarta EE 9 Web Profile


### Specifications Added to Jakarta EE 9

The following specifications previously part of Java SE 8 will be added to Jakarta EE 9 either as required or optional specifications as indicated and MUST be moved to the `jakarta` namespace.

*   Jakarta Activation (Required)
*   Jakarta XML Binding (Optional)
*   Jakarta XML Web Services (Optional)
*   Jakarta Web Services Metadata (Optional)
*   Jakarta SOAP with Attachments (Optional)


### Specifications marked Optional in Jakarta EE 9

Specifications marked optional in Jakarta EE 9 in addition to those added above and marked Optional above are:

*   Jakarta Enterprise Beans 2.x API group
*   Jakarta Enterprise Web Services, JSR 109


### Specifications Pruned in Jakarta EE 9

List of specifications pruned in Jakarta EE 9:

*   Jakarta Stable API Project Specifications
    *   Jakarta XML Registries
    *   Jakarta XML RPC
    *   Jakarta Deployment
    *   Jakarta Management
*   Support for Distributed Interoperability in the EJB 3.2 Core Specification, Chapter 10


## Release Milestones

The Jakarta EE 9 platform project is proposing that this release plan covers all specifications targeted for Jakarta EE 9. As stated in the scope, specifications will not be making functionality changes for inclusion in this release therefore individual specification release plans would be unnecessary ceremony. However, we are proposing that final Release Reviews are carried out individually for each specification to ensure artifacts are present.


### Waves

We are proposing to deliver Jakarta EE 9 in a set of waves similar to those delivered in the Jakarta EE 8 release. These waves are somewhat related to the dependency tree of specifications. We aim to deliver specifications with a low number of dependencies first followed by other specifications.


#### Independent Wave (standalone)

The following specifications can be delivered independently of other apis.

*   Jakarta Annotations
*   Jakarta Concurrency
*   Jakarta Messaging
*   Jakarta Persistence
*   Jakarta Managed Beans
*   Jakarta Web Services Metadata


#### Wave 1

The specifications included in Wave 1 are:

*   Jakarta JSON Processing
*   Jakarta Dependency Injection
*   Jakarta Expression Language
*   Jakarta Bean Validation
*   Jakarta WebSocket
*   Jakarta Servlet
*   Jakarta Activation
*   Jakarta SOAP with Attachments
*   Jakarta Interceptors


#### Wave 2

The specifications included in Wave 2 are:

*   Jakarta Mail
*   Jakarta Authentication
*   Jakarta JSON Binding
*   Jakarta Server Pages
*   Jakarta Debugging Support for Other Languages
*   Jakarta Authorization
*   Jakarta XML Binding


#### Wave 3

The specifications included in Wave 3 are:

*   Jakarta Contexts and Dependency Injection
*   Jakarta XML Web Services


#### Wave 4

The specifications included in Wave 4 are:

*   Jakarta Batch
*   Jakarta RESTful Web Services
*   Jakarta Transactions


#### Wave 5

The specifications included in Wave 5 are:

*   Jakarta Connectors
*   Jakarta Standard Tag Library
*   Jakarta Enterprise Beans
*   Jakarta Enterprise Web Services


#### Wave 6

The specifications included in Wave 6 are:

*   Jakarta Security
*   Jakarta Server Faces


#### Wave 7

The specifications included in Wave 7 are:

*   Jakarta EE 9 Full Platform
*   Jakarta EE 9 Web Profile


### Milestone Builds

Jakarta EE specification projects MUST deliver milestone and RC builds to Maven Central with the namespace change as soon as possible to enable dependent projects to proceed with their required namespace change.

Jakarta EE specification projects COULD make full standalone releases of their specifications along with all finalized artifacts after following the JESP in advance of the full Jakarta EE 9 Platform releases.

Plan progress will be tracked in a GitHub project board at the Eclipse EE4J organization level. Milestones for each specification will be tracked across the project board columns.


### Full Profile and Web Profile Release Candidate

It is the intention of the project team to deliver one or more release candidates of both the Full Profile and the Web Profile after the conclusion of Wave 7. The Profile Release candidates will include:

*   Release candidates for all API JARs in Maven Central
*   Release candidate Bill of Material pom files for Web and Full Profiles in Maven Central
*   Release candidate TCKs
*   Release candidate compatible implementation(s)

The purpose of the release candidate is to enable tools and users to try out the new APIs and discover any problems and inconsistencies prior to full release. We aim to leave a period of two months between the first release candidate and the final release to gather feedback and correct any minor problems prior to final release. Once the release candidate has been validated and any issues ironed out, the full release will proceed with all deliverables required for submission to the specification committee for approval.


### Proposed Progress Reviews

The project team believe this timeline is aggressive and these are **_early estimate dates_** which will be reviewed and adjusted at each release review.

1. Individual Component Plan Reviews (Feb 1)
2. All API jars available (Feb 14th)
3. Platform TCK changes complete (March 13th)
4. Full Profile and Web Profile First Release Candidate (May 4th)
5. Full Profile and Web Profile Final Release Review Votes Start (June 12th)

**Update:** These were the original ***proposed*** progress review dates at the time of the finalized Release Plan (Dec 2019).
The overall schedule for Jakarta EE 9 will now be maintained on [this separate page](https://eclipse-ee4j.github.io/jakartaee-platform/jakartaee9/JakartaEE9#jakarta-ee-9-schedule).

### Compatible Implementation          

The JESP requires us to have a Compatible Implementation of the Full Profile and Web Profile available before the Platform Project can deliver a final specification. At this stage, it is assumed that this implementation will be Eclipse GlassFish. However, the Platform project has no control over the release dates of Eclipse GlassFish. The platform project will maintain close coordination with the Eclipse GlassFish project for the duration of the Jakarta EE 9 release development.


<!-- Docs to Markdown version 1.0β17 -->

## FAQ

Additional clarifications for this Release Plan can be found in the [Jakarta EE 9 Release Plan FAQ](https://eclipse-ee4j.github.io/jakartaee-platform/jakartaee9/JakartaEE9ReleasePlanFAQ).
