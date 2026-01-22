# Hiconic Monolitic Release Notes ${version}

<table>
  <tr><td>Group Id</td><td><b>${groupId}</b></td></tr>
  <tr><td>Artifact Id</td><td><b>${artifactId}</b></td></tr>
  <tr><td>Version</td><td><b>${version}</b></td></tr>
  <tr><td>Release Date</td><td><b>${date}</b></td></tr>
</table>

## Changes

### Hiberante Mappings
- Fixed mapping for collections of BigDecimal
- Introduced TRIBEFIRE_HBM_MAPPING_VERSION env
- Collections of Dates now mapped as timestamp (date+time) rather than date only (mapping version 2)
- Collections of Enums now stored as text rather than binary (mapping version 2)
- Generating indices for properties with Indexed MD (mapping version 3; will be controlled by a separate property later)
- Automatic generation of indices for foreign keys and map key column (mapping version 3; will be controlled by a separate property later)

### Graph Fetching
- implemented with different resolution strategies
- there is still the need to measure how the strategies perform in real life contexts
- in case of Hibernate direct SQL is used for resolution