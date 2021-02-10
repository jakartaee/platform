
# Jakarta EE 9.1 Release Plan FAQ

This FAQ should be used to complement the [Jakarta EE 9.1 Release Plan](https://eclipse-ee4j.github.io/jakartaee-platform/jakartaee9/JakartaEE9.1ReleasePlan).

## FAQ

**API**
- [Can the Specifications be updated?](#can-the-specifications-be-updated)
- [Can the Javadoc be updated?](#can-the-javadoc-be-updated)

**CORBA**
- [Why not just remove the CORBA requirement?](#why-not-just-remove-the-CORBA-requirement)


### Can the Specifications be updated?

Yes, as long as it does not introduce any functional changes.
Any updates to a Component's Specification will need to conform to the rules of a Service Release (x.y.z).

**Note:** The Jakarta EE 9.1 Platform Specification will be updated in support of the Java SE 11 requirement.

### Can the Javadoc be updated?

Yes, as long as it does not introduce any functional changes.
Any updates to a Component's Javadoc will need to conform to the rules of a Service Release (x.y.z).

### Why not just remove the CORBA requirement?

The goal of Jakarta EE 9.1 is to support Java SE 11, without any impact to the functional aspects of Jakarta EE 9.
Removal of CORBA in 9.1 would affect the Enterprise Beans APIs and, thus, make Jakarta EE 9.1 incompatible with Jakarta EE 9 from an API perspective.
For this reason, the CORBA requirements will continue to be Optional in Jakarta EE 9.1, with the future intent of removal.
