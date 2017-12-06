---
title: "활성 쿼리 (SQL Server PDW) 모니터링"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.prod: sql-non-specified
ms.prod_service: mpp-data-warehouse
ms.service: 
ms.component: analytics-platform-system
ms.technology: mpp-data-warehouse
ms.custom: 
ms.date: 01/13/2017
ms.reviewer: na
ms.suite: sql
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: bb73f790-0537-414b-8dc2-f1eb69b92362
caps.latest.revision: "7"
ms.openlocfilehash: b2975ef92cb3af808ea5698f1980af3f9d0996d1
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="monitoring-active-queries"></a>활성 쿼리 모니터링
이 항목에서는 활성 쿼리를 모니터링 하려면 관리 콘솔 및 SQL Server PDW 시스템 뷰를 사용 하는 방법을 보여 줍니다. 참조 [관리 콘솔을 사용 하 여 어플라이언스에 모니터링](monitor-the-appliance-by-using-the-admin-console.md) 및 [시스템 뷰](tsql-system-views.md) 이러한 도구에 대 한 내용은 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
활성 쿼리를 모니터링 하는 데 사용 하는 방법에 관계 없이 로그인 "사용 하 여 모든의 관리 콘솔에서"에서 설명 하는 권한이 있어야 합니다 [관리 콘솔을 사용할 수 있는 권한을 부여](grant-permissions.md#grant-permissions-to-use-the-admin-console)합니다.  
  
## <a name="PermsAdminConsole"></a>활성 쿼리 모니터  
관리 콘솔 및 SQL Server PDW 시스템 뷰를 모두 사용할 수 활성 쿼리를 모니터링 합니다. 아래 지침을 따릅니다.  
  
### <a name="to-monitor-active-queries-by-using-the-admin-console"></a>관리 콘솔을 사용 하 여 활성 쿼리를 모니터링 하려면  
  
1.  관리 콘솔에 로그온 합니다. 참조 [관리 콘솔을 사용 하 여 어플라이언스에 모니터링](monitor-the-appliance-by-using-the-admin-console.md) 지침에 대 한 합니다.  
  
2.  상단 메뉴에서 클릭 **쿼리**합니다. 쿼리, 쿼리 및 쿼리의 현재 상태에 대 한 시작 및 종료 시간을 제출한 로그인을 포함 하 여 장치에서 가장 최근 쿼리 하는 방법에 대 한 기본 정보가 포함 된 테이블이 표시 됩니다.  
  
3.  해당 행에 대해 왼쪽된 열에 쿼리 ID 위로 마우스 포인터를 가져가면 쿼리 명령을 확인 합니다.  
  
    에 특정 쿼리에 대해 자세한 정보를 보려면 쿼리 ID를 클릭 합니다. 전체 쿼리 및 쿼리 계획을 쿼리 실행의 각 단계에 대 한 상태 정보를 포함 하 여 정보가 표시 됩니다. 모든 오류를 반환 하는 경우에 오류에 세부 정보를 볼 수 있습니다. <!-- MISSING LINKS See [Understanding Query Plans &#40;SQL Server PDW&#41;](../sqlpdw/understanding-query-plans-sql-server-pdw.md) for information on how to interpret the query plan information available in the Admin Console.  -->
  
### <a name="to-monitor-active-queries-by-using-the-system-views"></a>시스템 뷰를 사용 하 여 활성 쿼리 모니터링  
쿼리를 모니터링 하는 데 사용 하는 주 시스템 뷰는 [sys.dm_pdw_exec_requests](../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-requests-transact-sql.md)합니다. 이 시스템 뷰를 사용 하 여 찾을 수는 `request_id` 쿼리 텍스트에 기반 하는 활성 또는 최근 쿼리에 대 한 합니다.  
  
예를 들어 다음 쿼리를 찾습니다는 `request_id` 및 현재 `status` 모든 열을 선택 하는 모든 쿼리에 `memberAddresses` 테이블입니다.  
  
```sql  
SELECT request_id, command, status   
FROM sys.dm_pdw_exec_requests   
WHERE command   
LIKE ‘%SELECT * FROM db1..memberAddresses%’;  
```  
  
후의 `request_id` 되었습니다의 다른 정보를 사용 하는 쿼리를 식별는 `dm_pdw_exec_requests` 쿼리 처리에 자세히 알아보려면 테이블 또는 사용 하 여 [sys.dm_pdw_request_steps](../relational-databases/system-dynamic-management-views/sys-dm-pdw-request-steps-transact-sql.md) 개별 쿼리 상태를 보려면 쿼리 실행에 대 한 단계입니다.  
  
<!-- MISSING LINKS 
## See Also  
[Common Metadata Query Examples &#40;SQL Server PDW&#41;](../sqlpdw/common-metadata-query-examples-sql-server-pdw.md)  
-->
  