---
title: DROP FULLTEXT INDEX (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DROP_FULLTEXT_INDEX_TSQL
- DROP FULLTEXT INDEX
dev_langs:
- TSQL
helpviewer_keywords:
- deleting full-text indexes
- removing full-text indexes
- full-text indexes [SQL Server], removing
- DROP FULLTEXT INDEX statement
- dropping full-text indexes
ms.assetid: 7443a4ab-1d43-4a22-bbba-a07f620892cb
caps.latest.revision: 33
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: d4636ec49342f1028a09b90c348387520e5e4355
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="drop-fulltext-index-transact-sql"></a>DROP FULLTEXT INDEX(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  지정된 테이블 또는 인덱싱된 뷰에서 전체 텍스트 인덱스를 제거합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
DROP FULLTEXT INDEX ON table_name  
```  
  
## <a name="arguments"></a>인수  
 *table_name*  
 제거할 전체 텍스트 인덱스를 포함하는 테이블 또는 인덱싱된 뷰의 이름입니다.  
  
## <a name="remarks"></a>주의  
 DROP FULLTEXT INDEX 명령을 사용하기 전에 전체 텍스트 인덱스에서 모든 열을 삭제할 필요는 없습니다.  
  
## <a name="permissions"></a>Permissions  
 사용자 테이블 또는 인덱싱된 뷰에 대해 ALTER 권한이 있거나의 멤버는 **sysadmin** 고정 서버 역할 또는 **db_owner** 또는 **db_ddladmin** 고정 데이터베이스 역할입니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 `JobCandidate` 테이블에 있는 전체 텍스트 인덱스를 삭제합니다.  
  
```  
USE AdventureWorks2012;  
GO  
DROP FULLTEXT INDEX ON HumanResources.JobCandidate;  
GO  
```  
  
## <a name="see-also"></a>관련 항목:  
 [sys.fulltext_indexes&#40; Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql.md)   
 [ALTER FULLTEXT INDEX&#40;Transact-SQL&#41;](../../t-sql/statements/alter-fulltext-index-transact-sql.md)   
 [CREATE FULLTEXT INDEX&#40;Transact-SQL&#41;](../../t-sql/statements/create-fulltext-index-transact-sql.md)   
 [전체 텍스트 검색](../../relational-databases/search/full-text-search.md)  
  
  