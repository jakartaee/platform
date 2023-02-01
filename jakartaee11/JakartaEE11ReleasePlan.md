# **DRAFT** Jakarta EE 11 Release Plan

### Preamble:  

**THIS IS A DRAFT**

Please revisit to keep updated

## Timeline

| | Q1 2023 | Q2 2023 | Q3 2023 | Q4 2023 | Q1 2024 |
|-|---------|---------|---------|---------|---------|
| | | | | | |
| *Components* | Plan Reviews | | | | |
| *Platform* | | Plan Review | | | |
| *All*| | TCK pass w/Security Manager Disabled | | | |
| *All* | | | | Milestones published | | |
| *All* | | | | TCK pass on Java SE 21 | |
| *Components* | | | | Individual Component Spec Ballots | |
| *Platform* | | | | | Platform TCK pass on Java SE 21 |
| *Platform* | | | | | Platform ballot |
| *Platform* | | | | | **Release** |

## Scope ([issue]())
The goal of the Jakarta EE 11 release is to deliver a set of coordinated specifications across the spectrum of Jakarta EE technologies. 

The Platform team sees Jakarta EE 11 as the collection of component Specifications.
Some of these component Specifications are introducing breaking changes to their API, which will require an increase in the Major version of the respective Specification.
Many other component Specifications are introducing updates which are binary compatible and, thus, will only require a Minor version update.
Regardless of the scope of changes, all artifacts for the component and Platform Specifications will be affected -- Specifications, APIs, TCKs, and Compatible Implementations.

## Java SE 21 ([issue]())
Java SE 21 will become the minimum runtime supported by Jakarta EE compatible implementations.

### API Source and Target Level
If a component Specification is planning a Major or Minor version update for Jakarta EE 11, then the recommendation would be to recompile and distribute the specification’s APIs at lowest required of Java SE 17 and Java SE 21.

**Note:**A component specification may be required to recompile to a higher Java SE level than it actually use depending on the specifications it depends on.

**Note:** The Platform API uber jar files will all be compiled at the Java SE 21 source/target levels.
This is consistent with past practices.

### TCK Source Level
The TCKs will be compiled at the Java SE 21 level.

#### Signature Tests
In Jakarta EE 9.1, the framework for performing API Signature tests was updated to make it easier to test Signatures across multiple Java levels.
The framework and/or API tests may need to be tweaked as we continue to learn and experiment with future levels of Java.

### Compatible Implementation (CI) Source Level
How a Compatible Implementation supports the Java SE 21 runtime (or above) will be left as a vendor-defined solution.

## JPMS Module Info classes ([issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/329))
Suggestions on support for JPMS modules were introduced in the Jakarta EE 9 Platform Specification.
It is desired to firm up these suggestions into requirements.
Several discussions via Issues, Mailing Lists, and the Platform call have resulted in these requirements for Jakarta EE 11.
 
