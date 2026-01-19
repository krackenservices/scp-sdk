# SCP SDK

Python SDK for the **System Capability Protocol** (SCP) - programmatic access to manifests and graphs, plus a framework for building integrations.

## Features

- **Core Models**: Type-safe Pydantic models for SCP v0.1 manifests
- **Graph Abstraction**: Efficient querying and traversal of system dependencies
- **Integration Framework**: Reusable base classes and utilities for building integrations (60-80% code reduction)
- **Fully Tested**: Comprehensive test suite with pytest

## Installation

```bash
# Using uv (recommended)
uv add scp-sdk

# Or with pip
pip install scp-sdk
```

## Quick Example

```python
from scp_sdk import Manifest, Graph

# Load and query a manifest
manifest = Manifest.from_file("scp.yaml")
print(manifest.urn)  # urn:scp:payment-service
print(manifest.tier)  # 1

# Build and query a graph
graph = Graph.from_file("graph.json")
payment_svc = graph.find_system("urn:scp:payment-service")

# Get blast radius
dependents = graph.dependents_of(payment_svc)
print(f"{len(dependents)} systems depend on payment-service")
```

## Documentation

- **[Getting Started](getting-started.md)** - Installation and setup
- **[Examples](examples.md)** - Common usage patterns
- **[API Reference](api-reference.md)** - Manual API documentation
- **[Integration Guide](integration-guide.md)** - Building custom integrations

### Auto-Generated API Reference

- **[Core Module](reference/core.md)** - Models, Manifest, Graph, Export
- **[Integrations Module](reference/integrations.md)** - Integration framework
- **[Testing Module](reference/testing.md)** - Test fixtures and helpers
- **[Utilities Module](reference/utils.md)** - Tier utilities

## Related Projects

- [scp-definition](https://github.com/krackenservices/scp-definition) - SCP specification and JSON schema
- [scp-integrations](https://github.com/krackenservices/scp-integrations) - CLI tools for scanning and exporting
- [scp-viewer](https://github.com/krackenservices/scp-viewer) - Web dashboard for visualizing architectures
- [scp-demo](https://github.com/krackenservices/scp-demo) - Demo project for example models

## License

MIT
