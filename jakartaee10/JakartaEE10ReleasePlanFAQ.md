
# Jakarta EE 10 Release Plan FAQ

This FAQ should be used to complement the [Jakarta EE 10 Release Plan](https://eclipse-ee4j.github.io/jakartaee-platform/jakartaee10/JakartaEE10ReleasePlan).

### FAQ Table of Contents

** Scope **
- [Why is Core Profile not part of this Release Plan?](#why-is-core-profile-not-part-of-this-release-plan)

** Java SE 11 **
- [Why require Java SE 17 for TCK execution?](why-require-java-se-17-for-tck-execution)

** Feature Removal **
- [Why remove these two EJB features?](why-remove-these-two-ejb-features)

** Standalone TCKs **
- [Why are the standalone TCKs not a requirement for Jakarta EE 10?](why-are-the-standalone-tcks-not-a-requirement-for-jakarta-ee-10)

** Deliverables in Jakarta EE 10 **
- [What happened to the Jakarta Web Services Metadata Specification?](what-happened-to-the-jakarta-web-services-metadata-specification)

** JPMS **
- [Should the TCK enforce modularization?](#should-the-tck-enforce-modularization)
- [Can JPMS `open module` be used?](#can-jpms-open-module-be-used)
- [Are automatic modules allowed?](#are-automatic-modules-allowed)
- [Are ServiceLoaders affected by modularization?](#are-serviceloaders-affected-by-modularization)

----------
#### Why is Core Profile not part of this Release Plan?

The Core Profile is a new profile under development for Jakarta EE.
Since the goal is to allow profiles to deliver on their own schedules (separate from the Platform), there is no strict requirement that the Core Profile be delivered with Jakarta EE 10.
The current definition of the Core Profile can be found [https://eclipse-ee4j.github.io/jakartaee-platform/jakartaee10/JakartaEE10CoreProfileRelasePlan.md](here).
The Core Profile is currently expected to be delivered in the same Q1 2022 timeframe as the rest of the Jakarta EE 10 release. 

#### Why require Java SE 17 for TCK execution?

Although we have set the requirement for Java SE 11 as the minimum runtime requirement, several vendors have expressed an interest in supporting Java SE 17 as soon as its available.
In order to support this desire, we are requiring the TCK to successfully execute with Java SE 17 as part of Jakarta EE 10.

#### Why remove these two EJB features?

As stated in the Release Plan, the main goal is to allow more Compatible Implementations to be used for ratification of the Platform Specification.
Currently, these two features (EJB Entity Beans and the Embeddable EJB Container) are Optional features.
The goal of this exercise is to also remove the requirement that these optional features need to be implemented and tested for ratification.
A new designation will need to be defined to indicate which features are or are not required to ratify the Platform Specification.

#### Why are the standalone TCKs not a requirement for Jakarta EE 10?

Short answer is that this is just too much work to contain for Jakarta EE 10.
But, we need to start this activity.
So, for Jakarta EE 10, the plan is to outline the process for separating these standalone TCKs from the Platform TCK and to move as many of these as possible in the alloted timeframe.

#### What happened to the Jakarta Web Services Metadata Specification?

Due to the tight integration with the Jakarta XML Web Services Specification, it was determined there was no reason to keep these two efforts separate.
The exact process for "retiring" the Web Services Metadata Specification and merging its contents into the XML Web Services Specification is still being worked.
But, for Jakarta EE 10, consider Jakarta Web Services Metadata 3.0 as an integral part of Jakarta XML Web Services 4.0.

#### Should the TCK enforce modularization?

Yes.
At the Component Specification level, the TCK should be adjusted to provide simple verification of the `module-info.class`.
A minimal validation would be to verify the existence of the `module-info.class` by loading the API jar and verifying that the `module.getDescriptor().isAutomatic()` is `false`.  
**Note:** This requirement does not apply to the Platform or Profile uber jar files since these will not be modularized for Jakarta EE 10.

#### Can JPMS `open module` be used?

No.
JPMS `open module` definitions are not to be used by the component `module-info.class` files.
This open reflective access to the module is not consistent with the longer term modularization goals.

#### Are automatic modules allowed?

No new automatic modules are allowed to be defined in Jakarta EE 10.
Components are strongly encouraged to update existing module definitions if automatic modules were used in the past. 
But, this modification will not be enforced for Jakarta EE 10.

#### Are ServiceLoaders affected by modularization?

Yes, most likely.
If your Component uses custom ServiceLoaders, then these will need to be updated to use the JDK-provided ServiceLoaders (to allow for proper module processing).
Research is currently being performed across the Jakarta EE Components to see which ones are affected.
Issues will be created to track the necessary updates.
