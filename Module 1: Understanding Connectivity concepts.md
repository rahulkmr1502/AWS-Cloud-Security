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

flowchart LR
    subgraph MultiVPC ["Multi-VPC Architecture"]
        subgraph AppVPC ["Application VPC"]
            APP[⚙️ Application Services]
        end

subgraph DataVPC ["Data VPC"]
            DATA[(🗄️ Database & Storage)]
        end

        subgraph SecVPC ["Security VPC"]
            SEC[🛡️ SecOps & Monitoring]
        end

        APP <-->|Internal Dedicated Link| DATA
        APP <-->|Security Inspections| SEC
        DATA <-->|Audit & Policy Logs| SEC
    end

    classDef vpcBox fill:#0f172a,stroke:#0284c7,stroke-width:2px,color:#f8fafc;
    classDef compBox fill:#1e293b,stroke:#38bdf8,stroke-width:1px,color:#f8fafc;
    class AppVPC,DataVPC,SecVPC vpcBox;
    class APP,DATA,SEC compBox;

