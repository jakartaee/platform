# Jakarta EE 9.1 Release Plan

## Scope

The goal of the Jakarta EE 9.1 release is to deliver a set of specifications functionally equivalent to Jakarta EE 9 and adding the support for the Java SE 11 runtime.

The Platform team sees Jakarta EE 9.1 as an extension to the foundational Jakarta EE 9 release.
No API updates are expected in Jakarta EE 9.1.
Only the Platform and Web Profile Specifications along with the TCK and Compatible Implementations should be affected by Jakarta EE 9.1.

## Java SE 11
### API Source Level

The APIs will continue to be compiled at the Java SE 8 level.
The APIs need to be usable by both Java SE 8 and Java SE 11.
Thus, keeping the same Java SE 8 source/target level for the APIs will still be required.

### TCK Source Level

The TCKs will continue to be compiled at the Java SE 8 level.
This would allow the same TCK to be used for Compatibility testing with either Java SE 8 or 11 runtime.

#### Signature Tests

Currently, the TCK Signature Tests are specific to the level of the Java SE runtime which is being used for testing.
The TCK may need to be updated to include the Java SE 11 signatures.

#### CORBA and RMI/IIOP Tests

For Jakarta EE 9, the CORBA tests were left as-is and these tests were executed by default, but the RMI/IIOP tests were removed as part of the default execution.
Since the CORBA ORB was removed from Java SE 11, there will be an impact to the TCK to support these CORBA tests.
To minimize the impact to Jakarta EE 9.1, the expectation is to leave the CORBA tests in the TCK, but make them optional.

#### Web Services Tests

Many of the Web Services related features (XML Binding, XML Web Services, Web Services Metadata, and SOAP with Attachments) were dropped from Java SE 11.
But, they were picked up for optional inclusion with Jakarta EE 9.
Since these optional features were provided with the Java SE 8 runtime, the TCK may need to be adjusted when running with the Java SE 11 runtime where they are no longer provided.

### Compatible Implementation (CI) Source Level

How a Compatible Implementation supports the Java SE 11 runtime will be left as a vendor-defined solution.

## Specification Project Minor (Point) Releases?

A few of the Jakarta Specification projects are already working on their “next” releases.
This type of new, innovative work needs to be encouraged and promoted.

Since the ultimate goal of Jakarta EE 9.1 is to support the Java SE 11 runtime in a timely manner, no Specification API updates will be included in 9.1.
If the Specification text or Javadoc needs to be updated to clarify some processing without any functional impact to the API, those types of changes should be entertained via a Service Release (x.y.z).
The exact process for Specification Service Releases (extent of changes, reviews required, ballots required, etc) is still being worked out.

The preferred approach would be for these Specification projects to continue with their proposed “next” releases -- taking them through the required plan and review processes.
But, don’t attempt to tie them to the Jakarta EE 9.1 release.
These would just be independent updates to the Jakarta Specifications that could be discussed for inclusion in a future Jakarta EE Platform release.

## Deliverables in Jakarta EE 9.1

The following details the specifications and APIs included within the Jakarta EE 9.1 Platform.

### Jakarta EE 9.1 Specifications

List of existing specifications in Jakarta EE 9.1.
(**Note:** Service Releases (x.y.z) are not specified here since no functional changes are included in a Service Release.)

- Jakarta EE Platform 9.1
- Jakarta EE Web Profile 9.1
- Jakarta Activation 2.0
- Jakarta Annotations 2.0 
- Jakarta Authentication 2.0
- Jakarta Authorization 2.0
- Jakarta Batch 2.0
- Jakarta Bean Validation 3.0
- Jakarta Concurrency 2.0
- Jakarta Connectors 2.0
- Jakarta Contexts and Dependency Injection 3.0
- Jakarta Debugging Support for Other Languages 2.0
- Jakarta Dependency Injection 2.0
- Jakarta Enterprise Beans 4.0
- Jakarta Enterprise Web Services 2.0 (Optional)
- Jakarta Expression Language 4.0
- Jakarta Interceptors 2.0
- Jakarta JSON Binding 2.0
- Jakarta JSON Processing 2.0
- Jakarta Mail 2.0
- Jakarta Managed Beans 2.0
- Jakarta Messaging 3.0
- Jakarta Persistence 3.0
- Jakarta RESTful Web Services 3.0
- Jakarta Security 2.0
- Jakarta Server Faces 3.0
- Jakarta Server Pages 3.0
- Jakarta Servlet 5.0
- Jakarta SOAP with Attachments 2.0 (Optional)
- Jakarta Standard Tag Library 2.0
- Jakarta Transactions 2.0
- Jakarta WebSocket 2.0
- Jakarta Web Services Metadata 3.0 (Optional)
- Jakarta XML Binding 3.0 (Optional)
- Jakarta XML Web Services 3.0 (Optional)

### Jakarta EE 9.1 APIs

The Platform and Web Profile API jar files will be re-generated to correspond with the 9.1 release designation.
The intent is that the content of the 9.0 and 9.1 jar files are the same, but update the maven coordinate artifacts to make them easy to find and use.

## Release Milestones

The Jakarta EE 9.1 platform project is proposing that this release plan covers all specifications targeted for Jakarta EE 9.1.
As stated in the scope, specifications will not be making functionality changes for inclusion in this release, therefore individual specification release plans are not necessary.

### Full Platform and Web Profile Release Candidate

Although the Jakarta EE 9.1 release is limited in scope, at least one Release Candidate for Jakarta EE Platform and Web Profile will be produced.
These Release Candidates will include:

- Release candidates for all API JARs in Maven Central
- Release candidate Bill of Material pom files for Web Profile and Full Platform in Maven Central
- Release candidate TCKs
- Release candidate compatible implementation(s)

Once the release candidate has been validated and any issues ironed out, the full 9.1 release will proceed with all deliverables required for submission to the specification committee for approval.

### Proposed Progress Reviews

Since this Jakarta EE 9.1 release is limited in scope, no interim progress reviews are expected.
The overall schedule for Jakarta EE 9.1 will be maintained on [this separate page](https://eclipse-ee4j.github.io/jakartaee-platform/jakartaee9/JakartaEE9.1#jakarta-ee-9.1-schedule).

### Compatible Implementation          

The JESP requires us to have a Compatible Implementation of the Full Profile and Web Profile available before the Platform Project can deliver a final specification.
At this stage, it is assumed that this implementation will be Eclipse GlassFish.
However, the Platform project has no control over the release dates of Eclipse GlassFish.
The platform project will maintain close coordination with the Eclipse GlassFish project for the duration of the Jakarta EE 9.1 release development.

## FAQ

Additional clarifications for this Release Plan can be found in the [Jakarta EE 9.1 Release Plan FAQ](https://eclipse-ee4j.github.io/jakartaee-platform/jakartaee9/JakartaEE9.1ReleasePlanFAQ).
