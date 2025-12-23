# Hiconic Monolitic Release Notes ${version}

<table>
  <tr><td>Group Id</td><td><b>${groupId}</b></td></tr>
  <tr><td>Artifact Id</td><td><b>${artifactId}</b></td></tr>
  <tr><td>Version</td><td><b>${version}</b></td></tr>
  <tr><td>Release Date</td><td><b>${date}</b></td></tr>
</table>

## Changes

### Hibernate
- Automatic indices for foreign keys on entity and linear collection props
- Support fur Opimistic Locking with @Version property annotation / Version meta data
- Experimental graph-fetching (parallelized entity graph resolution framework)

### GM
- AOP Support for Workes with WorkerAspect

### Tools
- Fixing message when raising version for publishing

### General
- Hiding sensitive information from logs
- About page text color fixed for Mac

### Reflex
- Support for Explorer and many core features adapted (checks, swagger-ui, workers...), still WIP
