# Hiconic Monolitic Release Notes ${version}

The main development themes were the expansion of the Reflex/RX platform, reproducible application packaging, model-driven configuration, stronger authentication and session handling, and substantially richer operational tools. Additional work covered database reliability, JavaScript interoperability, templating, build tooling, and extension migration.

**1. Reflex/RX platform and extension integration**

July brought a broad RX integration change across the platform and several extensions. Subsequent work expanded module composition, service domains, access integration, security, Explorer/workbench integration, and system tooling.

- Added platform initialization facilities, initializer status reflection, registered-name reporting, and checks for initializer failures.
- Improved context propagation, including full user context for system evaluations and preservation of dynamic attribute contexts across RX sessions.
- Added state processing, an ID generator aspect, system evaluators, and execution-domain support.
- Improved module reflection, optional module composition, application artifact identity, and embedding applications without an artifact identity.
- Consolidated extension configuration metadata into platform-owned models for authentication and validation.

**2. Application assembly, configuration, and packaged resources**

Application builds gained reproducible RX application images, npm web application assembly, packaged configuration projection, and effective configuration compilation and validation.

- Added configuration imports, partial assembly, placeholder resolution, and model-driven value descriptor expressions.
- Added source-relative and artifact-addressed resource resolution, configuration decryption expressions, and encrypted packaged-resource assembly.
- Refactored `ArtifactResource` to `PackagedResource` and removed special treatment of the `HICONIC-RESOURCES` folder.
- Improved classpath resource indexing for Windows, Eclipse, Gradle output, explicitly listed resources, and unpacked classpaths.
- Fixed dependency traversal that could omit transitive application libraries behind POM aggregator dependencies.
- Improved configuration diagnostics, import-origin reporting, and Docker image assembly defaults.

**3. Authentication, authorization, and sessions**

Security work covered native login, Shiro/OIDC integration, JWT authentication, browser approval, authorization metadata, and cluster behavior.

- Added browser/device approval support and extensible login options, including trusted entry points, login interventions, and pre-authenticated actions.
- Unified login flows and isolated external login actions from native credentials; made external actions cluster-safe.
- Added RX JWT web authentication, multiple JWKS configurations, audience-based JWKS selection, user synchronization, and configurable role modification.
- Added a modeled session idle timeout and optional JWT-related session expiry behavior.
- Fixed clustered session retrieval, expired-session handling, session reacquisition, and configured session-cookie behavior.
- Introduced node-specific internal session IDs and prevented their propagation to other nodes.
- Improved credential selection, security audit logging, user/role/group reconciliation, password encryption integration, and preservation of authorization failure reasons.
- Added RBAC role induction and authorization overrides, and exposed effective RBAC roles in OpenAPI descriptions.

**4. Logging, log reflection, and diagnostics**

Log reflection developed into a more capable operational interface for local and clustered applications.

- Added and refined live tailing, independent tail tabs, local snapshots, historical log access, human-readable bundles, and current-view exports.
- Improved remote downloads and streaming exports, chronological merging of cluster logs, and preservation of node identity.
- Added capability-aware access checks and improved expired-session and access-error handling.
- Integrated log-level management, reusable profiles, cascading overrides, cluster updates, and profile editing.
- Synchronized JUL and Logback levels, supported the `OFF` level, and retained configured JUL loggers.
- Reduced self-generated noise from tail requests, bounded local log history, and improved handling of rotated-log cursors.
- Improved startup, initializer, push-channel, and request diagnostics.

**5. HTTP, Web API, OpenAPI, and push delivery**

- Added mutual TLS with PEM client certificates, static default headers, and configurable server-certificate and hostname verification.
- Improved HTTP error modeling through reason chains, preserved response bodies after decoding failures, and limited logged error bodies to 32 KiB.
- Added per-parameter date formatting and time-zone annotations, while improving canonical and legacy date parsing.
- Added modeled response cache control, configurable internal forwards, and streaming gzip response compression.
- Improved canonical routing, 404 handling, empty responses, oversized-request errors, and upload/delete mappings.
- Improved OpenAPI processor-binding alignment, YAML exports, configured API paths, and extension description resolution.
- Restored SSE push behavior, authenticated SSE channels, and cleaned up stale notification WebSockets.

**6. Databases, JDBC messaging, locking, and process execution**

- Added an **RX JDBC console**, with subsequent improvements to result handling, nullable cells, access control, and npm-published API models.
- Added composite-index metadata and Hibernate support, database update statement integration, query-result statistics, and auto-group-by fixes.
- Made Hibernate schema updates dependent on mapping fingerprints and added per-session-factory schema-generation configuration.
- Reworked JDBC messaging to store messages as resource-backed blobs and improved large-message handling and expiry checks.
- Improved PostgreSQL large-object cleanup for resources.
- Fixed JDBC locking issues involving stale state, reentrancy, lock ownership, refresh behavior, notifications, and database failures.
- Improved process failure handling and unattended revival; fixed duplicate root nodes when extending existing process definitions and corrected RX BPMN conversion behavior.
- Added audit-record archiving and improved Hikari logging.

**7. GenericModel, JavaScript, templating, and Explorer**

- Introduced model-driven templating and extension points for document/Word-oriented output sinks. This represents infrastructure for document templating; it does not by itself establish a complete Word product.
- Improved metadata annotations, partial value descriptor evaluation, explicitly typed JSON entity identity, YAML serialization, enum merging, and transient-property cloning.
- Added modeled request execution contexts and an anticipated-reason category; improved error reporting for messaging and fire-and-forget evaluations.
- Fixed JavaScript reflection recursion, null collection elements, entity attributes, cloning behavior, and model-resource routing.
- Added npm publishing metadata and restricted publishing to supported JavaScript runtime packages.
- Updated Explorer branding to Hiconic, added runtime configuration, and rebuilt it with resource-routing and WebSocket fixes.

**8. Developer tooling, CI, dependencies, and documentation**

- Introduced the Hiconic Gradle plugin, followed by model declaration, generated-reflection dependency, and classpath-indexing improvements.
- Migrated selected Devrock reflection and Wire enrichment functionality to Java's Class-File API.
- Updated CI Docker image definitions to Java 25 and Ubuntu 24.04; added npm to the SDK image. Commits to image definitions do not prove when every downstream environment adopted them.
- Added headless Eclipse plugin release automation and cumulative beta publishing; fixed scans hanging on unavailable directories.
- Updated ASM to 9.10.1 and Tomcat assets to 9.0.120.
- Improved repository filters, external-tool execution, Docker Compose working directories, and distribution of corrected Ant tasks through SDK/build dependencies.
- Added daily Maven artifact-index retention with five snapshots and a repository job-token publishing fallback.
- Created `hiconic-documentation`, with an initial combined Wire, GenericModel, and Reflex documentation version in October; removed an obsolete documentation link from the organization profile.