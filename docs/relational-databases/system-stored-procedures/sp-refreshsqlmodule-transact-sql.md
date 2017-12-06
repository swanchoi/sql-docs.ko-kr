---
title: sp_refreshsqlmodule (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
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
- sp_refreshsqlmodule_TSQL
- sp_refreshsqlmodule
dev_langs: TSQL
helpviewer_keywords:
- metadata [SQL Server], stored procedures
- metadata [SQL Server], triggers
- metadata [SQL Server], views
- triggers [SQL Server], refreshing metadata
- views [SQL Server], refreshing metadata
- sp_refreshsqlmodule
- metadata [SQL Server], functions
- stored procedures [SQL Server], refreshing metadata
- user-defined functions [SQL Server], refreshing metadata
ms.assetid: f0022a05-50dd-4620-961d-361b1681d375
caps.latest.revision: "21"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: a95c2e905efa377edb83fd82a104758853b18271
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2017
---
# <a name="sprefreshsqlmodule-transact-sql"></a>sp_refreshsqlmodule(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  현재 데이터베이스에서 지정된 비스키마 바운드 저장 프로시저, 사용자 정의 함수, 뷰, DML 트리거, 데이터베이스 수준 DDL 트리거 또는 서버 수준 DDL 트리거에 대한 메타데이터를 업데이트합니다. 기본 개체가 변경되면 매개 변수의 데이터 형식과 같은 이러한 개체의 영구 메타데이터가 최신 상태를 유지하지 못할 수 있습니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sys.sp_refreshsqlmodule [ @name = ] 'module_name'   
    [ , [ @namespace = ] ' <class> ' ]  
  
<class> ::=  
{  
  | DATABASE_DDL_TRIGGER  
  | SERVER_DDL_TRIGGER  
}  
  
```  
  
## <a name="arguments"></a>인수  
 [  **@name=** ] **'***모듈***'**  
 저장 프로시저, 사용자 정의 함수, 뷰, DML 트리거, 데이터베이스 수준 DDL 트리거 또는 서버 수준 DDL 트리거의 이름입니다. *모듈* 공용 언어 런타임 (CLR) 저장 프로시저 또는 CLR 함수가 될 수 없습니다. *모듈* 스키마 바인딩할 수 없습니다. *모듈* 은 **nvarchar**, 기본값은 없습니다. *모듈* 다중 부분 식별자가 될 수 있지만 현재 데이터베이스에 개체를 참조할 수 있습니다.  
  
 [ **,** @**네임 스페이스** =] **'** \<클래스 > **'**  
 지정된 모듈의 클래스입니다. 때 *모듈* 이 DDL 트리거인 경우 \<클래스 >가 필요 합니다. *\<클래스 >* 은 **nvarchar**(20). 잘못된 입력:  
  
|||  
|-|-|  
|DATABASE_DDL_TRIGGER||  
|SERVER_DDL_TRIGGER|**적용 대상**: [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] 부터 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]까지|  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 0이 아닌 수(실패)  
  
## <a name="remarks"></a>주의  
 **sp_refreshsqlmodule** 는 개체에는 모듈의 정의 영향을 주는 변경 내용이 있을 때만 적용 됩니다. 그렇지 않으면 모듈을 쿼리하거나 호출할 때 예기치 않은 결과가 발생할 수 있습니다. 뷰를 새로 고치려면 하나를 사용 **sp_refreshsqlmodule** 또는 **sp_refreshview** 동일한 결과입니다.  
  
 **sp_refreshsqlmodule** 모든 사용 권한, 확장된 속성 또는 개체와 연결 된 SET 옵션에는 영향을 주지 않습니다.  
  
 서버 수준 DDL 트리거를 새로 고치려면 아무 데이터베이스 컨텍스트에서 이 저장 프로시저를 실행하세요.  
  
> [!NOTE]  
>  실행 하면 개체와 연결 되어 있는 모든 서명이 삭제 됩니다 **sp_refreshsqlmodule**합니다.  
  
## <a name="permissions"></a>Permissions  
 모듈에 대한 ALTER 권한 및 개체가 참조하는 CLR 사용자 정의 형식과 XML 스키마 컬렉션에 대한 REFERENCES 권한이 필요합니다. 지정된 모듈이 데이터베이스 수준 DDL 트리거일 경우 현재 데이터베이스에 ALTER ANY DATABASE DDL TRIGGER 권한이 필요합니다. 지정된 모듈이 서버 수준 DDL 트리거일 경우 CONTROL SERVER 권한이 필요합니다.  
  
 또한 EXECUTE AS 절로 정의되는 모듈의 경우 지정된 보안 주체에 대해 IMPERSONATE 권한이 필요합니다. 일반적으로 모듈이 EXECUTE AS USER로 정의되었으며 보안 주체의 사용자 이름이 모듈이 만들어진 때의 사용자와 다른 사용자로 확인되지 않는 이상 개체를 새로 고쳐도 EXECUTE AS 보안 주체가 변경되지 않습니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-refreshing-a-user-defined-function"></a>1. 사용자 정의 함수 새로 고침  
 다음 예에서는 사용자 정의 함수를 새로 고칩니다. 이 예에서는 별칭 데이터 형식인 `mytype`과 `to_upper`을 사용하는 사용자 정의 함수 `mytype`를 만듭니다. 그런 다음 `mytype`의 이름을 `myoldtype`으로 바꾸고 다른 정의가 있는 새 `mytype`을 만듭니다. `dbo.to_upper` 함수를 새로 고치면 이전 항목 대신 새로 구현된 `mytype`이 참조됩니다.  
  
```  
-- Create an alias type.  
USE AdventureWorks2012;  
GO  
IF EXISTS (SELECT 'mytype' FROM sys.types WHERE name = 'mytype')  
DROP TYPE mytype;  
GO  
  
CREATE TYPE mytype FROM nvarchar(5);  
GO  
  
IF OBJECT_ID ('dbo.to_upper', 'FN') IS NOT NULL  
DROP FUNCTION dbo.to_upper;  
GO  
  
CREATE FUNCTION dbo.to_upper (@a mytype)  
RETURNS mytype  
WITH ENCRYPTION  
AS  
BEGIN  
RETURN upper(@a)  
END;  
GO  
  
SELECT dbo.to_upper('abcde');  
GO  
  
-- Increase the length of the alias type.  
sp_rename 'mytype', 'myoldtype', 'userdatatype';  
GO  
  
CREATE TYPE mytype FROM nvarchar(10);  
GO  
  
-- The function parameter still uses the old type.  
SELECT name, type_name(user_type_id)   
FROM sys.parameters   
WHERE object_id = OBJECT_ID('dbo.to_upper');  
GO  
  
SELECT dbo.to_upper('abcdefgh'); -- Fails because of truncation  
GO  
  
-- Refresh the function to bind to the renamed type.  
EXEC sys.sp_refreshsqlmodule 'dbo.to_upper';  
  
-- The function parameters are now bound to the correct type and the statement works correctly.  
SELECT name, type_name(user_type_id) FROM sys.parameters  
WHERE object_id = OBJECT_ID('dbo.to_upper');  
GO  
  
SELECT dbo.to_upper('abcdefgh');  
GO  
```  
  
### <a name="b-refreshing-a-database-level-ddl-trigger"></a>2. 데이터베이스 수준 DDL 트리거 새로 고침  
 다음 예에서는 데이터베이스 수준 DDL 트리거를 새로 고칩니다.  
  
```  
USE AdventureWorks2012;  
GO  
EXEC sys.sp_refreshsqlmodule @name = 'ddlDatabaseTriggerLog' , @namespace = 'DATABASE_DDL_TRIGGER';  
GO  
```  
  
### <a name="c-refreshing-a-server-level-ddl-trigger"></a>3. 서버 수준 DDL 트리거 새로 고침  
 다음 예에서는 서버 수준 DDL 트리거를 새로 고칩니다.  
  
||  
|-|  
|**적용 대상**: [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] 부터 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]까지|  
  
```  
USE master;  
GO  
EXEC sys.sp_refreshsqlmodule @name = 'ddl_trig_database' , @namespace = 'SERVER_DDL_TRIGGER';  
GO  
  
```  
  
## <a name="see-also"></a>관련 항목:  
 [sp_refreshview &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-refreshview-transact-sql.md)   
 [데이터베이스 엔진 저장 프로시저 &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/database-engine-stored-procedures-transact-sql.md)  
  
  