---
title: sys.dm_exec_query_parallel_workers (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 05/24/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- dm_exec_query_parallel_workers_TSQL
- dm_exec_query_parallel_workers
- sys.dm_exec_query_parallel_workers_TSQL
- sys.dm_exec_query_parallel_workers
dev_langs: TSQL
helpviewer_keywords: sys.dm_exec_query_parallel_workers dynamic management view
ms.assetid: 1d72cef1-22d8-4ae0-91db-6694fe918c9f
caps.latest.revision: "1"
author: pelopes
ms.author: pelopes
manager: ajayj
ms.workload: Inactive
ms.openlocfilehash: dd0653ae9177673026eb07bbc14f2b6769315e00
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmexecqueryparallelworkers-transact-sql"></a>sys.dm_exec_query_parallel_workers (Transact SQL)
[!INCLUDE[tsql-appliesto-ss2016-all-md](../../includes/tsql-appliesto-ss2016-all-md.md)]

  노드당 반환 작업자 가용성 정보입니다.  
  
|이름|데이터 형식|Description|  
|----------|---------------|-----------------|  
|**node_id**|**int**|NUMA 노드 id입니다.|  
|**scheduler_count**|**int**|이 노드의 스케줄러 수입니다.|  
|**max_worker_count**|**int**|병렬 쿼리에 대 한 작업자의 최대 수입니다.|  
|**reserved_worker_count**|**int**|모든 요청에서 사용 되는 주 작업자 수 및 병렬 쿼리에 예약 작업자의 수입니다.| 
|**free_worker_count**|**int**|작업에 사용할 수 있는 작업자 수입니다.<br /><br />**참고:** 들어오는 모든 요청 소비 1 명 이상 작업자에 사용 가능한 작업자 수에서 뺍니다.  있기 무료 작업자 수 과도 하 게 로드 하는 서버에 음수를 수 있습니다.| 
|**used_worker_count**|**int**|병렬 쿼리에 사용 된 작업자 수입니다.|  
  
## <a name="permissions"></a>Permissions  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 서버에 대 한 VIEW SERVER STATE 권한이 필요 합니다.  
  
 [!INCLUDE[ssSDS](../../includes/sssds-md.md)] 프리미엄 계층 데이터베이스에서 VIEW DATABASE STATE 권한이 필요 합니다. [!INCLUDE[ssSDS](../../includes/sssds-md.md)] 표준 및 기본 계층 필요는 [!INCLUDE[ssSDS](../../includes/sssds-md.md)] 관리자 계정.  
  
## <a name="examples"></a>예  
  
### <a name="a-viewing-current-parallel-worker-availability"></a>1. 현재 병렬 작업자 가용성 보기  

``` tsql 
SELECT * FROM sys.dm_exec_query_parallel_workers;  
```  
  
## <a name="see-also"></a>관련 항목:  
 [동적 관리 뷰 및 함수&#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [실행 관련 동적 관리 뷰 및 함수 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/execution-related-dynamic-management-views-and-functions-transact-sql.md)   
 [sys.dm_os_workers &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-os-workers-transact-sql.md)