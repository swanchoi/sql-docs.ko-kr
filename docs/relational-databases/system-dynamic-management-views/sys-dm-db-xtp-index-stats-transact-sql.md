---
title: sys.dm_db_xtp_index_stats (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 08/29/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.dm_db_xtp_index_stats
- dm_db_xtp_index_stats
- sys.dm_db_xtp_index_stats_TSQL
- dm_db_xtp_index_stats_TSQL
dev_langs: TSQL
helpviewer_keywords: sys.dm_db_xtp_index_stats dynamic management view
ms.assetid: 8d0a50b8-2015-4576-930f-e3307dfc888e
caps.latest.revision: "25"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 8803e51eab52a10e67e90dc6ddb06cfc7d737434
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmdbxtpindexstats-transact-sql"></a>sys.dm_db_xtp_index_stats(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2014-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2014-asdb-xxxx-xxx-md.md)]

  데이터베이스를 마지막으로 다시 시작한 후 수집된 통계가 포함됩니다.  
  
 자세한 내용은 참조 [메모리 내 oltp&#40; 메모리 내 최적화 &#41;](../../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md) 및 [메모리 최적화 된 테이블에 사용 하 여 인덱스에 대 한 지침이](http://msdn.microsoft.com/library/16ef63a4-367a-46ac-917d-9eebc81ab29b)합니다.  

  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|object_id|**bigint**|이 인덱스가 속한 개체의 ID입니다.|  
|xtp_object_id|**bigint**|개체의 현재 버전에 해당 하는 내부 ID입니다.<br /><br /> 참고: 적용할 [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)]합니다.|  
|index_id|**bigint**|인덱스의 ID입니다. index_id는 프로젝트 내에서만 고유합니다.|  
|scans_started|**bigint**|수행된 메모리 내 OLTP 인덱스 검사 수입니다. 모든 SELECT, INSERT, UPDATE 또는 DELETE에는 인덱스 검사가 필요합니다.|  
|scans_retries|**bigint**|다시 시도해야 하는 인덱스 검사 수입니다.|  
|rows_returned|**bigint**|테이블을 만든 후 또는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 시작 후 반환된 누적 행 수입니다.|  
|rows_touched|**bigint**|테이블을 만든 후 또는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 시작 후 액세스된 누적 행 수입니다.|  
|rows_expiring|**bigint**|내부적으로만 사용됩니다.|  
|rows_expired|**bigint**|내부적으로만 사용됩니다.|  
|rows_expired_removed|**bigint**|내부적으로만 사용됩니다.|  
|phantom_scans_started|**bigint**|내부적으로만 사용됩니다.|  
|phatom_scans_retries|**bigint**|내부적으로만 사용됩니다.|  
|phantom_rows_touched|**bigint**|내부적으로만 사용됩니다.|  
|phantom_expiring_rows_encountered|**bigint**|내부적으로만 사용됩니다.|  
|phantom_expired_rows_encountered|**bigint**|내부적으로만 사용됩니다.|  
|phantom_expired_removed_rows_encountered|**bigint**|내부적으로만 사용됩니다.|  
|phantom_expired_rows_removed|**bigint**|내부적으로만 사용됩니다.|  
|object_address|**varbinary (8)**|내부적으로만 사용됩니다.|  
  
## <a name="permissions"></a>Permissions  
 현재 데이터베이스에 대해 VIEW DATABASE STATE 권한이 필요합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [메모리 액세스에 최적화 된 테이블 동적 관리 뷰 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/memory-optimized-table-dynamic-management-views-transact-sql.md)  
  
  