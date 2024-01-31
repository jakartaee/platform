# Jakarta EE 11 Release Plan

### Preamble

## Timeline

|              | Q1 2023      | Q2 2023 | Q3 2023     | Q4 2023 | Q1 2024 | Q2 2024 | June/July 2024  |
|--------------|--------------|---------|-------------|---------|---------|---------|-----------------|
| *Components* | Plan Reviews |         |             |         |         |         |                 |
| *Platform*   |              |         | Plan Review |         |         |         |                 |
| *All*        |              |         |             | TCK pass w/Security Manager Disabled |    | | |
| *All*        |              |         |             | M1 release |      |         |                 |
| *All*        |              |         |             |         | Wave 1, 2, 3, 4 specs release review initiated by 2024-02-29 | | |
| *All*        |              |         |             |         | M2 release | | |
| *All*        |              |         |             |         | Wave 5 specs release review initiated by 2024-03-29 | | |
| *All*        |              |         |             |         | M3 release | | |
| *Components* |              |         |             |         | Each Wave 1 - 5 component spec has an impl that passes its TCK on Java SE 17 and an impl that passes its TCK on Java SE 21. These need not be the same impl. |          | |
| *Components* |              |         |             |         | | Each Wave 6, 7 component spec has an impl that passes its TCK on Java SE 17 and an impl that passes its TCK on Java SE 21. These need not be the same impl. |          |
| *All*        |              |         |             |         | | Wave 6, 7 specs release review initiated by 2024-04-27 | |
| *All*        |              |         |             |         | | M4 release | |
| *Components* |              |         |             |         | | Individual component spec ballots completed | |
| *Platform*   |              |         |             |         | | Platform TCK ready to run on Java SE 21 and Java SE 17 | |
| *Components* |              |         |             |         |         | Further refine implementations | |
| *Platform*   |              |         |             |         |         |         | Platform ballot |
| *Platform*   |              |         |             |         |         |         | Web Platform ballot |
| *Platform*   |              |         |             |         |         |         | Core Platform ballot |
| *Platform*   |              |         |             |         |         |         | **Release**     |

For all milestone releases after M1:
* specs that are slated to have release review initiated before that milestone will include their final versions in the milestone.
* all other specs will include the latest version they have on hand. (Ed and Arjan commit to do the release work for this case, if necessary.)

## Scope ([issue]())
The goal of the Jakarta EE 11 release is to deliver a set of coordinated specifications across the spectrum of Jakarta EE technologies. 

The Platform team sees Jakarta EE 11 as the collection of component Specifications.
Some of these component Specifications are introducing breaking changes to their API, which will require an increase in the Major version of the respective Specification.
Many other component Specifications are introducing updates which are binary compatible and, thus, will only require a Minor version update.
Regardless of the scope of changes, all artifacts for the component and Platform Specifications will be affected -- Specifications, APIs, TCKs, and Compatible Implementations.

## Java SE ([issue]())
Java SE 17 will become the minimum runtime supported by compatible implementations of Jakarta EE.

