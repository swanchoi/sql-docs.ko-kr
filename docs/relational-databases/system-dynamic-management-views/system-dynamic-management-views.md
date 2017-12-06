---
title: "동적 관리 뷰 (Transact SQL) | Microsoft Docs"
ms.custom: 
ms.date: 06/29/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: TSQL
helpviewer_keywords:
- database scoped dynamic management objects [SQL Server]
- dynamic management objects [SQL Server], about dynamic management objects
- server state information [SQL Server]
- dynamic management functions [SQL Server]
- metadata [SQL Server], dynamic management objects
- dynamic management views [SQL Server]
- DMVs [SQL Server]
- functions [SQL Server], dynamic management
- server scoped dynamic management objects [SQL Server]
- dynamic management objects [SQL Server]
ms.assetid: cf893ecb-0bf6-4cbf-ac00-8a1099e405b1
caps.latest.revision: "41"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Active
ms.openlocfilehash: 97d8db9f9e697b72deecc59f6dbb0674b5061f0d
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="system-dynamic-management-views"></a>시스템 동적 관리 뷰
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  동적 관리 뷰 및 함수는 서버 인스턴스 상태 모니터링, 문제 진단 및 성능 튜닝에 사용할 수 있는 서버 상태 정보를 반환합니다.  
  
> [!IMPORTANT]  
>  동적 관리 뷰 및 함수는 내부 구현과 관련된 상태 데이터를 반환합니다. 이렇게 반환되는 스키마와 데이터는 이후 버전의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 변경될 수 있습니다. 따라서 다음 번 릴리스의 동적 관리 뷰 및 함수는 이번 릴리스의 동적 관리 뷰 및 함수와 호환되지 않을 수 있습니다. 예를 들어 이후 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 릴리스에서 Microsoft가 열 목록의 끝에 열을 추가하여 동적 관리 뷰의 정의를 보강할 수 있습니다. 반환된 열 수가 응용 프로그램을 바꾸거나 중단할 수 있으므로 프로덕션 코드에서는 `SELECT * FROM dynamic_management_view_name` 구문을 사용하지 않는 것이 좋습니다.  
  
 동적 관리 뷰 및 함수에는 다음과 같은 두 가지 유형이 있습니다.  
  
-   서버 범위 동적 관리 뷰 및 함수. 이 유형에는 서버에 대한 VIEW SERVER STATE 권한이 필요합니다.  
  
-   데이터베이스 범위 동적 관리 뷰 및 함수. 이 유형에는 데이터베이스에 대한 VIEW DATABASE STATE 권한이 필요합니다.  
  
## <a name="querying-dynamic-management-views"></a>동적 관리 뷰 쿼리  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문에서 두 부분, 세 부분 또는 네 부분으로 된 이름을 사용하여 동적 관리 뷰를 참조할 수 있습니다. 한편 동적 관리 함수는 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문에서 두 부분이나 세 부분으로 된 이름을 사용하여 참조할 수 있습니다. [!INCLUDE[tsql](../../includes/tsql-md.md)] 문에서 한 부분으로 된 이름을 사용하여 동적 관리 뷰 및 함수를 참조할 수는 없습니다.  
  
 모든 동적 관리 뷰 및 함수는 sys 스키마에 있어야 하며 dm_* 명명 규칙을 따라야 합니다. 동적 관리 뷰 또는 함수를 사용할 경우 뷰 또는 함수 이름에 sys 스키마 접두사를 지정해야 합니다. 예를 들어 dm_os_wait_stats 동적 관리 뷰를 쿼리하려면 다음 쿼리를 실행합니다.  
  
 ```tsql
SELECT wait_type, wait_time_ms  
FROM sys.dm_os_wait_stats;  
```  
  
### <a name="required-permissions"></a>필요한 권한  
 동적 관리 뷰 또는 함수를 쿼리하려면 개체에 대한 SELECT 권한과 VIEW SERVER STATE 또는 VIEW DATABASE STATE 권한이 필요합니다. 이러한 사용 권한을 통해 동적 관리 뷰 및 함수에 대한 사용자 또는 로그인의 액세스를 선택적으로 제한할 수 있습니다. 이렇게 하기 위해서는 먼저 master에 사용자를 만든 다음 사용자가 액세스할 수 없도록 할 동적 관리 뷰 또는 함수에 대한 사용자의 SELECT 권한을 거부합니다. 그러면 사용자의 데이터베이스 컨텍스트에 관계없이 사용자가 이러한 동적 관리 뷰 또는 함수에서 선택할 수 없게 됩니다.  
  
