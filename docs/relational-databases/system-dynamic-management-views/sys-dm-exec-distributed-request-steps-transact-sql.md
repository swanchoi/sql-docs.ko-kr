---
title: sys.dm_exec_distributed_request_steps (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SYS.DM_EXEC_DISTRIBUTED_REQUEST_STEPS_TSQL
- DM_EXEC_DISTRIBUTED_REQUEST_STEPS_TSQL
- DM_EXEC_DISTRIBUTED_REQUEST_STEPS
dev_langs: TSQL
helpviewer_keywords:
- PolyBase,views
- PolyBase
- dm_exec_distributed_request_steps
- sys.dm_exec_distributed_request_steps management view
ms.assetid: 1954541d-b716-4e03-8fcc-7022f428e01d
caps.latest.revision: "8"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 4ae648f06b9224cf1545a0984e904c8845e6b88b
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmexecdistributedrequeststeps-transact-sql"></a>sys.dm_exec_distributed_request_steps (Transact SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2016-xxxx-asdw-pdw-md.md)]

  주어진된 PolyBase 요청 또는 쿼리를 작성 하는 모든 단계에 대 한 정보를 보유 합니다. 각 쿼리 단계에 대해 행을 나열합니다.  
  
|열 이름|데이터 형식|Description|범위|  
|-----------------|---------------|-----------------|-----------|  
|execution_id|**int**|execution_id 및 step_index이이 보기에 대 한 키를 구성 합니다. 이 요청과 관련 된 고유 숫자 id입니다.|참조 ID에 [sys.dm_exec_requests &#40; Transact SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql.md).|  
|step_index|**int**|이 단계의 요청 구성 하는 단계 시퀀스의 위치입니다.|0 (n-1)에 n 단계를 포함 한 요청입니다.|  
|operation_type|**nvarchar (128)**|이 단계에서 표시 된 작업의 형식입니다.|'MoveOperation', 'OnOperation', 'RandomIDOperation', 'RemoteOperation', 'ReturnOperation', 'ShuffleMoveOperation', 'TempTablePropertiesOperation', 'DropDiagnosticsNotifyOperation', 'HadoopShuffleOperation', 'HadoopBroadCastOperation' ' HadoopRoundRobinOperation'|  
|distribution_type|**nvarchar (32)**|여기서 단계 실행 중입니다.|' AllComputeNodes ',' AllDistributions', 'ComputeNode', 'Distribution', 'AllNodes', 'SubsetNodes', 'SubsetDistributions',' 지정 되지 않습니다 '.|  
|location_type|**nvarchar (32)**|여기서 단계 실행 중입니다.|'Compute', 'h e a d' 또는 'DMS'. 모든 데이터 이동을 단계 'DMS' 보여 줍니다.|  
|상태|**nvarchar (32)**|이 단계는 상태|'보류 중인', '실행 중', 'Complete', '실패', 'UndoFailed', 'PendingCancel', ' 취소 ', '취소', '중단'|  
|error_id|**nvarchar(36)**|있는 경우이 단계와 관련 된 오류의 고유 id|id를 참조 하십시오. [sys.dm_exec_compute_node_errors&#40; Transact SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-exec-compute-node-errors-transact-sql.md), 오류가 발생 하지 않은 경우 NULL입니다.|  
|start_time|**datetime**|단계 실행 시작 된 시간|더 작은 또는 현재 시간 및 크거나 end_compile_time이이 단계 속해 있는 쿼리 합니다.|  
|end_time|**datetime**|이 단계 실행을 완료, 취소 되었거나 실패 시간입니다.|더 작은 또는 현재 시간 및 크거나 start_time, 실행의 현재 단계에 대 한 NULL로 설정 하거나 큐에 대기 합니다.|  
|total_elapsed_time|**int**|시간 쿼리 단계가 실행 되는, (밀리초)|0 사이의 start_time 및 end_time 간의 차이입니다. 큐에 대기 중인된 단계에 대 한 0입니다.|  
|row_count|**bigint**|변경 되거나이 요청에서 반환 된 행의 총 수|변경 하지 않았거나 데이터, 그렇지 않으면 영향을 받는 행의 수를 반환 하는 단계에 대 한 0입니다. DMS 단계에 대 한-1로 설정 합니다.|  
|command|nvarchar(4000)|이 단계의 명령의 전체 텍스트를 포함합니다.|단계에 대해 유효한 요청 문자열입니다. 4000 자 보다 긴 경우 잘립니다.|  
  
## <a name="see-also"></a>관련 항목:  
 [PolyBase 동적 관리 뷰를 사용한 문제 해결](http://msdn.microsoft.com/library/ce9078b7-a750-4f47-b23e-90b83b783d80)   
 [동적 관리 뷰 및 함수&#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [데이터베이스 관련된 동적 관리 뷰 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/database-related-dynamic-management-views-transact-sql.md)  
  
  