## Jakarta Data
Jakarta EE 11 plans to include Jakarta Data in its platform specification. For more on Jakarta Data see [Jakarta Data](https://jakarta.ee/specifications/data/).

## CDI
Continue to make CDI the single component model used across all of EE by removing Managed Beans from Annotations and all callsites that use Managed Beans.

With the help of the platform project, the CDI project will do the work to move all aspects of CDI that deal with integrating CDI with other specifications out of the CDI spec and into the platform spec or appropriate profile spec. The remaining content will still be called CDI.  For more information see the [CDI issue tracker](https://github.com/jakartaee/cdi/issues/687#issuecomment-1667009015).

### API Source Code `--release` Level

For the Jakarta EE Platform (Platform, Web and Core), the Java compiler `--release` option is 17. For the component specs, the Jakarta EE Platform requires the Java compiler `--release` option is **at most** 17, but component specifications can decide on a lower level.

### TCK Source Level

- Component spec TCKs and platform TCK must compile at Java 17 or less.
- A compatible component impl must pass their component TCK when run under Java 17 or 21.
   - To ratify a component specification, there must exist an implementation that passes on Java 17. There must also exist an implementation that passes on 21.
   - These need not be the same implementation. There can be one implementation that passes on 17 and a different one that passes on 21.
- A compatible platform impl must pass the platform TCK when run under 17 or 21.
   - To ratify a platform specification, there must exist an implementation that passes on 17. There must also exist an implementation that passes on 21.
   - These need not be the same implementation. There can be one implementation that passes on 17 and a different one that passes on 21.

#### Signature Tests
In Jakarta EE 9.1, the framework for performing API Signature tests was updated to make it easier to test Signatures across multiple Java levels.
The framework and/or API tests may need to be tweaked as we continue to learn and experiment with future levels of Java.

### Compatible Implementation (CI) Source Level

The long-standing policy of considering specification API binaries, in Maven Central or anywhere else, as a non-normative convenience remains unchanged. The platform project is silent on this matter. However, because the platform project does mandate a specific JDK requirement for compatible implementations passing the component or platform TCK, if a component specification does publish an API binary, that binary is practically constrained to follow that mandate." See [TCK Source Level](#tck-source-level)

## JPMS Module Info classes ([issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/329))
Suggestions on support for JPMS modules were introduced in the Jakarta EE 9 Platform Specification.
It is desired to firm up these suggestions into requirements.
Several discussions via Issues, Mailing Lists, and the Platform call have resulted in these requirements for Jakarta EE 11.
 
* Each individual component specification API provides at least one `module-info.class` following a specified set of conventions:
  * spec module name is `jakarta.<specName>` (reference [names.adoc](https://github.com/jakartaee/specification-committee/blob/master/names.adoc))
  * spec provides JPMS module definition (reliance on automatic modules is not allowed)
  * spec updates provider lookup algorithm to include search on module-path (if applicable)
* The Platform and Web Profile Specification API will not provide a platform/profile level `module-info.class` for EE 11
  * Don’t want to set the expectation that implementations must support JPMS at this point
  * Implementations can still experiment with their own aggregator modules

## Standalone Component TCKs ([issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/333))
Each Specification project should own the TCK source and produce the TCK artifacts.
This needs to be done in such a way that the artifacts can be run to validate implementations at the individual specification level, as well as integrated into platform level TCKs.

We know that not all Specifications can establish their standalone TCKs in this timeframe.

The Platform TCK can initiate this refactoring by breaking apart the TCK source into separate directories within the Platform TCK repository.

This will help with the eventual move of these TCK directories into their respective component repositories.

## Component Specification Project Releases
As mentioned, many of the Component Specification projects have already declared their intent for either a Major or Minor version update for Jakarta EE 11.
These projects have already submitted or completed their Plan Reviews for inclusion in Jakarta EE 11, and are driving towards a H2 2024 release.
These updates are outlined in the sections below.

## Deliverables in Jakarta EE 11
The following details the specifications and APIs currently planned for the Jakarta EE 11 Platform and Web Profile.

### Jakarta EE 11 Specifications
List of specifications in Jakarta EE 11 Platform, Jakarta EE 11 Web Profile, and Jakarta EE Core Profile (updated specifications marked with asterisks).

- Jakarta EE Platform 11*
- Jakarta EE Web Profile 11*
- Jakarta EE Core Profile 11*

- Jakarta CDI 4.1*
- Jakarta Data 1.0*
- Jakarta Activation 2.1.2* service release
- Jakarta Annotations 3.0*
- Jakarta Authentication 3.1*
- Jakarta Authorization 3.0*
- Jakarta Batch 2.1
- Jakarta Concurrency 3.1*
- Jakarta Connectors 2.1
- Jakarta Debugging Support for Other Languages 2.0
- Jakarta Dependency Injection 2.0.1
- Jakarta Enterprise Beans 4.0.1
- Jakarta Expression Language 6.0
- Jakarta Faces 4.1*
- Jakarta Interceptors 2.2*
- Jakarta JSON Binding 3.0
- Jakarta JSON Processing 2.1.2* service release
- Jakarta Lang Model 4.0.1
- Jakarta Mail 2.1.2* service release
- Jakarta Messaging 3.1
- Jakarta Persistence 3.2*
- Jakarta RESTful Web Services 4.0*
- Jakarta SOAP with Attachments 3.0
- Jakarta Security 4.0*
- Jakarta Server Pages 4.0*
- Jakarta Servlet 6.1*
- Jakarta Standard Tag Library 3.0
- Jakarta Transactions 2.0.1
- Jakarta Validation 3.1*
- Jakarta WebSocket 2.2*
- Jakarta XML Binding 4.0
- Jakarta XML Web Services 4.0

### Proposed Updates to Platform

- Jakarta CDI
- Jakarta Data 1.0
- Jakarta Activation
- Jakarta Annotations
- Jakarta Authentication
- Jakarta Authorization
- Jakarta Concurrency
- Jakarta Faces
- Jakarta Interceptors
- Jakarta JSON Processing
- Jakarta Mail
- Jakarta Persistence
- Jakarta RESTful Web Services
- Jakarta Security
- Jakarta Server Pages
- Jakarta Servlet
- Jakarta Transactions
- Jakarta Validation
- Jakarta WebSocket

### Proposed Updates to Web Profile

- Jakarta CDI
- Jakarta Annotations
- Jakarta Validation
- Jakarta Concurrency
- Jakarta Authentication
- Jakarta Interceptors
- Jakarta JSON Processing
- Jakarta Persistence
- Jakarta RESTful Web Services
- Jakarta Security
- Jakarta Faces
- Jakarta Server Pages
- Jakarta Servlet
- Jakarta WebSocket

### Proposed Updates to Core Profile

- Jakarta CDI
- Jakarta Annotations
- Jakarta Interceptors
- Jakarta JSON Processing
- Jakarta RESTful Web Services

### Jakarta EE 11 APIs
The Platform and Web Profile API uber jar files will be re-generated to correspond with the Jakarta EE 11 release designation.
These API uber jar files will be compiled and distributed at the Java 11 source/target levels.  
**Note:** These uber jars will not be modularized, per the earlier discussion.

## Release Milestones
The Jakarta EE 11 Platform release plan covers the Platform and Web Profile specifications.
As stated earlier, all component Specifications which plan a Major or Minor release will be creating their own separate release plans.

### Waves

We are proposing to deliver Jakarta EE 11 in a set of waves similar to those delivered in the previous Jakarta EE releases. These waves are somewhat related to the dependency tree of specifications. We aim to deliver specifications with a low number of dependencies first followed by other specifications. (updated specifications marked with asterisks)

#### Wave 1

- Jakarta Annotations*
- Jakarta JSON Processing* (service release)

#### Wave 2

- Jakarta Expression Language*
- Jakarta Interceptors*
- Jakarta Lang Model* (may be released with Jakarta CDI [Core] in wave 3)

#### Wave 3

- Jakarta Activation* (service release)
- Jakarta Contexts and Dependency Injection*

#### Wave 4

- Jakarta JSON Binding
- Jakarta Mail* (service release)
- Jakarta SOAP with Attachments
- Jakarta XML Binding

#### Wave 5

- Jakarta Authorization*
- Jakarta Batch
- Jakarta Persistence*
- Jakarta RESTful Web Services*
- Jakarta Server Pages*
- Jakarta Servlet*
- Jakarta Validation*
- Jakarta WebSocket*
- Jakarta XML Web Services

#### Wave 6

- Jakarta Authentication*
- Jakarta Concurrency*
- Jakarta Faces*
- Jakarta Messaging
- Jakarta Standard Tag Library

#### Wave 7

- Jakarta Security*
- Jakarta Data*

#### Wave 8

- Jakarta Platform* (including appropriate content formerly in CDI EE)
- Jakarta Web Profile* (including appropriate content formerly in CDI EE)
- Jakarta Core Profile*

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

Additional clarifications for this Release Plan can be found in the [Jakarta EE 11 Release Plan FAQ](https://jakartaee.github.io/platform/jakartaee11/JakartaEE11ReleasePlanFAQ).