> [!NOTE]  
>  DENY가 우선 적용되기 때문에 사용자에게 VIEW SERVER STATE 권한을 부여했지만 VIEW DATABASE STATE 권한을 거부한 경우 해당 사용자는 서버 수준 정보는 볼 수 있지만 데이터베이스 수준 정보는 볼 수 없습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 동적 관리 뷰 및 함수는 다음 범주로 구분됩니다.  
  
|||  
|-|-|  
|[Always On 가용성 그룹 동적 관리 뷰 및 Funtions (Transact SQL)](../../relational-databases/system-dynamic-management-views/always-on-availability-groups-dynamic-management-views-functions.md)|[메모리 액세스에 최적화 된 테이블 동적 관리 뷰 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/memory-optimized-table-dynamic-management-views-transact-sql.md)|  
|[변경 데이터 캡처 관련 동적 관리 뷰&#40;Transact-SQL&#41;](http://msdn.microsoft.com/library/2a771d7d-693a-4f56-9227-02cd00e0e200)|[개체 관련 동적 관리 뷰 및 함수 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/object-related-dynamic-management-views-and-functions-transact-sql.md)|  
|[변경 내용 추적 관련 동적 관리 뷰](http://msdn.microsoft.com/library/dc8a0af9-fcd8-4c34-9453-5132717c9bdb)|[쿼리 알림 관련된 동적 관리 뷰 &#40; Transact SQL &#41;](http://msdn.microsoft.com/library/92eb22d8-33f3-4c17-b32e-e23acdfbd8f4)|  
|[공용 언어 런타임 관련 동적 관리 뷰 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/common-language-runtime-related-dynamic-management-views-transact-sql.md)|[복제 관련 동적 관리 뷰 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/replication-related-dynamic-management-views-transact-sql.md)|  
|[데이터베이스 미러링 관련된 동적 관리 뷰 &#40; Transact SQL &#41;](http://msdn.microsoft.com/library/04fb21de-1b5e-4a8e-9ca6-1b78ad278db1)|[리소스 관리자 관련 동적 관리 뷰 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/resource-governor-related-dynamic-management-views-transact-sql.md)|  
|[데이터베이스 관련된 동적 관리 뷰 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/database-related-dynamic-management-views-transact-sql.md)|[보안 관련 동적 관리 뷰 및 함수&#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/security-related-dynamic-management-views-and-functions-transact-sql.md)|  
|[실행 관련 동적 관리 뷰 및 함수 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/execution-related-dynamic-management-views-and-functions-transact-sql.md)|[서버 관련 동적 관리 뷰 및 함수&#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql.md)|  
|[확장된 이벤트 동적 관리 뷰](../../relational-databases/system-dynamic-management-views/extended-events-dynamic-management-views.md)|[Service Broker 관련 동적 관리 뷰&#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/service-broker-related-dynamic-management-views-transact-sql.md)|  
|[Filestream 및 FileTable 동적 관리 뷰 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/filestream-and-filetable-dynamic-management-views-transact-sql.md)|[공간 데이터 관련 동적 관리 뷰 및 함수 &#40; Transact SQL &#41;](http://msdn.microsoft.com/library/c542ac38-451f-43a5-bf8c-4edd38bb738e)|  
|[전체 텍스트 검색 및 의미 체계 검색 동적 관리 뷰 및 함수 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/full-text-and-semantic-search-dynamic-management-views-functions.md)|[SQL 데이터 웨어하우스 및 병렬 데이터 웨어하우스 동적 관리 뷰 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)|  
|[지리적 복제 동적 관리 뷰 및 함수 &#40; Azure SQL 데이터베이스 &#41;](../../relational-databases/system-dynamic-management-views/geo-replication-dynamic-management-views-and-functions-azure-sql-database.md)|[SQL Server 운영 체제 관련 동적 관리 뷰 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/sql-server-operating-system-related-dynamic-management-views-transact-sql.md)|  
|[인덱스 관련 동적 관리 뷰 및 함수 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/index-related-dynamic-management-views-and-functions-transact-sql.md)|[스트레치 데이터베이스 동적 관리 뷰 &#40; Transact SQL &#41;](http://msdn.microsoft.com/library/1193efce-a105-49a9-a8b8-26b063485567)|  
|[동적 관리 뷰 및 함수 &#40; 관련 O I Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/i-o-related-dynamic-management-views-and-functions-transact-sql.md)|[트랜잭션 관련 동적 관리 뷰 및 함수&#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/transaction-related-dynamic-management-views-and-functions-transact-sql.md)|  

  
## <a name="see-also"></a>관련 항목:  
 [GRANT 서버 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/grant-server-permissions-transact-sql.md)   
 [GRANT 데이터베이스 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/grant-database-permissions-transact-sql.md)   
 [시스템 뷰 &#40; Transact SQL &#41;](http://msdn.microsoft.com/library/35a6161d-7f43-4e00-bcd3-3091f2015e90)  
  
  