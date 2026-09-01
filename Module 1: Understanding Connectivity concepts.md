# Module: Core AWS Networking & Connectivity Concepts
## 1. Core Concepts & Definitions
- **Software-Defined Networking (SDN):** Transition from physical network switches and cabling to dynamic, programmatic software configurations.
- **Shared Responsibility Model:** AWS manages physical network infrastructure, data centers, and hypervisors; the customer configures routing policies, VPC subnets, route tables, and security perimeters.

## 2. Fundamental Architectural Patterns
### Multi-Tier Architecture
Divides application components by functional layer to implement defense-in-depth security:

- **Presentation Tier:** Public-facing interface handling client requests (e.g., web servers).
- **Application (Logic) Tier:** Processes business logic and mediates communication between layers.
- **Data Tier:** Houses databases and storage systems behind internal boundaries.
