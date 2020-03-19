
# Jakarta EE 9 Release Plan FAQ

This FAQ should be used to complement the [Jakarta EE 9 Release Plan](https://eclipse-ee4j.github.io/jakartaee-platform/jakartaee9/JakartaEE9ReleasePlan).

## FAQ

**API**
- [Is adding @Deprecated allowed?](#is-adding-deprecated-allowed)
- [Is introducing Generics in the API signatures allowed?](#is-introducing-generics-in-the-api-signatures-allowed)
- [Is adding @Repeatable allowed?](#is-adding-repeatable-allowed)
- [Should `javax` property names be renamed to `jakarta`?](#should-javax-property-names-be-renamed-to-jakarta)
- [Will the target namespace change for schemas?](#will-the-target-namespace-change-for-schemas)

**TCK**
- [Keep the old `javax` signature files?](#keep-the-old-javax-signature-files)

### Is adding @Deprecated allowed?

Adding @Deprecated to the Java code is allowed where it is currently defined in the Javadoc (consistency).
But, introducing newly @Deprecated classes or methods would require a separate Release Plan for that Project.

### Is introducing Generics in the API signatures allowed?

No.
Although there were simple cases identified where the introduction of Generics would be okay, it was decided to keep it simple and not allow the introduction of Generics in the Jakarta EE 9 APIs.
Any proposed use of Generics would require a separate Release Plan for that Project.

### Is adding @Repeatable allowed?

Adding @Repeatable to the Java code is allowed where it should it have been introduced in previous Java EE or Jakarta EE releases (consistency).

### Should `javax` property names be renamed to `jakarta`?

Yes, `javax.*` property names should be renamed to `jakarta.*` for all properties defined by Jakarta EE 9.
Pruned Jakarta EE Projects will leave their property names in the `javax.*` namespace.

### Will the target namespace change for schemas?

Yes, the proposed target namespace is `https://jakarta.ee/xml/ns/jakartaee/`.  
This work is being tracked [via this bug](https://github.com/jakartaee/jakarta.ee/issues/592).

### Keep the old `javax` signature files?

There is no reason to keep these old `javax` signature files since only the `jakarta` signatures will be developed, maintained, and tested.
To clarify, this question is referring to the `javax` signature files in [this directory](https://github.com/eclipse-ee4j/jakartaee-tck/tree/master/src/com/sun/ts/tests/signaturetest/signature-repository).
