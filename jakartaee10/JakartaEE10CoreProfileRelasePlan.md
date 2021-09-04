# Jakarta EE 10 Core Profile Release Plan

## Scope ([issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/352))
The goal of the Jakarta EE 10 release is to deliver a set of coordinated specifications across the spectrum of Jakarta EE technologies.

## The Core Profile ([issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/387))
The Core Profile is focused on providing a minimal basis for cloud native runtimes, including runtimes that support build time applications.

## Java SE 11 ([issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/331))
Java SE 11 will become the minimum runtime supported by Jakarta EE compatible implementations.


### API Source and Target Level
If a component Specification is planning a Major or Minor version update for Jakarta EE 10, then the recommendation would be to recompile and distribute the specification’s APIs at the Java SE 11 source and target levels.
This is not a requirement since there may be reasons to continue compiling and distributing the APIs at an earlier Java source or target level.

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
* The Core Profile Specification API will not provide a profile level `module-info.class` for EE 10
    * Don’t want to set the expectation that implementations must support JPMS at this point
    * Implementations can still experiment with their own aggregator modules

## Standalone Component TCKs (issue)
Each Specification project should own the TCK source and produce the TCK artifacts. This needs to be done in such a way that the artifacts can be run to validate implementations at the individual specification level, as well as integrated into platform level TCKs.

This is a run-at goal for Jakarta EE 10.  We know that not all Specifications can establish their standalone TCKs in this timeframe.  The Platform TCK can initiate this refactoring by breaking apart the TCK source into separate directories within the Platform TCK repository.  This will help with the eventual move of these TCK directories into their respective component repositories.
At this point the Core Profile does not envision a profile specific TCK. Rather the Core Profile TCK will be made up of the individual specification TCKs.

## Component Specification Project Releases
As mentioned, many of the Component Specification projects have already declared their intent for either a Major or Minor version update for Jakarta EE 10.  These projects have already submitted or completed their Plan Reviews for inclusion in Jakarta EE 10, and are driving towards a 4Q2021 release.  These updates are outlined in the sections below.

## Deliverables in Jakarta EE 10 Core Profile
The following details the specifications and APIs currently planned for the Jakarta EE 10 Core Profile.

### Jakarta EE 10 Core Profile Specifications
List of specifications in Jakarta EE 10 Core Profile (updated specifications marked with asterisks).

* Jakarta EE Core Profile 10.0*
* Jakarta Annotations 2.0
* Jakarta Contexts and Dependency Injection Lite 4.0*
* Jakarta Dependency Injection 2.0
* Jakarta Expression Language 5.0*
* Jakarta Interceptors 2.0
* Jakarta JSON Binding 2.1*
* Jakarta JSON Processing 2.1*
* Jakarta RESTful Web Services 3.1*
* Jakarta Config 1.0* (If available in Q4 2021)

## Release Milestones
As soon as all component Specifications have produced a release candidate, the Core Profile Specification will produce a release candidate based on these.  The Release Candidates will include:

* Release candidate Bill of Material pom file for Core Profile in Maven Central
* Release candidate Core Profile related TCKs
* Release candidate compatible implementation(s)

Once the release candidates have been validated and any issues ironed out, the final 10.0 release will proceed with all deliverables required for submission to the specification committee for approval.

### Proposed Progress Reviews
A progress review will most likely occur as the content becomes more firm, and component specifications have produced release candidates.

### Compatible Implementation
The JESP requires us to have a Compatible Implementation of the Core Profile available before the final Core Profile Specification can be ratified. Discussions are occurring with the ArC, Micronaut and Weld projects to provide implementations.

## FAQ

Additional clarifications for this Release Plan can be found in the overall platform [Jakarta EE 10 Release Plan FAQ](https://eclipse-ee4j.github.io/jakartaee-platform/jakartaee10/JakartaEE10ReleasePlanFAQ).
