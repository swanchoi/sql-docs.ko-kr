---
title: "외부 테이블 (Transact SQL)을 삭제 | Microsoft Docs"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 02a6a236-0756-4570-abfa-6f677a7df042
caps.latest.revision: 12
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 0e560c5341abd440f641a988751a6ca2875b9bbb
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="drop-external-table-transact-sql"></a>외부 테이블 삭제 (Transact SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-asdw-pdw_md](../../includes/tsql-appliesto-ss2016-xxxx-asdw-pdw-md.md)]

  외부 테이블에서 PolyBase를 제거합니다. 외부 데이터는 삭제 되지 않습니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
DROP EXTERNAL TABLE [ database_name . [schema_name ] . | schema_name . ] table_name   
[;]  
```  
  

## <a name="arguments"></a>인수  
 [ *database_name* 합니다. [*schema_name*]. | *schema_name* 합니다. ] *table_name*  
 제거할 외부 테이블의 한 부분으로 3 구성 이름입니다. 테이블 이름, 스키마 또는 데이터베이스 및 스키마 포함 될 수 있습니다.  
  
## <a name="permissions"></a>Permissions  
  
-   필요한 **ALTER** 테이블이 속해 있는 스키마에 대 한 권한이 있습니다.  
  
## <a name="general-remarks"></a>일반적인 주의 사항  
 외부 테이블을 삭제 모든 테이블 관련 메타 데이터가 제거 됩니다. 외부 데이터는 삭제 되지 않습니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-using-basic-syntax"></a>1. 기본 구문을 사용 하 여  
  
```  
DROP EXTERNAL TABLE SalesPerson;  
DROP EXTERNAL TABLE dbo.SalesPerson;  
DROP EXTERNAL TABLE EasternDivision.dbo.SalesPerson;  
```  
  
### <a name="b-dropping-an-external-table-from-the-current-database"></a>2. 현재 데이터베이스에서 외부 테이블을 삭제 하는 중입니다.  
 다음 예제에서는 제거 된 `ProductVendor1` 테이블, 데이터, 인덱스 및 현재 데이터베이스에서 모든 종속 보기.  
  
```  
DROP EXTERNAL TABLE ProductVendor1;  
```  
  
### <a name="c-dropping-a-table-from-another-database"></a>3. 다른 데이터베이스에서 테이블 삭제  
 다음 예에서는 `EasternDivision` 데이터베이스에서 `SalesPerson` 테이블을 삭제합니다.  
  
```  
DROP EXTERNAL TABLE EasternDivision.dbo.SalesPerson;  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>예: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] 및[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="d-using-basic-syntax"></a>4. 기본 구문을 사용 하 여  
  
```  
DROP EXTERNAL TABLE SalesPerson;  
DROP EXTERNAL TABLE dbo.SalesPerson;  
DROP EXTERNAL TABLE EasternDivision.dbo.SalesPerson;  
```  
  
### <a name="e-dropping-an-external-table-from-the-current-database"></a>5. 현재 데이터베이스에서 외부 테이블을 삭제 하는 중입니다.  
 다음 예제에서는 제거 된 `ProductVendor1` 테이블, 데이터, 인덱스 및 현재 데이터베이스에서 모든 종속 보기.  
  
```  
DROP EXTERNAL TABLE ProductVendor1;  
```  
  
### <a name="f-dropping-a-table-from-another-database"></a>6. 다른 데이터베이스에서 테이블 삭제  
 다음 예에서는 `EasternDivision` 데이터베이스에서 `SalesPerson` 테이블을 삭제합니다.  
  
```  
DROP EXTERNAL TABLE EasternDivision.dbo.SalesPerson;  
```  
  
## <a name="see-also"></a>관련 항목:  
 [CREATE EXTERNAL TABLE&#40;Transact-SQL&#41;](../../t-sql/statements/create-external-table-transact-sql.md)  
  
  

