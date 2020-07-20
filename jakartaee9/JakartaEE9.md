# Jakarta EE 9 (under development)

- [Jakarta EE 9 Release Plan](#jakarta-ee-9-release-plan)
    - [Individual Component Release Plans](#individual-component-release-plans)
- [Jakarta EE 9 Schedule](#jakarta-ee-9-schedule)
    - [Jakarta EE 9 Project Board](#jakarta-ee-9-project-board)

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

## Jakarta EE 9 schedule

Overall schedule (dates are ***tentative*** and ***subject to change***).  The wave content is based off of the descriptions in the [Jakarta EE 9 Release Plan](JakartaEE9ReleasePlan).

- Milestone 1 release (Java 8) - **June 23** announce (done)
    - Development Complete - June 12
    - Testing Complete - June 19
    
    
- Final Jakarta EE 9 release (Java 11) - **Sept 16** announce (proposed)
    - Wave 0 (independent) Specification PRs 
        - PRs Ready for Review - Anytime before Aug 10
        - PRs Complete/Ballots Start - Anytime before Aug 24
        - Ballots Complete - Anytime before Sept 7
    - Wave 1 Specification PRs 
        - PRs Ready for Review - July 6
        - PRs Complete/Ballots Start - July 20
        - Ballots Complete - Aug 3
    - Wave 2 Specification PRs 
        - PRs Ready for Review - July 13
        - PRs Complete/Ballots Start - July 27
        - Ballots Complete - Aug 10
    - Wave 3 Specification PRs 
        - PRs Ready for Review - July 20
        - PRs Complete/Ballots Start - Aug 3
        - Ballots Complete - Aug 17
    - Wave 4 Specification PRs 
        - PRs Ready for Review - July 27
        - PRs Complete/Ballots Start - Aug 10
        - Ballots Complete - Aug 24
    - Wave 5 Specification PRs 
        - PRs Ready for Review - Aug 3
        - PRs Complete/Ballots Start - Aug 17
        - Ballots Complete - Aug 31
    - Wave 6 Specification PRs 
        - PRs Ready for Review - Aug 10
        - PRs Complete/Ballots Start - Aug 24
        - Ballots Complete - Sept 7
    - Wave 7 (Platform) Specification PRs 
        - PRs Ready for Review - Aug 17
        - PRs Complete/Ballots Start - Aug 31
        - Ballots Complete - Sept 14 
    
### Jakarta EE 9 Project board

Jakarta EE 9 will track its development progress with a [Github Project Board](https://github.com/orgs/eclipse-ee4j/projects/17).
An individual Epic Issue was created for each Specification Project to track its progress.
For example, here's a link to the [Jakarta EE Platform Specification Version 9 Issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/133).

The [Jakarta EE Release repo](https://github.com/eclipse-ee4j/jakartaee-release) will also be used for Issue tracking across the overall project.
For example, the [Milestone/Release Candidate API artifacts](https://github.com/eclipse-ee4j/jakartaee-release/issues) are tracked in this repository.
