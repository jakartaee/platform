---
title: "Publishing Jakarta EE XML Schemas"
date: "2020-03-25T00:00:00+00:00"
---

# How to Publish XML Schemas

This page describes how to publish XML Schemas to https://jakarta.ee/xml/ns/jakartaee.

Submit a PR to https://github.com/jakartaee/jakarta.ee with the following content:

- `static/xml/ns/jakartaee/wombat-x.y.xsd`
- Updated descriptor file `data/jakartaee_schemas.yml` 

Example 1 `data/jakartaee_schemas.yml`:

```
- name: Jakarta EE X
  version: X
  schemas: 

  ...
  other schemas for this version
  ...

  - schema: wombat-x.y.xsd
    namespace: jakartaee
    description: Wombat does...
    status: Final Release
```

Example 2 `data/persistence_schemas.yml`:

```
- name: Jakarta Persistence X
  version: X
  schemas: 

  ...
  other schemas for this version
  ...

  - schema: wombat-x.y.xsd
    namespace: persistence
    description: Wombat does...
    status: Final Release
```
