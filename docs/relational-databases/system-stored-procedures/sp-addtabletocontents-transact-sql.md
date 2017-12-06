---
title: sp_addtabletocontents (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to: SQL Server
f1_keywords:
- sp_addtabletocontents_TSQL
- sp_addtabletocontents
helpviewer_keywords: sp_addtabletocontents
ms.assetid: 2ea27001-74f4-463e-bf1b-b6b5a86b9219
caps.latest.revision: "23"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a16b89e4d2567a24b8c61fdb5ce6830e2205f824
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="spaddtabletocontents-transact-sql"></a>sp_addtabletocontents(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  원본 테이블을 검사하여 현재 추적 테이블에 없는 행이 있을 경우 병합 추적 테이블에 이 행에 대한 참조를 추가합니다. 이 옵션을 사용 하면 대량 로드 데이터를 사용 하 여 많은 양의 **bcp**을 병합 추적 트리거를 실행 하지 않는 합니다. 이 저장 프로시저는 게시 데이터베이스의 게시자에서 실행됩니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_addtabletocontents [ @table_name = ] 'table_name'  
    [ , [ @owner_name = ] 'owner_name' ]  
    [ , [ @filter_clause = ] 'filter_clause' ]  
```  
  
## <a name="arguments"></a>인수  
 [  **@table_name=**] **'***table_name***'**  
 테이블의 이름입니다. *table_name* 은 **sysname**, 기본값은 없습니다.  
  
 [  **@owner_name=**] **'***owner_name***'**  
 테이블 소유자의 이름입니다. *owner_name* 은 **sysname**, 기본값은 NULL입니다.  
  
 [  **@filter_clause=** ] **'***filter_clause***'**  
 새로 로드된 데이터의 어떤 행을 병합 추적 테이블에 추가해야 할지 제어하는 필터 절을 지정합니다. *filter_clause* 은 **nvarchar (4000)**, 기본값은 NULL입니다. 경우 *filter_clause* 은 **null**, 모든 대량 로드 된 행이 추가 됩니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="remarks"></a>주의  
 **sp_addtabletocontents** 병합 복제에만 사용 됩니다.  
  
 행은 *table_name* 으로 참조 되는 해당 **rowguidcol** 참조는 병합 추적 테이블에 추가 됩니다. **sp_addtabletocontents** 대량으로 병합 복제를 사용 하 여 게시 된 테이블에 데이터를 복사한 후 사용 해야 합니다. 저장 프로시저는 복사된 행의 추적을 시작하며 새 행이 다음 동기화에 포함될 것인지 확인합니다.  
  
## <a name="permissions"></a>Permissions  
 구성원만는 **sysadmin** 고정된 서버 역할 또는 **db_owner** 고정된 데이터베이스 역할을 실행할 수 있는 **sp_addtabletocontents**합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  