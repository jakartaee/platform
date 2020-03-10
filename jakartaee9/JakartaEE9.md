# Jakarta EE 9 (under development)

## Jakarta EE 9 Release Plan

The [Jakarta EE 9 Release Plan](JakartaEE9ReleasePlan) is now available!  
In late 2019, it was reviewed and endorsed by the Platform Project, as well as the [Jakarta EE Steering Committee](https://jakarta.ee/meeting_minutes/steering_committee/minutes-december-17-2019.pdf).
In early 2020, an official ballot was approved by the [Jakarta EE Specification Committee](https://www.eclipse.org/lists/jakarta.ee-spec/msg00574.html).

A [Jakarta EE 9 Release Plan FAQ](https://eclipse-ee4j.github.io/jakartaee-platform/jakartaee9/JakartaEE9ReleasePlanFAQ) has also been created to help clarify aspects of the Release Plan.

### Individual Component Release Plans

The key goal of the [Jakarta EE 9 Release Plan](JakartaEE9ReleasePlan) is to move from the `javax` namespace to the `jakarta` namespace.
Almost all of the Jakarta EE 9 components will be exclusively focused on that effort.
But, there are a few components (ie. EJB, Activation, maybe others..) that need additional changes to their APIs in the Jakarta EE 9 timeframe.
For these components, a separate Release Plan will be necessary to outline the reasoning for these additional updates.
Also, it is expected that these type of changes will still be required to stick to the date goals being set for Jakarta EE 9.

These component release plans are not as elaborate as the [Jakarta EE 9 Release Plan](JakartaEE9ReleasePlan).
They should reference this overall Release Plan as a basis for the individual component release plan.
These component release plans will utilize the existing Eclipse mechanism for defining an upcoming release, which is documented in the [Eclipse Foundation Project Handbook](https://www.eclipse.org/projects/handbook/#release).

- [Jakarta Activation Framework 2.0 Release Plan](https://projects.eclipse.org/projects/ee4j.jaf/releases/2.0/plan)
- [Jakarta Enterprise Beans 4.0 Release Plan](https://projects.eclipse.org/projects/ee4j.ejb/releases/4.0/plan)

## Jakarta EE 9 Project board

Jakarta EE 9 will track its progress with a [Github Project Board](https://github.com/orgs/eclipse-ee4j/projects/17).
An individual Issue was created for each Specification Project to track its progress.  
For example, here's a link to the [Jakarta EE Platform Specification Version 9 Issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/133).
The [Jakarta EE Release repo](https://github.com/eclipse-ee4j/jakartaee-release) will also be used for Issue tracking across the overall project.  
For example, the [Milestone/Release Candidate API artifacts](https://github.com/eclipse-ee4j/jakartaee-release/issues) are tracked in this repository.
