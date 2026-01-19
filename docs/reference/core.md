# Core Module Reference

Auto-generated API documentation for `scp_sdk.core`.

## Models

Data models representing SCP manifest structure.

::: scp_sdk.core.models.SCPManifest
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.models.System
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.models.Classification
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.models.Ownership
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.models.Contact
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.models.Capability
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.models.Contract
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.models.SLA
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.models.SecurityExtension
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.models.Dependency
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.models.RetryConfig
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.models.CircuitBreakerConfig
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.models.Constraints
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.models.Runtime
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.models.Environment
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.models.FailureMode
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.models.ValidationIssue
options:
show_root_heading: true
heading_level: 3

---

## Manifest

High-level API for loading and querying SCP manifests.

::: scp_sdk.core.manifest.Manifest
options:
show_root_heading: true
heading_level: 3
members: - from_file - from_yaml - urn - name - tier - domain - team - get_dependency - dependencies - capabilities - get_otel_service_name

---

## Graph

Graph abstraction for analyzing system dependencies.

::: scp_sdk.core.graph.Graph
options:
show_root_heading: true
heading_level: 3
members: - from_file - from_dict - from_manifests - systems - dependencies - find_system - dependencies_of - dependents_of - validate - to_dict - to_json

::: scp_sdk.core.graph.SystemNode
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.graph.DependencyEdge
options:
show_root_heading: true
heading_level: 3

---

## Export / Import

Functions for working with the unified JSON graph format.

::: scp_sdk.core.export.export_graph_json
options:
show_root_heading: true
heading_level: 3

::: scp_sdk.core.export.import_graph_json
options:
show_root_heading: true
heading_level: 3
