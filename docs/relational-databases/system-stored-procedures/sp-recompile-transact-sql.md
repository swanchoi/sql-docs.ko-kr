---
title: sp_recompile (TRANSACT-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_recompile_TSQL
- sp_recompile
dev_langs: TSQL
helpviewer_keywords: sp_recompile
ms.assetid: 6192ca87-febd-4075-8199-14b4fa609b8c
caps.latest.revision: "36"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 5cd98a22d086fac88ad523fb2fdded5bc38d9d70
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2017
---
# <a name="sprecompile-transact-sql"></a>sp_recompile(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  저장 프로시저, 트리거 및 사용자 정의 함수가 다음에 실행될 때 다시 컴파일되도록 합니다. 프로시저나 트리거가 다음에 실행될 때 기존 계획을 프로시저 캐시에서 삭제하고 새 계획이 생성되도록 하여 이 작업을 수행합니다. [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] 컬렉션에서는 SP:Recompile 이벤트 대신 SP:CacheInsert 이벤트가 로깅됩니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```tsql  
  
sp_recompile [ @objname = ] 'object'  
```  
  
## <a name="arguments"></a>인수  
 [ @objname=] '*개체*'  
 현재 데이터베이스에 있는 저장 프로시저, 트리거, 테이블, 뷰 또는 사용자 정의 함수의 정규화된 이름 또는 정규화되지 않은 이름입니다. *개체* 은 **nvarchar(776)**, 기본값은 없습니다. 경우 *개체* 는 저장된 프로시저, 트리거 또는 사용자 정의 함수, 저장된 프로시저, 트리거의 이름 또는 함수에서 다음에 실행할 때 다시 컴파일될 됩니다. 경우 *개체* 다음에 실행 되는 테이블 또는 뷰를 참조 하는 사용자 정의 함수는 다시 컴파일할 수 또는 테이블이 나 뷰의 모든 저장된 프로시저, 트리거의 이름입니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 0이 아닌 수(실패)  
  
## <a name="remarks"></a>주의  
 sp_recompile은 현재 데이터베이스에서만 개체를 찾습니다.  
  
 저장 프로시저 또는 트리거 및 사용자 정의 함수에 사용되는 쿼리는 컴파일되는 경우에만 최적화됩니다. 데이터베이스에 통계에 영향을 주는 인덱스 또는 다른 변경 내용이 생기면 데이터베이스, 컴파일된 저장 프로시저, 트리거 및 사용자 정의 함수가 효율성을 잃을 수도 있습니다. 테이블에서 사용되는 저장 프로시저 및 트리거를 다시 컴파일하면 쿼리를 다시 최적화할 수 있습니다.  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]는 자동으로 저장 프로시저, 트리거 및 사용자 정의 함수를 다시 컴파일하는 편이 좋은 경우 그렇게 합니다.  
  
## <a name="permissions"></a>Permissions  
 지정된 개체에 대한 ALTER 권한이 필요합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 `Customer` 테이블에 대해 수행되는 저장 프로시저, 트리거 및 사용자 정의 함수가 다음에 실행될 때 다시 컴파일되도록 합니다.  
  
```  
USE AdventureWorks2012;  
GO  
EXEC sp_recompile N'Sales.Customer';  
GO  
```  
  
## <a name="see-also"></a>관련 항목:  
 [CREATE PROCEDURE&#40;Transact-SQL&#41;](../../t-sql/statements/create-procedure-transact-sql.md)   
 [CREATE TRIGGER&#40;Transact-SQL&#41;](../../t-sql/statements/create-trigger-transact-sql.md)   
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  