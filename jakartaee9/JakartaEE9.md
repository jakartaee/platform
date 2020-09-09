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
    
    
- Final Jakarta EE 9 release (Java 8) - **Nov 20** completion (proposed)
    
    **Note:** We are now driving towards a Friday, Nov 20 date for Jakarta EE 9 completion.
    Jakarta EE 9 will be formally announced at the JakartaOne Livestream on Tuesday, Dec 08.
    
    - Wave 0 (independent) Specification PRs 
        - PRs Ready for Review - Anytime before Sept 25
        - PRs Complete/Ballots Start - Anytime before Oct 09
        - Ballots Complete - Anytime before Oct 23
    - Wave 1 Specification PRs 
        - PRs Ready for Review - Sept 11
        - PRs Complete/Ballots Start - Sept 25
        - Ballots Complete - Oct 9
    - Wave 2 Specification PRs 
        - PRs Ready for Review - Sept 18
        - PRs Complete/Ballots Start - Oct 02
        - Ballots Complete - Oct 16
    - Wave 3 Specification PRs 
        - PRs Ready for Review - Sept 25
        - PRs Complete/Ballots Start - Oct 09
        - Ballots Complete - Oct 23
    - Wave 4 Specification PRs 
        - PRs Ready for Review - Oct 02
        - PRs Complete/Ballots Start - Oct 16
        - Ballots Complete - Oct 30
    - Wave 5 Specification PRs 
        - PRs Ready for Review - Oct 09
        - PRs Complete/Ballots Start - Oct 23
        - Ballots Complete - Nov 06
    - Wave 6 Specification PRs 
        - PRs Ready for Review - Oct 16
        - PRs Complete/Ballots Start - Oct 30
        - Ballots Complete - Nov 13
    - Wave 7 (Platform) Specification PRs 
        - PRs Ready for Review - Oct 23
        - PRs Complete/Ballots Start - Nov 06
        - Ballots Complete - Nov 20 
    
### Jakarta EE 9 Project board

Jakarta EE 9 will track its development progress with a [Github Project Board](https://github.com/orgs/eclipse-ee4j/projects/17).
An individual Epic Issue was created for each Specification Project to track its progress.
For example, here's a link to the [Jakarta EE Platform Specification Version 9 Issue](https://github.com/eclipse-ee4j/jakartaee-platform/issues/133).

The [Jakarta EE Release repo](https://github.com/eclipse-ee4j/jakartaee-release) will also be used for Issue tracking across the overall project.
For example, the [Milestone/Release Candidate API artifacts](https://github.com/eclipse-ee4j/jakartaee-release/issues) are tracked in this repository.
