---
title: "Publishing Jakarta EE XML Schemas"
date: "2020-03-25T00:00:00+00:00"
---

# How to Publish XML Schemas

## Staging

Submit a PR to https://github.com/eclipse-ee4j/ee4j with the following content:

- `xml/ns/jakartaee/wombat-x.y.xsd`


## Publishing

The following describes how to publish XML Schemas to https://jakarta.ee/xml/ns/jakartaee.
This will be the responsibility of the Platform Project.
A schema may be published in Draft state by setting the `status` field in `data/schemas.yml` to **Draft**.
For a final release, this field must be changed to **Final Release**

Submit a PR to https://github.com/jakartaee/jakarta.ee with the following content:

- `static/xml/ns/jakartaee/wombat-x.y.xsd`
- Updated descriptor file `data/schemas.yml` 

Example `data/schemas.yml`:

```
- name: Jakarta EE X
  version: X
  schemas: 

  ...
  other schemas for this version
  ...

  - schema: wombat-x.y.xsd
    description: Wombat does...
    status: Final Release
```
