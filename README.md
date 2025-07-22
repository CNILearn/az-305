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

## 01 - Governance

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
- [Case study](https://learn.microsoft.com/training/modules/design-data-storage-solution-for-relational-data/)

## 5 - Data integration

- [Learn module](https://learn.microsoft.com/training/modules/design-data-integration/)
- [Case study](https://learn.microsoft.com/training/modules/design-data-storage-solution-for-relational-data/)
