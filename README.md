# flux-fleet

Example of flux management repo

Notes:

* vendor-locked to EKS
* everythong with `PLACEHOLDER` should be set to correct values: secrets, arns, etc
* secrets should be encrypted
* renovate updates stage cluster's HelmReleases, prod is updated manually at later point

## Design

```mermaid
graph LR
  subgraph flux-fleet
    subgraph ./clusters
      subgraph ./clusters/prod
        subgraph ./clusters/prod/infrastructure
          cl_prod_infra_ks[kustomization.yaml] --> cl_prod_infra_karpenter(karpenter.yaml) & cl_prod_infra_monitoring(monitoring.yaml)
        end
      end
      subgraph ./clusters/stage
        subgraph ./clusters/stage/infrastructure
          cl_stage_infra_ks[kustomization.yaml] --> cl_stage_infra_karpenter(karpenter.yaml) & cl_stage_infra_monitoring(monitoring.yaml)
        end
      end
    end

    subgraph ./infrastructure
      subgraph ./infrastructure/karpenter
        infra_karpenter_stage(stage) & infra_karpenter_prod(prod) --> infra_karpenter_base(base)
      end
      subgraph ./infrastructure/monitoring
        infra_monitoring_stage(stage) & infra_monitoring_prod(prod) --> infra_monitoring_base(base)
      end
    end

    cl_stage_infra_karpenter -.-> infra_karpenter_stage
    cl_stage_infra_monitoring -.-> infra_monitoring_stage
    cl_prod_infra_karpenter -.-> infra_karpenter_prod
    cl_prod_infra_monitoring -.-> infra_monitoring_prod
  end

```
