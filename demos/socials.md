# How to add socials to your demo portal

Simple add an object named `socials` to your `demo.yaml`.

We currently support the following keys:

- `website`
- `documentaiton`

Here is an example of a `demo.yaml` file with `socials` configured.

```yaml
organizationName: Konfig
portalName: Konfig Documentation
socials:
  website: https://apidemo.konfigthis.com
  documentation: https://demo.konfigthis.com/konfig-dev/konfig-demo-docs
demos:
  - id: demo
```
