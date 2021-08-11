# Jakarta EE 10 Release Plan

### Preamble:  
_Jakarta EE 10 is the first major release of Jakarta EE since the “jakarta” namespace update.
Many of the component Specifications are introducing Major or Minor version updates to signify key changes in their respective Specifications and APIs.
The Platform and/or Web Profile Specifications will be incorporating many of these updated Specifications._

## Scope ([issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/352))
The goal of the Jakarta EE 10 release is to deliver a set of coordinated specifications across the spectrum of Jakarta EE technologies. 

The Platform team sees Jakarta EE 10 as the collection of component Specifications.
Some of these component Specifications are introducing breaking changes to their API, which will require an increase in the Major version of the respective Specification.
Many other component Specifications are introducing updates which are binary compatible and, thus, will only require a Minor version update.
Regardless of the scope of changes, all artifacts for the component and Platform Specifications will be affected -- Specifications, APIs, TCKs, and Compatible Implementations.

### Core Profile ([issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/387))
Complementing the Web Profile, a new profile called the Core Profile is being proposed for Jakarta EE 10.
The goal of the Core Profile is to define a subset of the Jakarta EE technologies which target microservices development and runtimes.
It is still not clear if the Core Profile will be released in sync with the Web and Platform specifications.
A separate release plan will be developed, circulated, and balloted for the Core Profile.

## Java SE 11 ([issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/331))
Java SE 11 will become the minimum runtime supported by Jakarta EE compatible implementations.

### API Source and Target Level
If a component Specification is planning a Major or Minor version update for Jakarta EE 10, then the recommendation would be to recompile and distribute the specification’s APIs at the Java SE 11 source and target levels.
This is not a requirement since there may be reasons to continue compiling and distributing the APIs at an earlier Java source or target level.

**Note:** The Platform API uber jar files will all be compiled at the Java SE 11 source/target levels.
This is consistent with past practices.
These uber jar files will be deprecated for Jakarta EE 10 to allow for possible removal in a future release.

### TCK Source Level
The TCKs will be compiled at the Java SE 11 level.
In order to allow for runtimes beyond Java SE 11, the TCK will also need to be (successfully) executed with Java SE 17.

#### Signature Tests
In Jakarta EE 9.1, the framework for performing API Signature tests was updated to make it easier to test Signatures across multiple Java levels.
The framework and/or API tests may need to be tweaked as we continue to learn and experiment with future levels of Java.

### Compatible Implementation (CI) Source Level
How a Compatible Implementation supports the Java SE 11 runtime (or above) will be left as a vendor-defined solution.

## JPMS Module Info classes ([issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/329))
Suggestions on support for JPMS modules were introduced in the Jakarta EE 9 Platform Specification.
It is desired to firm up these suggestions into requirements.
Several discussions via Issues, Mailing Lists, and the Platform call have resulted in these requirements for Jakarta EE 10.
 
