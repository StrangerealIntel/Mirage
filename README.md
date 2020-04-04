# Mirage
### Description
#### Matrix ATT&amp;CK for Kubernetes from Microsoft

### Objectives
#### The goal of the repository is to create a JSON structure of the ATT&amp;CK for Kubernetes from Microsoft that can be used for integrate to a web panel of a wiki or an render like MITRE ATT&amp;CK Navigator for sharing propose.

### Concept
#### Get and convert to JSON

```csharp
> $j = (Get-Content -Path '.\ATT&CK_Kubernetes_V1.0.json')| ConvertFrom-Json
```
#### The structure of the header content the description, the versioning, the reference and the matrice to the framework

```csharp
> $j |Format-List  

description : Matrix ATT&CK for Kubernetes from Microsoft
version     : 1.0
reference   : https://www.microsoft.com/security/blog/2020/04/02/attack-matrix-kubernetes/
matrix      : {@{id=Ini1; name=Using cloud credentials; description=In cases where the Kubernetes cluster is deployed in a public cloud ...}
```

#### The matrice section content id, name of TTPs, a short description and a reference (this can be a URL from a page of the Wiki like MITRE wiki or from your tools).

```csharp
> $j.matrix[0]|Format-List

id          : Ini1
name        : Using cloud credentials
description : In cases where the Kubernetes cluster is deployed in a public cloud (like AKS in Azure, GKE in GCP, or EKS in AWS), compromised cloud credential can lead to cluster takeover. Attackers who have access to the 
              cloud account credentials can get access from the layer of cluster management.
reference   :
