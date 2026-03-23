# Design deep dive

#### Infrastructure as Code

Think of Infrastructure as Code like a detailed architectural blueprint for a building. Just as the same blueprint can be handed to different construction companies to build the same structure, IaC definitions describe your infrastructure in a provider-neutral way that can be executed on any cloud platform. Modern IaC tools enable:

**Declarative Infrastructure Definition**: Infrastructure requirements expressed in provider-neutral formats can be translated to provider-specific implementations through abstraction layers. Tools such as **Terraform, Pulumi, and Crossplane** allow teams to define infrastructure once and deploy across multiple targets.

**Repeatable Deployment Patterns**: One-click deployment capabilities, once limited to proprietary platforms, now extend to cloud-agnostic configurations. This democratizes DPI deployment, allowing jurisdictions to stand up infrastructure rapidly while maintaining portability.

**Version-Controlled Infrastructure**: Infrastructure definitions stored in version control systems provide auditability, rollback capabilities, and collaborative development workflows that enhance governance.

#### Containerization and Orchestration

Containers work like standardized shipping containers in global trade. Before containerization, cargo had to be individually loaded and unloaded for each type of ship or truck. Standardized containers meant any cargo could travel on any vessel. Similarly, application containers package software so it runs identically whether on a developer's laptop, an AWS server, or an on-premises data center.

**Application Portability**: Applications packaged as containers run consistently across environments, from developer workstations to production clusters across different cloud providers.

**Orchestration Abstraction**: **Kubernetes** has emerged as a de facto standard for container orchestration. While cloud providers offer managed Kubernetes services with proprietary extensions, the core API remains portable, allowing workloads to migrate with minimal modification.

**Service Mesh Independence**: Service mesh technologies provide cross-cutting concerns such as observability, security, and traffic management in a provider-neutral manner.

#### Data Layer Considerations

If containers solve the portability of applications, data portability is the harder problem — and the more consequential one. Applications can be redeployed in minutes; migrating terabytes of citizen data takes planning and time. Data architecture decisions made early constrain choices for years:

**Database Abstraction**: Selecting database technologies available across providers---or that can be self-hosted---preserves portability. Open-source databases offer maximum flexibility, while cloud-native databases create dependencies that must be carefully evaluated.

**Storage Portability**: Object storage APIs have converged around S3-compatible interfaces, providing reasonable portability for unstructured data. Block and file storage present greater challenges and may require abstraction layers.

**Data Gravity**: As a dataset grows larger, it becomes increasingly expensive and time-consuming to move — much like how a growing library becomes harder to relocate. A national identity database with tens of millions of records creates a "gravitational pull" that attracts related processing to wherever the data physically resides. Architects should plan for this by designing systems where analytics and processing workloads can be deployed alongside the data, rather than assuming data can always move to the computation.

| **Architectural Principle**      | **Enabling Standards & Frameworks**                             | **Key Tools**                                 |
| -------------------------------- | --------------------------------------------------------------- | --------------------------------------------- |
| Infrastructure as Code           | HCL (Terraform), YAML (Pulumi), Kubernetes manifests            | Terraform, Pulumi, Crossplane, Ansible        |
| Containerization & Orchestration | Open Container Initiative (OCI), Kubernetes API, CNCF ecosystem | Kubernetes, Helm, Istio/Linkerd, ArgoCD       |
| Data Layer Portability           | S3-compatible APIs, SQL standards, OpenTelemetry                | PostgreSQL, MinIO, Prometheus, Grafana        |
| Security & Policy                | SPIFFE/SPIRE identity framework, Open Policy Agent              | OPA/Gatekeeper, HashiCorp Vault, Cert-Manager |