* Each individual component specification API provides at least one `module-info.class` following a specified set of conventions:
  * spec module name is `jakarta.<specName>` (reference [names.adoc](https://github.com/jakartaee/specification-committee/blob/master/names.adoc))
  * spec provides JPMS module definition (reliance on automatic modules is not allowed)
  * spec updates provider lookup algorithm to include search on module-path (if applicable)
  * TCK tests should be updated or provided to ensure a properly configured and functional `module-info.class` (guidelines will be provided)
* The Platform and Web Profile Specification API will not provide a platform/profile level `module-info.class` for EE 10
  * Don’t want to set the expectation that implementations must support JPMS at this point
  * Implementations can still experiment with their own aggregator modules

## “Removal” of Two EJB Features
The number of compatible implementations available for specification ratification is limited due to the requirement that all optional features need to be implemented and verified via the TCK.
This is a current restriction due to the EFSP and our Platform specification.
The EFSP is being worked on via [this issue](https://github.com/EclipseFdn/EFSP/issues/22) and should be resolved in the next iteration of the EFSP.

For the Platform specification, the following two features will be tagged as “removed” or “deprecated” (exact term and/or mechanism still needs to be determined).
* EJB Entity Beans (CMP and BMP)
* Embeddable EJB Container

The idea behind this tagging is to indicate that these features will no longer be required for specification ratification.
These features will still be documented as “optional” in the EJB specification.
And, the TCKs will still be available for verifying implementations that choose to implement these features.
The Platform specification will be updated to properly reflect that these features will not be required for ratifying compatible implementations.

## Standalone Component TCKs ([issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/333))
Each Specification project should own the TCK source and produce the TCK artifacts.
This needs to be done in such a way that the artifacts can be run to validate implementations at the individual specification level, as well as integrated into platform level TCKs.

This is a run-at goal for Jakarta EE 10.
We know that not all Specifications can establish their standalone TCKs in this timeframe.
The Platform TCK can initiate this refactoring by breaking apart the TCK source into separate directories within the Platform TCK repository.
This will help with the eventual move of these TCK directories into their respective component repositories.

## Component Specification Project Releases
As mentioned, many of the Component Specification projects have already declared their intent for either a Major or Minor version update for Jakarta EE 10.
These projects have already submitted or completed their Plan Reviews for inclusion in Jakarta EE 10, and are driving towards a 4Q2021 release.
These updates are outlined in the sections below.

## Deliverables in Jakarta EE 10
The following details the specifications and APIs currently planned for the Jakarta EE 10 Platform and Web Profile.

### Jakarta EE 10 Specifications
List of specifications in Jakarta EE 10 Platform and Web Profile (updated specifications marked with asterisks).

* Jakarta EE Platform 10*
* Jakarta EE Web Profile 10*
* Jakarta Activation 2.1*
* Jakarta Annotations 2.0 (Web Profile)
* Jakarta Authentication 3.0* (Web Profile)
* Jakarta Authorization 3.0*
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
* Jakarta Interceptors 2.0 (Web Profile)
* Jakarta JSON Binding 2.1* (Web Profile)
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

### Proposed Updates to Web Profile
* Move Concurrency 3.0* from Platform to Web Profile 10* ([issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/363#issuecomment-846424050))

### Jakarta EE 10 APIs
The Platform and Web Profile API uber jar files will be re-generated to correspond with the Jakarta EE 10 release designation.
These API uber jar files will be compiled and distributed at the Java 11 source/target levels.  
**Note:** These uber jars will not be modularized, per the earlier discussion.

## Release Milestones
The Jakarta EE 10 Platform release plan covers the Platform and Web Profile specifications.
As stated earlier, all component Specifications which plan a Major or Minor release will be creating their own separate release plans.

### Full Platform and Web Profile Release Candidate

With the rather large Jakarta EE 10 release scope, at least one Release Candidate for Jakarta EE Platform and Web Profile will be produced.
These Release Candidates will include:

* Release candidates for all API JARs in Maven Central
* Release candidate Bill of Material pom files for Web Profile and Full Platform in Maven Central
* Release candidate TCKs
* Release candidate compatible implementation(s)

Once the release candidates have been validated and any issues ironed out, the full 10 release will proceed with all deliverables required for submission to the specification committee for approval.

### Proposed Progress Reviews

Since this Jakarta EE 10 release is rather large, a progress review will most likely occur as the content becomes more firm.
The overall schedule for Jakarta EE 10 will be maintained on [this separate page](https://eclipse-ee4j.github.io/jakartaee-platform/jakartaee10/JakartaEE10#jakarta-ee-10-schedule).

### Compatible Implementation          

The JESP requires us to have a Compatible Implementation of the Full Platform and Web Profile available before the Platform Project can deliver a final Specification. Discussions are occurring with the Specification Committee to allow for additional ratified compatible implementations (besides always relying on Eclipse Glassfish).
The Platform project has no control over the release dates of any potential Compatible Implementations.
The platform project will maintain close coordination with the various Compatible Implementations for the duration of the Jakarta EE 10 release cycle.

### FAQ

Additional clarifications for this Release Plan can be found in the [Jakarta EE 10 Release Plan FAQ](https://eclipse-ee4j.github.io/jakartaee-platform/jakartaee10/JakartaEE10ReleasePlanFAQ).
