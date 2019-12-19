# Jakarta EE 9 (under development)

## Jakarta EE 9 Release Plan

The [Jakarta EE 9 Release Plan](JakartaEE9ReleasePlan) is now available!  
It was recently reviewed and endorsed by the Platform Project, as well as the Jakarta EE Steering Committee (_need approved minutes link here when ready_).
In the new year, an official ballot will be initiated with the Jakarta EE Specification Committee to make it "official".
_(A link to the final ballot will also be posted here.)_
In the mean time, let's continue with our development efforts as if it's all approved...

### Individual Component Release Plans

The key goal of the [Jakarta EE 9 Release Plan](JakartaEE9ReleasePlan) is to move from the `javax` namespace to the `jakarta` namespace.
Almost all of the Jakarta EE 9 components will be exclusively focused on that effort.
But, there are a few components (ie. EJB, Activation, maybe others..) that need additional changes to their APIs in the Jakarta EE 9 timeframe.
For these components, a separate Release Plan will be necessary to outline the reasoning for these additional updates.
Also, it is expected that these type of changes will still be required to stick to the date goals being set for Jakarta EE 9.

These component release plans do not have to be as elaborate as the [Jakarta EE 9 Release Plan](JakartaEE9ReleasePlan).
They can and should reference this overall Release Plan as a basis for the individual component release plan.
These component release plans should utilize the existing Eclipse mechanism for defining an upcoming release, which is documented in the [Eclipse Foundation Project Handbook](https://www.eclipse.org/projects/handbook/#release).

Let's use Jakarta Enterprise Beans as an example.
If you are a committer on the project, you can go to the [Eclipse project page](https://projects.eclipse.org/projects/ee4j.ejb) and select the option to [Create a new release](https://projects.eclipse.org/node/14204/create-release) on the right hand side menu under Committer Tools.
From here, you can enter an expected release date and the corresponding version number for this release.
Select "create and edit" and you'll be presented with various panels for building up your individual Release Plan.
Once the Release Plan is ready, it will need to be reviewed with the Specification Committee for approval.
