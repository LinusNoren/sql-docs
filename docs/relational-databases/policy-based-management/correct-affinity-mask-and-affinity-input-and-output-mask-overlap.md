---
title: "Correct affinity mask & affinity IO mask overlap policy"
description: Learn how to enable a policy that checks whether an instance of SQL Server has one ore more processors that are assigned to be used with both the affinity mask and the affinity I/O mask options for Policy-Based Management in SQL Server.
author: VanMSFT
ms.author: vanto
ms.date: "03/14/2017"
ms.service: sql
ms.subservice: security
ms.topic: conceptual
helpviewer_keywords:
  - "Best Practices [Database Engine]"
---
# Correct Affinity Mask and Affinity Input and Output Mask Overlap
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  This rule checks whether the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has one or more processors that are assigned to be used with both the affinity mask and the affinity I/O mask options. On a computer that has more than one processor, the affinity mask and the affinity I/O mask options are used to designate which CPUs are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Enabling a CPU with both the affinity mask and the affinity I/O mask can slow performance by forcing the processor to be overused.  
  
## Best Practices Recommendations  
 When you specify either the affinity mask or the affinity I/O mask options, you should specify both, but only enable each CPU no more than once.  
  
 Do not enable the same CPU in both the affinity mask option and the affinity I/O mask option. The bits that correspond to each CPU should be in one of the following states:  
  
-   0 in both the affinity mask option and the affinity I/O mask option  
  
-   0 in the affinity mask option and 1 in the affinity I/O mask option  
  
-   1 in the affinity mask option and 0 in the affinity I/O mask option  
  
## For More Information  
 [affinity mask Server Configuration Option](../../database-engine/configure-windows/affinity-mask-server-configuration-option.md)  
  
 [affinity Input-Output mask Server Configuration Option](../../database-engine/configure-windows/affinity-input-output-mask-server-configuration-option.md)  
  
 [affinity64 mask Server Configuration Option](../../database-engine/configure-windows/affinity64-mask-server-configuration-option.md)  
  
 [affinity64 Input-Output mask Server Configuration Option](../../database-engine/configure-windows/affinity64-input-output-mask-server-configuration-option.md)  
  
## See Also  
 [Monitor and Enforce Best Practices by Using Policy-Based Management](../../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
