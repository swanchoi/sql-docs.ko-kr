---
title: sys.dm_exec_compute_nodes (Transact SQL) | Microsoft Docs
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
- DM_EXEC_COMPUTE_NODES_TSQL
- DM_EXEC_COMPUTE_NODES
- SYS.DM_EXEC_COMPUTE_NODES_TSQL
dev_langs: TSQL
helpviewer_keywords:
- sys.dm_exec_compute_nodes management view
- PolyBase, views
- PolyBase management views
- dm_exec_compute_nodes management view
ms.assetid: 0de4b7a4-401f-4e2d-9ab0-c54587e05154
caps.latest.revision: "8"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 4affdf5cdcab66ffacab6bb40596855938ad1b98
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmexeccomputenodes-transact-sql"></a>sys.dm_exec_compute_nodes (Transact SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2016-xxxx-asdw-pdw-md.md)]

  PolyBase 데이터 관리에 사용 되는 노드에 대 한 정보를 보유 합니다. 노드당 한 행을 나열합니다.  
  
 이 DMV를 사용 하 여 자신의 역할, 이름 및 IP 주소를 사용 하 여 스케일 아웃 클러스터의 모든 노드 목록을 볼 수 있습니다.  
  
|열 이름|데이터 형식|Description|범위|  
|-----------------|---------------|-----------------|-----------|  
|compute_node_id|**int**|노드와 연결 된 고유 숫자 id입니다. 이 보기에 대 한 키입니다.|형식에 관계 없이 스케일 아웃 클러스터 전체에서 고유 합니다.|  
|형식|**nvarchar (32)**|노드의 유형입니다.|' COMPUTE', '헤드'|  
|name|**nvarchar (32)**|노드의 논리적 이름입니다.|적절 한 길이의 문자열입니다.|  
|address|**nvarchar (32)**|이 노드의 P 주소입니다.|IP 주소 범위|  
  
## <a name="see-also"></a>관련 항목:  
 [PolyBase 동적 관리 뷰를 사용한 문제 해결](http://msdn.microsoft.com/library/ce9078b7-a750-4f47-b23e-90b83b783d80)   
 [동적 관리 뷰 및 함수&#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [데이터베이스 관련된 동적 관리 뷰 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/database-related-dynamic-management-views-transact-sql.md)  
  
  