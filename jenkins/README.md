# Jenkins Build Information

## Jenkins URL
- https://ci.eclipse.org/jakartaee-platform/

## Jenkins Jobs
* [jakartaee-api-build](https://ci.eclipse.org/jakartaee-platform/job/jakartaee-api-build/)
  * The *jakartaee-api-build* job is triggered via a GitHub webhook to build the repo any time it changes.  It can also be triggered manually, if desired.

* [release](https://ci.eclipse.org/jakartaee-platform/job/release/)
  * The *release* job is intended to support building and releasing to staging [any of the repos](https://projects.eclipse.org/projects/ee4j.jakartaee-platform/developer) that are part of the jakartaee-platform project.  It currently only supports the [jakartaee-api repo](https://github.com/eclipse-ee4j/jakartaee-api/).  It's triggered manually.  This job is used when the API is ready to be delivered.

* [nexus-release](https://ci.eclipse.org/jakartaee-platform/job/nexus-release/)
  * The *nexus-release* job releases *staged* artifacts to Maven Central.  It's triggered manually.  This job is used when the platform is approved.

### Misc Jenkins Jobs

* [tutorial-publish](https://ci.eclipse.org/jakartaee-platform/job/tutorial-publish/) and [firstcup-publish](https://ci.eclipse.org/jakartaee-platform/job/firstcup-publish/)
  * The *tutorial-publish* and *firstcup-publish* jobs are triggered by GitHub webhooks and will republish the corresponding sites when the repos are updated.
