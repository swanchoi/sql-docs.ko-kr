---
title: "집계 (Transact SQL)를 만드는 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CREATE_AGGREGATE_TSQL
- CREATE AGGREGATE
- AGGREGATE_TSQL
- AGGREGATE
dev_langs:
- TSQL
helpviewer_keywords:
- CREATE AGGREGATE statement
- aggregate functions [SQL Server], user-defined
- user-defined functions [CLR integration]
ms.assetid: 62eebc19-9f15-4245-94fa-b3fcd64a9d42
caps.latest.revision: 50
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: ad5cf36e97bf3903cc9d42ec5179de6375624f95
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="create-aggregate-transact-sql"></a>CREATE AGGREGATE(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  구현이 [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]의 어셈블리 클래스에 정의된 사용자 정의 집계 함수를 만듭니다. [!INCLUDE[ssDE](../../includes/ssde-md.md)]에서 집계 함수를 해당 구현에 바인딩하려면 CREATE ASSEMBLY 문을 사용하여 먼저 해당 구현이 포함된 [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 어셈블리를 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]의 인스턴스에 업로드해야 합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
CREATE AGGREGATE [ schema_name . ] aggregate_name  
        (@param_name <input_sqltype>   
        [ ,...n ] )  
RETURNS <return_sqltype>  
EXTERNAL NAME assembly_name [ .class_name ]  
  
<input_sqltype> ::=  
        system_scalar_type | { [ udt_schema_name. ] udt_type_name }  
  
<return_sqltype> ::=  
        system_scalar_type | { [ udt_schema_name. ] udt_type_name }  
  
```  
  
## <a name="arguments"></a>인수  
 *schema_name*  
 사용자 정의 집계 함수가 속한 스키마의 이름입니다.  
  
 *aggregate_name*  
 만들려는 집계 함수의 이름입니다.  
  
 **@***param_name*  
 사용자 정의 집계에 포함된 하나 이상의 매개 변수입니다. 매개 변수의 값은 집계 함수를 실행할 때 사용자가 제공해야 합니다. "At" 기호를 사용 하 여 매개 변수 이름 지정 (**@**) 첫 번째 문자로 합니다. 매개 변수 이름에 대 한 규칙을 준수 해야 [식별자](../../relational-databases/databases/database-identifiers.md)합니다. 매개 변수는 함수에서 로컬로 사용됩니다.  
  
 *system_scalar_type*  
 입력 매개 변수의 값 또는 반환 값을 보유하는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 시스템 스칼라 데이터 형식 중 하나입니다. 모든 스칼라 데이터 형식을 사용할 수는 매개 변수로 사용자 정의 집계에 대 한 제외 하 고 **텍스트**, **ntext**, 및 **이미지**합니다. 와 같은 비스칼라 형식은 **커서** 및 **테이블**를 지정할 수 없습니다.  
  
 *udt_schema_name*  
 CLR 사용자 정의 형식이 속한 스키마의 이름입니다. 지정 하지 않으면는 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 참조 *udt_type_name* 다음과 같은 순서로:  
  
-   네이티브 SQL 유형 네임스페이스  
  
-   현재 데이터베이스에 있는 현재 사용자의 기본 스키마  
  
-   현재 데이터베이스의 **dbo** 스키마  
  
 *udt_type_name*  
 현재 데이터베이스에 생성되어 있는 CLR 사용자 정의 형식의 이름입니다. 경우 *udt_schema_name* 를 지정 하지 않으면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 는 형식이 현재 사용자의 스키마에 속하는 것으로 가정 합니다.  
  
 *assembly_name* [ **.** *class_name* ]  
 사용자 정의 집계 함수와 바인딩할 어셈블리를 지정하고 필요에 따라 어셈블리가 속한 스키마의 이름과 사용자 정의 집계를 구현하는 어셈블리의 클래스 이름을 지정합니다. 어셈블리는 CREATE ASSEMBLY 문을 사용하여 데이터베이스에 이미 생성되어 있어야 합니다. *class_name* 은 유효한 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 식별자와 일치 하는 어셈블리에 있는 클래스의 이름입니다. *class_name* 는 클래스를 작성 하는 데 사용 하 여 프로그래밍 언어 C#과 같은 네임 스페이스를 사용 하는 경우 네임 스페이스로 한정 이름일 수 있습니다. 경우 *class_name* 를 지정 하지 않으면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 같은 것으로 간주 *aggregate_name*합니다.  
  
## <a name="remarks"></a>주의  
 기본적으로 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]의 CLR 코드 실행 기능은 해제됩니다. 인스턴스에서 이러한 모듈의 코드가 실행 되지 것입니다 만들기, 수정 및 관리 코드 모듈을 참조 하는 데이터베이스 개체를 삭제 하지만 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 경우가 아니면는 [clr enabled 옵션](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) 사용 하 여 [sp_ 구성](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)합니다.  
  
 참조 되는 어셈블리의 클래스 *assembly_name* 해당 메서드를 인스턴스에서 사용자 정의 집계 함수를 구현 하기 위한 모든 요구 사항을 충족 해야 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]합니다. 자세한 내용은 참조 [clr 사용자 정의 집계](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md)합니다.  
  
## <a name="permissions"></a>Permissions  
 EXTERNAL NAME 절에 지정된 어셈블리에 대한 REFERENCES 권한과 CREATE AGGREGATE 권한이 필요합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 StringUtilities.csproj 예제 응용 프로그램이 컴파일된다고 가정합니다. 자세한 내용은 참조 [문자열 유틸리티 함수 예제](http://msdn.microsoft.com/library/9623013f-15f1-4614-8dac-1155e57c880c)합니다.  
  
 이 예에서는 집계 `Concatenate`를 만듭니다. 집계를 만들기 전에 `StringUtilities.dll` 어셈블리가 로컬 데이터베이스에 등록됩니다.  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @SamplesPath nvarchar(1024)  
-- You may have to modify the value of the this variable if you have  
--installed the sample some location other than the default location.  
  
SELECT @SamplesPath = REPLACE(physical_name, 'Microsoft SQL Server\MSSQL13.MSSQLSERVER\MSSQL\DATA\master.mdf', 'Microsoft SQL Server\130\Samples\Engine\Programmability\CLR\')   
     FROM master.sys.database_files   
     WHERE name = 'master';  
  
CREATE ASSEMBLY StringUtilities FROM @SamplesPath + 'StringUtilities\CS\StringUtilities\bin\debug\StringUtilities.dll'  
WITH PERMISSION_SET=SAFE;  
GO  
  
CREATE AGGREGATE Concatenate(@input nvarchar(4000))  
RETURNS nvarchar(4000)  
EXTERNAL NAME [StringUtilities].[Microsoft.Samples.SqlServer.Concatenate];  
GO  
```  
  
## <a name="see-also"></a>관련 항목:  
 [집계 &#40; 삭제 Transact SQL &#41;](../../t-sql/statements/drop-aggregate-transact-sql.md)  
  
  