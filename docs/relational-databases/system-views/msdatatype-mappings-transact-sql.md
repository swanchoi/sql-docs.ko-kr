---
title: MSdatatype_mappings (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-views
ms.reviewer: 
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to: SQL Server
f1_keywords:
- MSdatatype_mappings
- MSdatatype_mappings_TSQL
dev_langs: TSQL
helpviewer_keywords: MSdatatype_mappings view
ms.assetid: 13cdabb3-6e07-4e8d-ae80-4235022ccc7f
caps.latest.revision: "12"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7ad922397a8c2ed6e0b4faf0f92b84ee8d3408af
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="msdatatypemappings-transact-sql"></a>MSdatatype_mappings(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **MSdatatype_mappings** 뷰를 SQL Server 데이터 형식을 SQL Server 이외 데이터베이스 관리 시스템 (DBMS)에서 사용 되는 데이터 형식에 매핑합니다. 이 테이블에 저장 되는 **msdb** 데이터베이스입니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**dbms_name**|**nvarchar (128)**|DBMS의 이름이입니다. 다음은 가능한 값 및 해당 설명을 보려면입니다.<br /><br /> **MSSQLSERVER**: 대상은 SQL Server 데이터베이스입니다.<br />**ORACLE**: 대상은 Oracle 데이터베이스입니다.<br />**DB2**: 대상은 IBM DB2 데이터베이스입니다.<br />**SYBASE**: 대상은 Sybase 데이터베이스입니다.|  
|**sql_type**|**nvarchar (128)**|SQL Server 데이터 형식이입니다.|  
|**dest_type**|**nvarchar (128)**|SQL Server 이외 데이터 형식의 이름이입니다.|  
|**dest_prec**|**bigint**|SQL Server 이외 데이터 형식의 전체 자릿수가입니다.|  
|**dest_create_params**|**int**|내부적으로만 사용됩니다.|  
|**dest_nullable**|**bit**|SQL Server 이외 데이터 형식이 NULL 값을 지원할지 여부입니다.|  
  
## <a name="see-also"></a>관련 항목:  
 [다른 유형의 데이터베이스 복제](../../relational-databases/replication/non-sql/heterogeneous-database-replication.md)   
 [Oracle 게시자에 대 한 데이터 형식 매핑 지정](../../relational-databases/replication/publish/specify-data-type-mappings-for-an-oracle-publisher.md)   
 [복제 테이블 &#40; Transact SQL &#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [복제 뷰&#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  