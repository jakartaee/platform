
# Jakarta EE 11 Release Plan FAQ

This FAQ should be used to complement the [Jakarta EE 11 Release Plan](https://eclipse-ee4j.github.io/jakartaee-platform/jakartaee11/JakartaEE11ReleasePlan).

### FAQ Table of Contents

**Java SE 21**
- [Why require Java SE 21 for TCK execution?](why-require-java-se-21-for-tck-execution)

**Feature Removal**

**Standalone TCKs**
- [Why are the standalone TCKs not a requirement for Jakarta EE 11?](why-are-the-standalone-tcks-not-a-requirement-for-jakarta-ee-11)

**Deliverables in Jakarta EE 11**

**JPMS**
- [Should the TCK enforce modularization?](#should-the-tck-enforce-modularization)
- [Can JPMS `open module` be used?](#can-jpms-open-module-be-used)
- [Are automatic modules allowed?](#are-automatic-modules-allowed)
- [Are ServiceLoaders affected by modularization?](#are-serviceloaders-affected-by-modularization)

----------

#### Why require Java SE 21 for TCK execution?

Although we have set the requirement for Java SE 11 as the minimum runtime requirement, several vendors have expressed an interest in supporting Java SE 21 as soon as its available.
In order to support this desire, we are requiring the TCK to successfully execute with Java SE 21 as part of Jakarta EE 11.

#### Why are the standalone TCKs not a requirement for Jakarta EE 11?

Short answer is that this is just too much work to contain for Jakarta EE 11.
But, we need to start this activity.
So, for Jakarta EE 11, the plan is to outline the process for separating these standalone TCKs from the Platform TCK and to move as many of these as possible in the alloted timeframe.

#### Should the TCK enforce modularization?

No.
There is no requirement to validate component API jar `module-info.class` files for Jakarta EE 11.

#### Can JPMS `open module` be used?

No.
JPMS `open module` definitions are not to be used by the component `module-info.class` files.
This open reflective access to the module is not consistent with the longer term modularization goals.

#### Are automatic modules allowed?

No new automatic modules are allowed to be defined in Jakarta EE 11.
Components are strongly encouraged to update existing module definitions if automatic modules were used in the past. 
But, this modification will not be enforced for Jakarta EE 11.

#### Are ServiceLoaders affected by modularization?

Yes, most likely.
If your Component uses custom ServiceLoaders, then these will need to be updated to use the JDK-provided ServiceLoaders (to allow for proper module processing).
Research is currently being performed across the Jakarta EE Components to see which ones are affected.
Issues will be created to track the necessary updates.
