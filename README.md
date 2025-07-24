# Azure Architect

Demos, notes, links

## 0 - Intro

- [Exam](https://learn.microsoft.com/credentials/certifications/exams/az-305/)
- [Study Guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/az-305)
- [Case Studies](https://microsoftlearning.github.io/AZ-305-DesigningMicrosoftAzureInfrastructureSolutions/)
- [Azure Charts](https://azurecharts.com/)
- [Azure Icons](https://learn.microsoft.com/en-us/azure/architecture/icons/)
- [Cloud Adoption Framework](https://learn.microsoft.com/azure/cloud-adoption-framework/)
- [Cloud Adoption Journey](https://azure.microsoft.com/cloud-adoption-framework/#cloud-adoption-journey)
- [Azure Migrate overview](https://learn.microsoft.com/azure/cloud-adoption-framework/migrate/azure-migration-guide)
- [Learn: Cloud Adption Framework](https://learn.microsoft.com/learn/modules/microsoft-cloud-adoption-framework-for-azure/)
- [Well Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/)
- [Learn materials](https://learn.microsoft.com/en-us/training/courses/az-305t00)
- [GitHub Case Studies](https://github.com/MicrosoftLearning/AZ-305-DesigningMicrosoftAzureInfrastructureSolutions)

## 1 - Governance

- [Larn module](https://learn.microsoft.com/training/modules/design-governance/)
- [Case study](https://microsoftlearning.github.io/AZ-305-DesigningMicrosoftAzureInfrastructureSolutions/Instructions/CaseStudy/01-Governance.html)
- [Management Groups](https://learn.microsoft.com/azure/cloud-adoption-framework/ready/landing-zone/design-area/resource-org-management-groups)
- [Subscriptions decision guide](https://learn.microsoft.com/azure/cloud-adoption-framework/decision-guides/subscriptions/)
- [What is ARM](https://docs.microsoft.com/azure/azure-resource-manager/management/overview)
- [Resource naming convention](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-naming)
- [Resource tagging](https://learn.microsoft.com/azure/cloud-adoption-framework/ready/azure-best-practices/resource-tagging)
- [Best practices: tagging](https://learn.microsoft.com/azure/cloud-adoption-framework/ready/azure-best-practices/resource-tagging)
- [Resource tagging patterns](https://learn.microsoft.com/azure/cloud-adoption-framework/decision-guides/resource-tagging/?toc=/azure/azure-resource-manager/management/toc.json#resource-tagging-patterns)

## 2 - Compute

- [Learn module](https://learn.microsoft.com/en-us/training/modules/design-compute-solution/)^
- [Compute - Decision tree](https://learn.microsoft.com/en-us/azure/architecture/guide/technology-choices/compute-decision-tree)
- [Case Study](https://microsoftlearning.github.io/AZ-305-DesigningMicrosoftAzureInfrastructureSolutions/Instructions/CaseStudy/02-Compute.html)

## 3 - Non-relational data

- [Learn module](https://learn.microsoft.com/training/modules/design-data-storage-solution-for-non-relational-data/)
- [Case study](https://microsoftlearning.github.io/AZ-305-DesigningMicrosoftAzureInfrastructureSolutions/Instructions/CaseStudy/03-Nonrelationalstorage.html)


### Latency & IOPS Overview

| Tier | Access Latency | IOPS Characteristics | Notes |
|-----|----|----|----|
| Hot | Lowest (milliseconds) | High and consistent | Ideal for frequent reads/writes | 
| Cool | Slightly higher (still milliseconds) | Comparable to Hot | Best for infrequent access, backups | 
| Cold | Millisecond-level | Similar to Hot/Cool | Optimized for rarely accessed data | 
| Archive | Hours (rehydration required) | Not applicable until rehydrated | Offline tier; not suitable for active workloads | 

🧠 Key Insights
- Hot, Cool, and Cold tiers all offer millisecond-level latency and similar throughput and IOPS, making them suitable for online access.
- The main differences lie in availability SLAs, early deletion penalties, and costs—not raw performance.
- Archive tier is a different beast: it’s offline and requires rehydration (up to 15 hours) before access, so it’s not part of the IOPS conversation.
Microsoft doesn’t publish exact IOPS numbers for each tier because performance is influenced by factors like blob size, concurrency, and region. But for most workloads, Hot, Cool, and Cold tiers behave similarly in terms of responsiveness.

## 4 - Relational data

- [Learn module](https://learn.microsoft.com/training/modules/design-data-storage-solution-for-relational-data/)
- [Case study](https://microsoftlearning.github.io/AZ-305-DesigningMicrosoftAzureInfrastructureSolutions/Instructions/CaseStudy/04-Relationalstorage.html)

## 5 - Data integration

- [Learn module](https://learn.microsoft.com/training/modules/design-data-integration/)
- No case study

More information:

- [Explore concepts of data analytics](https://learn.microsoft.com/en-us/training/modules/explore-concepts-of-data-analytics/)
- [Data integration at scale with Azure Data Factory or Azure Synapse Pipeline](https://learn.microsoft.com/en-us/training/paths/data-integration-scale-azure-data-factory/)
- [Explore Azure Databricks](https://learn.microsoft.com/en-us/training/modules/explore-azure-databricks/)
- [Introduction to Azure Data Lake Storage Gen2](https://learn.microsoft.com/en-us/training/modules/explore-azure-databricks/)
- [Introduction to end-to-end analytics using Microsoft Fabric](https://learn.microsoft.com/en-us/training/modules/introduction-end-analytics-use-microsoft-fabric/)

### 🧰 Feature Comparison
| Platform | Core Purpose | Key Features | Integration & Use Cases | 
|-----|-------|-----------|-------------|
| Azure Data Lake | Scalable storage for big data | - Hierarchical namespace<br>- Hadoop-compatible<br>- Tiered storage options | - Stores structured & unstructured data<br>- Used with Spark, Synapse | 
| Azure Data Factory | Data integration & ETL orchestration | - 180+ connectors<br>- Data pipelines<br>- Mapping Data Flows | - ETL/ELT workflows<br>- Hybrid data movement<br>- SSIS support | 
| Azure Databricks | Advanced analytics & machine learning | - Apache Spark engine<br>- Collaborative notebooks<br>- ML & AI support | - Big data processing<br>- Real-time analytics<br>- ML pipelines | 
| Azure Synapse | Unified analytics & data warehousing | - Serverless & dedicated SQL pools<br>- Spark integration<br>- Data Explorer | - BI, data warehousing<br>- Real-time telemetry<br>- SQL + Spark | 
| Microsoft Fabric | End-to-end analytics platform | - OneLake unified storage<br>- Copilot AI<br>- Real-time & BI tools | - Combines Synapse, Power BI, Data Factory<br>- AI-powered insights | 

### 💰 Pricing Overview
| Platform | Pricing Model | Estimated Monthly Cost (Typical Usage) |
|-----|-------|-----------|
| Azure Data Lake | Pay-as-you-go (based on GB stored & ops) | - Hot: ~$0.15/GB<br>- Cool: ~$0.02/GB<br>- Archive: ~$0.002/GB | 
| Azure Data Factory | Based on pipeline runs, DIU hours, data ops | - Orchestration: ~$1 per 1,000 runs<br>- Data movement: ~$0.25/DIU-hour | 
| Azure Databricks | VM + DBU (Databricks Unit) usage | - Jobs Compute: ~$0.30/DBU<br>- All-Purpose: ~$0.55/DBU | 
| Azure Synapse | Serverless (per query) or Dedicated (DWU) | - Serverless SQL: ~$5/TB processed<br>- Dedicated SQL: ~$1.20/hour for DWU100 | 
| Microsoft Fabric | Capacity-based (F SKUs) + OneLake storage | - F2: ~$262/month<br>- F64: ~$8,409/month<br>- OneLake: ~$0.023/GB | 

### 🧠 Summary
- Azure Data Lake is best for scalable, secure storage of raw data.
- Azure Data Factory excels at orchestrating data movement and transformation.
- Azure Databricks is ideal for data scientists and engineers working on ML and big data.
- Azure Synapse Analytics offers a powerful hybrid of SQL and Spark for enterprise analytics.
- Microsoft Fabric unifies all these capabilities into a single, AI-powered platform with seamless integration.

## 6 - Application Architecture

- [Learn module](https://learn.microsoft.com/training/modules/design-application-architecture/)
- [Case study](https://microsoftlearning.github.io/AZ-305-DesigningMicrosoftAzureInfrastructureSolutions/Instructions/CaseStudy/06-Apparchitecture.html)
- [Serverless functions reference architecture](https://learn.microsoft.com/azure/architecture/serverless-quest/reference-architectures)

## 7 - Design Authentication and Authorization Solutions

- [Learn module](https://learn.microsoft.com/training/modules/design-authentication-authorization-solutions/)
- [Case study](https://microsoftlearning.github.io/AZ-305-DesigningMicrosoftAzureInfrastructureSolutions/Instructions/CaseStudy/07-Access.html)

### Using Managed Identities in On-Premises Environments

#### Azure Arc–enabled servers

Applications or processes running on Azure Arc-enabled servers can use system-assigned managed identities to obtain tokens for any Entra-protected resource. To set this up, install the Azure Connected Machine agent on your non-Azure server; behind the scenes it exposes a local identity endpoint that your code can call for tokens.

Documentation: https://learn.microsoft.com/en-us/azure/azure-arc/servers/managed-identity-authentication

#### Azure Automation Hybrid Workers
You can run runbooks on on-prem machines under the authentication context of a Managed Identity. Configure a Hybrid Worker Group in your Automation Account, enable the account’s managed identity, install the Hybrid Worker agent on your on-prem VM, then target that group when you start the runbook. This lets your on-prem script call Azure services (Key Vault, Storage, etc.) without storing credentials.

Blog post: https://www.dcac.com/2023/11/27/azure-managed-identity-on-premises/

#### Microsoft Entra cloud-governed management for on-premises workloads

Learn how to extend Entra ID’s identity governance and secure remote access to AD-integrated and federation-based applications running on-prem. Topics include Application Proxy, lifecycle management for on-prem AD accounts, B2B collaboration, and unified governance for both cloud and on-prem apps.

Documentation: https://learn.microsoft.com/en-us/entra/identity/hybrid/connect/cloud-governed-management-for-on-premises

### Managed Identities Across Entra Tenants (Multi-Tenant Scenarios)

#### Federated Identity Credentials for Entra Apps (GA)

You can now configure a user-assigned managed identity as a federated credential on an Entra App registration. This establishes trust so that workloads running under that managed identity—across tenants—can request tokens for your multi-tenant app without secrets or certificates.

Announcing blog: https://devblogs.microsoft.com/identity/access-cloud-resources-across-tenants-without-secrets-ga/

#### Securing managed identities in Microsoft Entra ID

Deep dive into system-assigned vs. user-assigned identities, how token acquisition and RBAC work for both control- and data-plane operations, and best practices for least-privilege and auditing.

Documentation: https://learn.microsoft.com/en-us/entra/architecture/service-accounts-managed-identities

[Microsoft Secure Future Initiative](https://www.microsoft.com/en-us/trust-center/security/secure-future-initiative)

## 8 - Design a solution to log and monitor Azure resources

- [Learn module](https://learn.microsoft.com/training/modules/design-solution-to-log-monitor-azure-resources/)
- [Case study](https://microsoftlearning.github.io/AZ-305-DesigningMicrosoftAzureInfrastructureSolutions/Instructions/CaseStudy/08-Logging.html)

### Reference modules

- [Design a full-stack monitoring strategy on Azure](https://learn.microsoft.com/training/modules/design-monitoring-strategy-on-azure/)
- [Analyze your Azure infrastructure by using Azure Monitor logs](https://learn.microsoft.com/learn/modules/analyze-infrastructure-with-azure-monitor-logs/)
- [Monitor your Azure virtual machines with Azure Monitor](https://learn.microsoft.com/training/modules/monitor-azure-vm-using-diagnostic-data/)
- [Monitor app performance](https://learn.microsoft.com/training/modules/monitor-app-performance/)

### Optional exercise

- [Enabling storage metrics and view metric data](https://learn.microsoft.com/en-us/training/modules/monitor-diagnose-and-troubleshoot-azure-storage/4-exercise-storage-metrics)

## 9 - Design a network solution

- [Learn module](https://learn.microsoft.com/training/modules/design-network-solutions/)
- [Defense in depth - Video](https://learn.microsoft.com/shows/azure-videos/defense-in-depth-security-in-azure)
- [Case study](https://microsoftlearning.github.io/AZ-305-DesigningMicrosoftAzureInfrastructureSolutions/Instructions/CaseStudy/09-Networkingoption2.html)

## 10 - Design a business continuity solution

- [Learn module](https://learn.microsoft.com/training/modules/design-solution-for-backup-disaster-recovery/)
- No case study

## 11 - Designing Microsoft Azure Infrastructure Solutions

- [Learn module](https://learn.microsoft.com/training/modules/design-migrations/)
- No case study