* Each individual component specification API provides at least one `module-info.class` following a specified set of conventions:
  * spec module name is `jakarta.<specName>` (reference [names.adoc](https://github.com/jakartaee/specification-committee/blob/master/names.adoc))
  * spec provides JPMS module definition (reliance on automatic modules is not allowed)
  * spec updates provider lookup algorithm to include search on module-path (if applicable)
  * TCK tests should be updated or provided to ensure a properly configured and functional `module-info.class` (guidelines will be provided)
* The Platform and Web Profile Specification API will not provide a platform/profile level `module-info.class` for EE 11
  * Don’t want to set the expectation that implementations must support JPMS at this point
  * Implementations can still experiment with their own aggregator modules

## Standalone Component TCKs ([issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/333))
Each Specification project should own the TCK source and produce the TCK artifacts.
This needs to be done in such a way that the artifacts can be run to validate implementations at the individual specification level, as well as integrated into platform level TCKs.

This is a run-at goal for Jakarta EE 11.
We know that not all Specifications can establish their standalone TCKs in this timeframe.
The Platform TCK can initiate this refactoring by breaking apart the TCK source into separate directories within the Platform TCK repository.
This will help with the eventual move of these TCK directories into their respective component repositories.

## Component Specification Project Releases
As mentioned, many of the Component Specification projects have already declared their intent for either a Major or Minor version update for Jakarta EE 11.
These projects have already submitted or completed their Plan Reviews for inclusion in Jakarta EE 11, and are driving towards a Q1 2024 release.
These updates are outlined in the sections below.

## Deliverables in Jakarta EE 11
The following details the specifications and APIs currently planned for the Jakarta EE 11 Platform and Web Profile.

### Jakarta EE 11 Specifications
List of specifications in Jakarta EE 11 Platform, Jakarta EE 11 Web Profile, and Jakarta EE Core Profile (updated specifications marked with asterisks).

* Jakarta EE Platform 11*
* Jakarta EE Web Profile 11*
* Jakarta EE Core Profile 11*

*TODO: add list of specifications*

<!--
* Jakarta Activation 2.1*
* Jakarta Annotations 2.1* (Web Profile)
* Jakarta Authentication 3.0* (Web Profile)
* Jakarta Authorization 2.1*
* Jakarta Batch 2.1*
* Jakarta Bean Validation 3.0 (Web Profile)
* Jakarta Concurrency 3.0* (Web Profile)
* Jakarta Connectors 2.1*
* Jakarta Contexts and Dependency Injection 4.0*
* Jakarta Debugging Support for Other Languages 2.0 (Web Profile)
* Jakarta Dependency Injection 2.0 (Web Profile)
* Jakarta Enterprise Beans 4.0
* Jakarta Enterprise Beans 4.0 Lite (Web Profile)
* Jakarta Enterprise Web Services 2.0 (Optional)
* Jakarta Expression Language 5.0* (Web Profile)
* Jakarta Interceptors 2.1* (Web Profile)
* Jakarta JSON Binding 3.0* (Web Profile)
* Jakarta JSON Processing 2.1* (Web Profile)
* Jakarta Mail 2.1*
* Jakarta Managed Beans 2.0 (Web Profile)
* Jakarta Messaging 3.1*
* Jakarta Persistence 3.1* (Web Profile)
* Jakarta RESTful Web Services 3.1* (Web Profile)
* Jakarta Security 3.0* (Web Profile)
* Jakarta Server Faces 4.0* (Web Profile)
* Jakarta Server Pages 3.1* (Web Profile)
* Jakarta Servlet 6.0* (Web Profile)
* Jakarta SOAP with Attachments 3.0* (Optional)
* Jakarta Standard Tag Library 3.0* (Web Profile)
* Jakarta Transactions 2.0 (Web Profile)
* Jakarta WebSocket 2.1* (Web Profile)
* Jakarta XML Binding 4.0* (Optional)
* Jakarta XML Web Services 4.0* (Optional)
* Jakarta Web Services Metadata 3.0 (Merged)
-->

### Proposed Updates to Web Profile

### Proposed Updates to Core Profile

### Jakarta EE 11 APIs
The Platform and Web Profile API uber jar files will be re-generated to correspond with the Jakarta EE 11 release designation.
These API uber jar files will be compiled and distributed at the Java 11 source/target levels.  
**Note:** These uber jars will not be modularized, per the earlier discussion.

## Release Milestones
The Jakarta EE 11 Platform release plan covers the Platform and Web Profile specifications.
As stated earlier, all component Specifications which plan a Major or Minor release will be creating their own separate release plans.

### Waves

We are proposing to deliver Jakarta EE 11 in a set of waves similar to those delivered in the previous Jakarta EE releases. These waves are somewhat related to the dependency tree of specifications. We aim to deliver specifications with a low number of dependencies first followed by other specifications.


#### Independent Wave (standalone)

The following specifications can be delivered independently of other apis.

*   Jakarta Annotations
*   Jakarta Concurrency
*   Jakarta Messaging
*   Jakarta Persistence
*   Jakarta Managed Beans


#### Wave 1

The specifications included in Wave 1 are:

*   Jakarta JSON Processing
*   Jakarta Dependency Injection (Service release for module-info)
*   Jakarta Expression Language
*   Jakarta Bean Validation (Service release for module-info)
*   Jakarta WebSocket
*   Jakarta Servlet
*   Jakarta Activation
*   Jakarta SOAP with Attachments
*   Jakarta Interceptors (Service release for module-info)


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
*   Jakarta Transactions (Service release for module-info)


#### Wave 5

The specifications included in Wave 5 are:

*   Jakarta Connectors
*   Jakarta Standard Tag Library
*   Jakarta Enterprise Beans (Service release for module-info)
*   Jakarta Enterprise Web Services


#### Wave 6

The specifications included in Wave 6 are:

*   Jakarta Security
*   Jakarta Server Faces


#### Wave 7

The specifications included in Wave 7 are:

*   Jakarta EE 10 Core Profile
*   Jakarta EE 10 Web Profile
*   Jakarta EE 10 Full Platform


### Platform and Web Profile Release Candidate

With the rather large Jakarta EE 11 release scope, at least one Release Candidate for Jakarta EE Platform and Web Profile will be produced.
These Release Candidates will include:

* Release candidates for all API JARs in Maven Central
* Release candidate Bill of Material pom files for Web Profile and Full Platform in Maven Central
* Release candidate TCKs
* Release candidate compatible implementation(s)

Once the release candidates have been validated and any issues ironed out, the full Jakarta EE 11 release will proceed with all deliverables required for submission to the specification committee for approval.

### Proposed Progress Reviews


### Compatible Implementation          

The JESP requires us to have a Compatible Implementation of the Full Platform and Web Profile available before the Platform Project can deliver a final Specification. Discussions are occurring with the Specification Committee to allow for additional ratified compatible implementations (besides always relying on Eclipse Glassfish).
The Platform project has no control over the release dates of any potential Compatible Implementations.
The platform project will maintain close coordination with the various Compatible Implementations for the duration of the Jakarta EE 11 release cycle.

### FAQ

Additional clarifications for this Release Plan can be found in the [Jakarta EE 11 Release Plan FAQ](https://eclipse-ee4j.github.io/jakartaee-platform/jakartaee11/JakartaEE11ReleasePlanFAQ).
