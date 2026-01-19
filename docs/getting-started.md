# Getting Started

## Installation

### Using uv (Recommended)

```bash
uv add scp-sdk
```

### Using pip

```bash
pip install scp-sdk
```

### From Source

```bash
git clone https://github.com/krackenservices/scp-sdk.git
cd scp-sdk
uv sync
```

## Basic Usage

### Loading Manifests

```python
from scp_sdk import Manifest

# Load from file
manifest = Manifest.from_file("scp.yaml")

# Or from YAML string
yaml_str = """
scp: "0.1.0"
system:
  urn: "urn:scp:payment-service"
  name: "Payment Service"
  classification:
    tier: 1
"""
manifest = Manifest.from_yaml(yaml_str)

# Access properties
print(manifest.urn)   # urn:scp:payment-service
print(manifest.name)  # Payment Service
print(manifest.tier)  # 1
```

### Working with Graphs

```python
from scp_sdk import Graph

# Load from unified JSON (from scp-cli scan --export json)
graph = Graph.from_file("graph.json")

# Query systems
for system in graph.systems():
    print(f"{system.name} (Tier {system.tier})")

# Find dependencies
payment = graph.find_system("urn:scp:payment-service")
deps = graph.dependencies_of(payment)
print(f"Payment service depends on {len(deps)} systems")

# Get blast radius
dependents = graph.dependents_of(payment)
print(f"{len(dependents)} systems would be affected if payment fails")
```

## Next Steps

- See [Examples](examples.md) for common usage patterns
- Read the [Integration Guide](integration-guide.md) to build custom integrations
- Explore the [API Reference](reference/core.md) for detailed documentation
