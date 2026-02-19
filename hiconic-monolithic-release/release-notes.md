# Hiconic Monolitic Release Notes ${version}

<table>
  <tr><td>Group Id</td><td><b>${groupId}</b></td></tr>
  <tr><td>Artifact Id</td><td><b>${artifactId}</b></td></tr>
  <tr><td>Version</td><td><b>${version}</b></td></tr>
  <tr><td>Release Date</td><td><b>${date}</b></td></tr>
</table>

## Changes

### Validation Extension

- introduced `tribefire.extension.validation`
- works in reflex and cortex
- constraint metadata/annotation request+payload validation
- custom validator support


### Auth Extension

- introduced `tribefire.extension.auth`
- works in reflex and cortex
- role-based request authorization mapped with metadata/annotation
- reflection support for current user overview and general overview