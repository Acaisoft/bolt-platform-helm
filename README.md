# Bolt Platform Umbrella Chart
Chart that holds all required components to deploy testing platform.

### Installation guide
1. Replace all `PLACEHOLDER` in values.yaml
2. hasura, argo and bolt-portal require tls secrets. Create `Certificate`'s custom
resources according to what was filled in `PLACEHOLDER` values.
3. wait for everything to start and you should be able to access bolt platform.