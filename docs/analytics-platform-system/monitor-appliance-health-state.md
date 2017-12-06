---
title: "모니터 어플라이언스 상태 (분석 플랫폼 시스템)"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.prod: sql-non-specified
ms.prod_service: mpp-data-warehouse
ms.service: 
ms.component: analytics-platform-system
ms.technology: mpp-data-warehouse
ms.custom: 
ms.date: 01/05/2017
ms.reviewer: na
ms.suite: sql
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 91132e3c-3137-4670-adaa-8a7b234fb8d2
caps.latest.revision: "12"
ms.openlocfilehash: dad3355061bafcbbfa3a34b21d2043b0411129ba
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="monitor-appliance-health-state"></a>모니터 어플라이언스 상태
이 SQL Server PDW 동적 관리 뷰를 직접 쿼리하여 또는 관리 콘솔을 사용 하 여 SQL Server PDW 어플라이언스의 상태를 모니터링 하는 방법을 설명 합니다.  
  
## <a name="to-monitor-the-appliance-state"></a>어플라이언스 상태를 모니터링 하려면  
시스템 관리자는 노드, 구성 요소 및 소프트웨어의 전체 계층 구조를 검색 하 관리 콘솔 또는 SQL Server PDW 동적 관리 뷰 (Dmv)를 사용할 수 있습니다. 다음 다이어그램에서는 SQL Server PDW를 모니터링 하는 구성 요소에 대 한 높은 수준의 이해를 제공 합니다.  
  
![모니터링 개요](./media/monitor-appliance-health-state/SQL_Server_PDW_Monitoring_Overview.png "SQL_Server_PDW_Monitoring_Overview")  
  
### <a name="monitor-component-status-by-using-the-admin-console"></a>관리 콘솔을 사용 하 여 구성 요소 상태 모니터링  
관리 콘솔을 사용 하 여 구성 요소 상태를 검색:  
  
1.  클릭는 **기기 상태** 탭 합니다.  
  
2.  어플라이언스 상태 페이지에서 노드 정보를 보려면 특정 노드를 클릭 합니다.  
  
    ![PDW 관리 콘솔 상태](./media/monitor-appliance-health-state/SQL_Server_PDW_AdminConsol_State.png "SQL_Server_PDW_AdminConsol_State")  
  
### <a name="monitor-component-status-by-using-system-views"></a>시스템 뷰를 사용 하 여 구성 요소 상태 모니터링  
시스템 뷰를 사용 하 여 구성 요소 상태를 검색 하려면 사용 [sys.dm_pdw_component_health_status](../relational-databases/system-dynamic-management-views/sys-dm-pdw-component-health-status-transact-sql.md)합니다. 예를 들어 다음 쿼리는 모든 구성 요소에 대 한 상태를 검색합니다.  
  
```sql  
SELECT   
   s.[pdw_node_id],  
   n.[name] as [node_name],  
   n.[address] ,  
   g.[group_id] ,  
   g.[group_name] ,  
   c.[component_id] ,  
   c.[component_name] ,  
   s.[component_instance_id] ,   
   p.[property_name] ,  
   s.[property_value] ,  
   s.[update_time]  
FROM [sys].[dm_pdw_component_health_status] AS s  
JOIN sys.dm_pdw_nodes AS n   
   ON s.[pdw_node_id] = n.[pdw_node_id]  
JOIN [sys].[pdw_health_components] AS c   
   ON s.[component_id] = c.[component_id]  
JOIN [sys].[pdw_health_component_groups] AS g   
   ON c.[group_id] = g.[group_id]  
JOIN [sys].[pdw_health_component_properties] AS p   
   ON s.[property_id] = p.[property_id] AND s.[component_id] = p.[component_id]  
WHERE p.property_name = 'Status'  
ORDER BY  
   s.[pdw_node_id],  
   g.[group_name] ,   
   s.[component_instance_id] ,  
   c.[component_name] ,   
   p.[property_name];  
```  
  
Status 속성에 대해 반환 되는 가능한 값은 같습니다.  
  
-   확인  
  
-   치명적이 지 않음  
  
-   심각  
  
-   Unknown  
  
-   지원되지 않음  
  
-   연결할 수 없습니다.  
  
-   복구할 수 없는  
  
모든 구성 요소에 대 한 모든 속성을 보려면 제거는 `WHERE  p.property_name = 'Status'` 절.  
  
**[update_time]** 열 구성 요소에서 SQL Server PDW 상태 에이전트 폴링된 마지막 시간을 보여 줍니다.  
  
> [!CAUTION]  
> 5 분 이상 동안; 구성 요소에 폴링 되지 때 문제를 조사 해야 합니다. 소프트웨어 하트 비트 문제를 나타내는 경고가 있을 수 있습니다.  
  
## <a name="see-also"></a>관련 항목:  
<!-- MISSING LINKS [Common Metadata Query Examples &#40;SQL Server PDW&#41;](../sqlpdw/common-metadata-query-examples-sql-server-pdw.md)  -->  
[어플라이언스 모니터링 &#40; 분석 플랫폼 시스템 &#41;](appliance-monitoring.md)  
  