---
title: "sp_execute_remote (Azure SQL 데이터베이스) | Microsoft Docs"
ms.custom: 
ms.date: 02/01/2017
ms.prod: 
ms.prod_service: sql-database
ms.reviewer: 
ms.service: sql-database
ms.component: system-stored-procedures
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sp_execute_remote
- sp_execute_remote_TSQL
helpviewer_keywords:
- remote execution
- queries, remote execution
ms.assetid: ca89aa4c-c4c1-4c46-8515-a6754667b3e5
caps.latest.revision: "17"
author: CarlRabeler
ms.author: carlrab
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: f3ce5718a35f8411a5333a200d6ea75f2326c79e
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="spexecuteremote-azure-sql-database"></a>sp_execute_remote (Azure SQL 데이터베이스)
[!INCLUDE[tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md.md)]

  실행 한 [!INCLUDE[tsql](../../includes/tsql-md.md)] 단일 원격 Azure SQL 데이터베이스 또는 수평 분할 구성표의 분할 된 데이터베이스 역할을 수행 하는 데이터베이스 집합에 문의 합니다.  
  
 저장된 프로시저를 탄력적 쿼리 기능의 일부입니다.  참조 [Azure SQL 데이터베이스 탄력적 데이터베이스 쿼리 개요](https://azure.microsoft.com/documentation/articles/sql-database-elastic-query-overview/) 및 [탄력적 데이터베이스 쿼리 (수평 분할) 분할에 대 한](https://azure.microsoft.com/documentation/articles/sql-database-elastic-query-horizontal-partitioning/)합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
sp_execute_remote [ @data_source_name = ] datasourcename  
[ , @stmt = ] statement  
[   
  { , [ @params = ] N'@parameter_name data_type [,...n ]' }   
     { , [ @param1 = ] 'value1' [ ,...n ] }  
]  
```  
  
## <a name="arguments"></a>인수  
 [ @data_source_name =] *datasourcename*  
 문이 실행 되는 외부 데이터 원본을 식별 합니다. 참조 [외부 데이터 원본 만들기 &#40; Transact SQL &#41; ](../../t-sql/statements/create-external-data-source-transact-sql.md). 외부 데이터 원본 "RDBMS" 또는 "SHARD_MAP_MANAGER" 유형일 수 있습니다.  
  
 [ @stmt=] *문*  
 포함 하는 유니코드 문자열을 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문 또는 일괄 처리 합니다. @stmt유니코드 상수 또는 유니코드 변수 여야 합니다. + 연산자로 두 문자열을 연결한 식처럼 더 복잡한 유니코드 식은 사용할 수 없습니다. 문자 상수도 사용할 수 없습니다. 유니코드 상수를 지정 하는 경우 그 앞에 **N**합니다. 예를 들어 유니코드 상수 **N'sp_who '** 유효 하지만 **'sp_who'** 않습니다. 문자열의 크기는 사용 가능한 데이터베이스 서버 메모리의 용량에 따라서만 제한됩니다. 64 비트 서버에서 문자열의 크기는 최대 크기인 2GB로 제한 **nvarchar (max)**합니다.  
  
> [!NOTE]  
>  @stmt예를 들어 변수 이름으로 같은 형식 발생 하는 매개 변수를 포함할 수 있습니다.`N'SELECT * FROM HumanResources.Employee WHERE EmployeeID = @IDParameter'`  
  
 @stmt에 포함된 각 매개 변수에는 @params 매개 변수 정의 목록과 매개 변수 값 목록 모두에 해당되는 항목이 있어야 합니다.  
  
 [ @params=] N'@*p a r a**data_type* [,... *n* ] '  
 @stmt에 포함된 모든 매개 변수의 정의를 포함하는 하나의 문자열입니다. 문자열은 유니코드 상수 또는 유니코드 변수여야 합니다. 각 매개 변수의 정의는 매개 변수 이름과 데이터 형식으로 구성됩니다. *n*추가 매개 변수 정의 나타내는 자리 표시자가입니다. 에 지정 된 모든 매개 변수에 @stmtmust 에 정의 되어야 @params합니다. @stmt의 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문 또는 일괄 처리에 매개 변수가 없으면 @params가 필요 없습니다. 이 매개 변수의 기본값은 NULL입니다.  
  
 [ @param1=] '*value1*'  
 매개 변수 문자열에 정의된 첫 번째 매개 변수의 값입니다. 값은 유니코드 상수 또는 유니코드 변수가 될 수 있습니다. @stmt에 포함된 모든 매개 변수에 대해 제공되는 매개 변수 값이 있어야 합니다. @stmt의 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문 또는 일괄 처리에 매개 변수가 없으면 값이 필요 없습니다.  
  
 *n*  
 추가 매개 변수의 값에 대한 자리 표시자입니다. 값은 상수 또는 변수만 가능합니다. 함수 또는 연산자를 사용하여 작성한 식처럼 더 복잡한 식은 값으로 사용할 수 없습니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 0이 아닌 값(실패)  
  
## <a name="result-sets"></a>결과 집합  
 첫 번째 SQL 문을에서 결과 집합을 반환 합니다.  
  
## <a name="permissions"></a>Permissions  
 `ALTER ANY EXTERNAL DATA SOURCE` 권한이 필요합니다.  
  
## <a name="remarks"></a>주의  
 `sp_execute_remote`위의 구문 섹션에 설명 된 대로 매개 변수를 특정 순서로 입력 되어야 합니다. 매개 변수 순서가 잘못되면 오류 메시지가 나타납니다.  
  
 `sp_execute_remote`동일한 동작 [execute&#40; Transact SQL &#41; ](../../t-sql/language-elements/execute-transact-sql.md) 이름의 범위 및 일괄 처리 합니다. Transact SQL 문 또는 일괄 처리는 sp_execute_remote  *@stmt*  sp_execute_remote 문이 실행 될 때까지 매개 변수 컴파일되지 않습니다.  
  
 `sp_execute_remote`행을 생성 하는 원격 데이터베이스의 이름을 포함 하는 ' $ShardName' 라는 결과 집합에는 추가 열을 추가 합니다.  
  
 `sp_execute_remote`유사 하 게 사용 될 [sp_executesql &#40; Transact SQL &#41; ](../../relational-databases/system-stored-procedures/sp-executesql-transact-sql.md).  
  
## <a name="examples"></a>예  
### <a name="simple-example"></a>간단한 예  
 다음 예제에서는 만들고 원격 데이터베이스에 간단한 SELECT 문을 실행 합니다.  
  
```tsql  
EXEC sp_execute_remote  
    N'MyExtSrc',  
    N'SELECT COUNT(w_id) AS Count_id FROM warehouse'   
```  
  
### <a name="example-with-multiple-parameters"></a>매개 변수가 여러 개이면 예제  
Master 데이터베이스에 대 한 관리자 자격 증명을 지정 하는 사용자 데이터베이스에 데이터베이스 범위 자격 증명을 만듭니다. 데이터베이스 범위 자격 증명을 지정 하 고 master 데이터베이스를 가리키는 외부 데이터 원본을 만듭니다. 다음 예에서는 사용자 데이터베이스에서 실행 한 다음는 `sp_set_firewall_rule` master 데이터베이스의 프로시저입니다. `sp_set_firewall_rule` 3 개의 매개 변수를 요구 하 고 요구 하는 프로시저는 `@name` 매개 변수를 유니코드입니다.

```
EXEC sp_execute_remote @data_source_name  = N'PointToMaster', 
@stmt = N'sp_set_firewall_rule @name, @start_ip_address, @end_ip_address', 
@params = N'@name nvarchar(128), @start_ip_address varchar(50), @end_ip_address varchar(50)',
@name = N'TempFWRule', @start_ip_address = '0.0.0.2', @end_ip_address = '0.0.0.2';
```

## <a name="see-also"></a>참고 항목:

[만들 데이터베이스 범위 자격 증명](../../t-sql/statements/create-database-scoped-credential-transact-sql.md)  
[외부 데이터 원본 (Transact SQL) 만들기](../../t-sql/statements/create-external-data-source-transact-sql.md)  
    