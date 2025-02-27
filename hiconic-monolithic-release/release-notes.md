# Hiconic Monolitic Release Notes ${version}

<table>
  <tr><td>Group Id</td><td><b>${groupId}</b></td></tr>
  <tr><td>Artifact Id</td><td><b>${artifactId}</b></td></tr>
  <tr><td>Version</td><td><b>${version}</b></td></tr>
  <tr><td>Release Date</td><td><b>${date}</b></td></tr>
</table>

## Changes

### Compatibility

* [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)
* Java 21
* Removed vulnerabilities: `org.jsoup:jsoup`, `ehcache`, `jackson-databind`, `swagger`, `commons-io`, `jquery`, `zip4j`, `commons-compress`, `tika`, `junit`, `io.jsonwebtoken`, `netty-handler`, `velocity-engine-core`, `okio`, `jsoup`

### SDK

* Hiconic SDK + Tutorial
* Portable CI/CD pipeline based on hiconic and reflex
* GitHub pipeline workflows

### Distributed Computing

* locking
    * API redesign
    * SQL based for best compatibility in cloud environments
    * reentrant distributed locks
    * lock heartbeat system to prevent blocking stale locks
* leadership
    * based on locking

### BPM / Workflow

* ProcessingEngine replaced by ProcessManager `tribefire.extension.process`
* dedicated versatile process api model `process-api-model`
* dedicated reasoning for controlled error handling
* simplified, efficient, decoupled, and flat process tracing
* process locking with distributed reentrant locks
* robust in-situ process halting and fixing in case of reasons or exceptions
* process definition via BPMN

### Authentication and Authorization

* modularized
* replaced exceptions by dedicated reasons

### Modeled Services (DDSA)

* GraphQL client
* introduced reasoning

### Hiconic JS

* NPM packages:
  * `@dev.hiconic/runtime`
  * `@dev.hiconic/tf.js_hc-js-api`
* published to `https://www.npmjs.com/`
* TypeScript typesafety for models and runtime
* pipeline support for model NPM packages

### Local First JS

* NPM package: `@dev.hiconic/local-first`
* published to `https://www.npmjs.com/`
* managed entities
* stored in signed, encrypted CRDT transactions in indexedDB
* native generic JSON marshaller for all hiconic data
* native dedicated JSON marshaller for compact `manipulation-model` data
* entity/property signals for solid-js

### Reflex Platform - 

* Modeled, Modular, and Wired Microservices
* unit-test support
* Modules
    * `web-server-rx-module`
    * `rest-verver-rx-module`
    * `web-api-server-rx-module`
    * `web-rpc-server-rx-module`
    * `websocket-server-rx-module`
    * `security-rx-module`
    * `validation-rx-module`
    * `db-rx-module`
    * `cli-rx-module`
    * `hibernate-rx-module`

