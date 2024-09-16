# Jakarta EE 12 Release Plan

### Preamble

## Timeline

|              | Q1 2025      | Q2 2025 | Q3 2025     | Q4 2025 | Q1 2026 | Q2 2026 | June/July 2026  |
|--------------|--------------|---------|-------------|---------|---------|---------|-----------------|
| *Components* | Plan Reviews |         |             |         |         |         |                 |
| *Platform*   |              | Plan Review |         |         |         |         |                 |
| *All*        |              |         | M1 release  |         |         |         |                 |
| *All*        |              |         | M2 release  |         |         | | |
| *All*        |              |         |             | M3 release |  | | |
| *All*        |              |         |             | M4 release | |  | |
| *Components* |              |         |             |         | Further refine implementations       |  | |
| *Platform*   |              |         |             |         |         |         | Platform ballot |
| *Platform*   |              |         |             |         |         |         | Web Platform ballot |
| *Platform*   |              |         |             |         |         |         | Core Platform ballot |
| *Platform*   |              |         |             |         |         |         | **Release**     |

## Scope ([issue]())

## Java SE ([issue]())

Java SE 21 will become the minimum runtime supported by compatible implementations of Jakarta EE.

### API Source Code `--release` Level

For the Jakarta EE Platform (Platform, Web and Core), the Java compiler `--release` option is 21. For the component specs, the Jakarta EE Platform requires the Java compiler `--release` option is **at most** 21, but component specifications can decide on a lower level.

### TCK Source Level

- Component spec TCKs and platform TCK must compile at Java 21 or less.
- A compatible component impl must pass their component TCK when run under Java 21 or 25.
   - To ratify a component specification, there must exist an implementation that passes on Java 21. There must also exist an implementation that passes on 25.
   - These need not be the same implementation. There can be one implementation that passes on 21 and a different one that passes on 25.
- A compatible platform impl must pass the platform TCK when run under 21 or 25.
   - To ratify a platform specification, there must exist an implementation that passes on 21. There must also exist an implementation that passes on 25.
   - These need not be the same implementation. There can be one implementation that passes on 21 and a different one that passes on 25.

### Compatible Implementation (CI) Source Level

The long-standing policy of considering specification API binaries, in Maven Central or anywhere else, as a non-normative convenience remains unchanged. The platform project is silent on this matter. However, because the platform project does mandate a specific JDK requirement for compatible implementations passing the component or platform TCK, if a component specification does publish an API binary, that binary is practically constrained to follow that mandate." See [TCK Source Level](#tck-source-level)

## JPMS Module Info classes ([issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/329))
Suggestions on support for JPMS modules were introduced in the Jakarta EE 9 Platform Specification.
It is desired to firm up these suggestions into requirements.
Several discussions via Issues, Mailing Lists, and the Platform call have resulted in these requirements for Jakarta EE 12.
 
* Each individual component specification API provides at least one `module-info.class` following a specified set of conventions:
  * spec module name is `jakarta.<specName>` (reference [names.adoc](https://github.com/jakartaee/specification-committee/blob/master/names.adoc))
  * spec provides JPMS module definition (reliance on automatic modules is not allowed)
  * spec updates provider lookup algorithm to include search on module-path (if applicable)
* The Platform and Web Profile Specification API will not provide a platform/profile level `module-info.class` for EE 12
  * Don’t want to set the expectation that implementations must support JPMS at this point
  * Implementations can still experiment with their own aggregator modules

## Standalone Component TCKs ([issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/333))
Each Specification project should own the TCK source and produce the TCK artifacts.
This needs to be done in such a way that the artifacts can be run to validate implementations at the individual specification level, as well as integrated into platform level TCKs.

We know that not all Specifications can establish their standalone TCKs in this timeframe.

The Platform TCK can initiate this refactoring by breaking apart the TCK source into separate directories within the Platform TCK repository.

This will help with the eventual move of these TCK directories into their respective component repositories.


### Jakarta EE 12 APIs
The Platform and Web Profile API uber jar files will be re-generated to correspond with the Jakarta EE 12 release designation.
These API uber jar files will be compiled and distributed at the Java 12 source/target levels.  
**Note:** These uber jars will not be modularized, per the earlier discussion.

## Release Milestones
The Jakarta EE 12 Platform release plan covers the Platform and Web Profile specifications.
As stated earlier, all component Specifications which plan a Major or Minor release will be creating their own separate release plans.

### Waves

TBD

### Platform and Web Profile Release Candidate

At least one Release Candidate for Jakarta EE Platform and Web Profile will be produced.
These Release Candidates will include:

* Release candidates for all API JARs in Maven Central
* Release candidate Bill of Material pom files for Web Profile and Full Platform in Maven Central
* Release candidate TCKs
* Release candidate compatible implementation(s)

Once the release candidates have been validated and any issues ironed out, the full Jakarta EE 12 release will proceed with all deliverables required for submission to the specification committee for approval.

### Proposed Progress Reviews


### Compatible Implementation

The JESP requires us to have a Compatible Implementation of the Full Platform and Web Profile available before the Platform Project can deliver a final Specification. Discussions are occurring with the Specification Committee to allow for additional ratified compatible implementations (besides always relying on Eclipse Glassfish).
The Platform project has no control over the release dates of any potential Compatible Implementations.
The platform project will maintain close coordination with the various Compatible Implementations for the duration of the Jakarta EE 12 release cycle.

### FAQ

Additional clarifications for this Release Plan can be found in the [Jakarta EE 12 Release Plan FAQ](https://jakartaee.github.io/platform/jakartaee12/JakartaEE12ReleasePlanFAQ).

