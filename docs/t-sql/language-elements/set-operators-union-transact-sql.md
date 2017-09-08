---
title: UNION (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 08/07/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- UNION
- UNION_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- UNION queries
- combining query results
- UNION operator [SQL Server]
ms.assetid: 607c296f-8a6a-49bc-975a-b8d0c0914df7
caps.latest.revision: 34
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 29f86913fd2fb6bf04c4c00d95427d34128c8fee
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="set-operators---union-transact-sql"></a>집합 연산자-UNION (TRANSACT-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  둘 이상의 쿼리 결과를 각 해당 쿼리에 속하는 모든 행이 포함된 하나의 결과 집합으로 결합합니다. UNION 연산은 두 테이블의 열을 결합하는 조인을 사용하는 것과는 다릅니다.  
  
 다음은 UNION을 사용하여 두 쿼리의 결과 집합을 결합하기 위한 기본 규칙입니다.  
  
-   열의 개수와 순서가 모든 쿼리에서 동일해야 합니다.  
  
-   데이터 형식이 호환되어야 합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
    { <query_specification> | ( <query_expression> ) }   
  UNION [ ALL ]   
  <query_specification | ( <query_expression> )   
 [ UNION [ ALL ] <query_specification> | ( <query_expression> )   
    [ ...n ] ]   
```  
  
## <a name="arguments"></a>인수  
\<query_specification > | ( \<query_expression >)는 쿼리 사양 또는 다른 쿼리 사양 또는 쿼리 식에서 데이터와 결합할 데이터를 반환 하는 쿼리 식입니다. UNION 연산의 일부인 열의 정의는 같을 필요는 없지만 암시적 변환을 통해 호환되어야 합니다. 데이터 형식이 다를 때 결과 데이터 형식에 대 한 규칙에 따라 결정 됩니다 [데이터 형식 우선 순위](../../t-sql/data-types/data-type-precedence-transact-sql.md)합니다. 형식은 동일하지만 전체 자릿수, 소수 자릿수 또는 길이가 다르면 식 결합에 대한 동일한 규칙에 따라 결과가 결정됩니다. 자세한 내용은 [전체 자릿수, 소수 자릿수 및 길이&#40;Transact-SQL&#41;](../../t-sql/data-types/precision-scale-and-length-transact-sql.md)를 참조하세요.  
  
 열은 **xml** 데이터 형식은 동일 해야 합니다. 모든 열은 XML 스키마로 형식화되거나 형식화되지 않아야 합니다. 형식화되는 경우 모든 열은 동일한 XML 스키마 컬렉션으로 형식화되어야 합니다.  
  
 UNION  
 여러 결과 집합을 결합하여 하나의 결과 집합으로 반환하도록 지정합니다.  
  
 ALL  
 모든 행을 결과로 통합합니다. 여기에는 중복 행이 포함됩니다. 지정하지 않을 경우 중복 행은 제거됩니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-using-a-simple-union"></a>1. 단순 UNION 사용  
 다음 예에서는 결과 집합에 `ProductModelID` 및 `Name` 테이블의 `ProductModel` 및 `Gloves` 열의 내용이 포함됩니다.  
  
```  
-- Uses AdventureWorks  
  
IF OBJECT_ID ('dbo.Gloves', 'U') IS NOT NULL  
DROP TABLE dbo.Gloves;  
GO  
-- Create Gloves table.  
SELECT ProductModelID, Name  
INTO dbo.Gloves  
FROM Production.ProductModel  
WHERE ProductModelID IN (3, 4);  
GO  
  
-- Here is the simple union.  
-- Uses AdventureWorks  
  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID NOT IN (3, 4)  
UNION  
SELECT ProductModelID, Name  
FROM dbo.Gloves  
ORDER BY Name;  
GO  
```  
  
### <a name="b-using-select-into-with-union"></a>2. UNION과 함께 SELECT INTO 사용  
 다음 예에서 두 번째 `INTO` 문의 `SELECT` 절은 `ProductResults` 및 `ProductModel` 테이블의 지정된 열에 대해 UNION 연산을 수행한 마지막 결과 집합을 `Gloves` 테이블에 포함시키도록 지정합니다. `Gloves` 테이블은 첫 번째 `SELECT` 문에서 생성됩니다.  
  
```  
-- Uses AdventureWorks  
  
IF OBJECT_ID ('dbo.ProductResults', 'U') IS NOT NULL  
DROP TABLE dbo.ProductResults;  
GO  
IF OBJECT_ID ('dbo.Gloves', 'U') IS NOT NULL  
DROP TABLE dbo.Gloves;  
GO  
-- Create Gloves table.  
SELECT ProductModelID, Name  
INTO dbo.Gloves  
FROM Production.ProductModel  
WHERE ProductModelID IN (3, 4);  
GO  
  
-- Uses AdventureWorks  
  
SELECT ProductModelID, Name  
INTO dbo.ProductResults  
FROM Production.ProductModel  
WHERE ProductModelID NOT IN (3, 4)  
UNION  
SELECT ProductModelID, Name  
FROM dbo.Gloves;  
GO  
  
SELECT ProductModelID, Name   
FROM dbo.ProductResults;  
  
```  
  
### <a name="c-using-union-of-two-select-statements-with-order-by"></a>3. 두 SELECT 문에서 ORDER BY와 함께 UNION 사용  
 UNION 절과 함께 사용되는 특정 매개 변수의 순서는 중요합니다. 다음 예에서는 출력 시 이름이 바뀌는 열이 있는 두 `UNION` 문에서 `SELECT`을 잘못 사용한 경우와 올바르게 사용한 경우를 보여 줍니다.  
  
```  
-- Uses AdventureWorks  
  
IF OBJECT_ID ('dbo.Gloves', 'U') IS NOT NULL  
DROP TABLE dbo.Gloves;  
GO  
-- Create Gloves table.  
SELECT ProductModelID, Name  
INTO dbo.Gloves  
FROM Production.ProductModel  
WHERE ProductModelID IN (3, 4);  
GO  
  
/* INCORRECT */  
-- Uses AdventureWorks  
  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID NOT IN (3, 4)  
ORDER BY Name  
UNION  
SELECT ProductModelID, Name  
FROM dbo.Gloves;  
GO  
  
/* CORRECT */  
-- Uses AdventureWorks  
  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID NOT IN (3, 4)  
UNION  
SELECT ProductModelID, Name  
FROM dbo.Gloves  
ORDER BY Name;  
GO  
  
```  
  
### <a name="d-using-union-of-three-select-statements-to-show-the-effects-of-all-and-parentheses"></a>4. 세 개의 SELECT 문에서 UNION을 사용하여 ALL 및 괄호의 효과 확인  
 다음 예에서는 `UNION`을 사용하여 동일한 5개의 데이터 행이 있는 세 테이블의 결과를 결합합니다. 첫 번째 예에서는 `UNION ALL`을 사용하여 중복 레코드를 보여 주고 15개 행을 모두 반환합니다. 두 번째 예에서는 `UNION` 없이 `ALL`을 사용하여 세 `SELECT` 문의 결합된 결과에서 중복 행을 제거하고 5개 행만 반환합니다.  
  
 세 번째 예에서는 첫 번째 `ALL`에서 `UNION`을 사용하고 `UNION`을 사용하지 않는 두 번째 `ALL`은 괄호로 묶습니다. 두 번째 `UNION`은 괄호로 묶었기 때문에 먼저 처리되고 `ALL` 옵션을 사용하지 않아 중복 행이 제거되기 때문에 5개 행을 반환합니다. 이러한 5개 행은 `SELECT` 키워드를 사용하여 첫 번째 `UNION ALL` 결과와 결합됩니다. 이 때 5개 행으로 된 두 집합 간의 중복 행은 제거되지 않습니다. 따라서 마지막 결과에는 10개의 행이 포함됩니다.  
  
```  
-- Uses AdventureWorks  
  
IF OBJECT_ID ('dbo.EmployeeOne', 'U') IS NOT NULL  
DROP TABLE dbo.EmployeeOne;  
GO  
IF OBJECT_ID ('dbo.EmployeeTwo', 'U') IS NOT NULL  
DROP TABLE dbo.EmployeeTwo;  
GO  
IF OBJECT_ID ('dbo.EmployeeThree', 'U') IS NOT NULL  
DROP TABLE dbo.EmployeeThree;  
GO  
  
SELECT pp.LastName, pp.FirstName, e.JobTitle   
INTO dbo.EmployeeOne  
FROM Person.Person AS pp JOIN HumanResources.Employee AS e  
ON e.BusinessEntityID = pp.BusinessEntityID  
WHERE LastName = 'Johnson';  
GO  
SELECT pp.LastName, pp.FirstName, e.JobTitle   
INTO dbo.EmployeeTwo  
FROM Person.Person AS pp JOIN HumanResources.Employee AS e  
ON e.BusinessEntityID = pp.BusinessEntityID  
WHERE LastName = 'Johnson';  
GO  
SELECT pp.LastName, pp.FirstName, e.JobTitle   
INTO dbo.EmployeeThree  
FROM Person.Person AS pp JOIN HumanResources.Employee AS e  
ON e.BusinessEntityID = pp.BusinessEntityID  
WHERE LastName = 'Johnson';  
GO  
-- Union ALL  
SELECT LastName, FirstName, JobTitle  
FROM dbo.EmployeeOne  
UNION ALL  
SELECT LastName, FirstName ,JobTitle  
FROM dbo.EmployeeTwo  
UNION ALL  
SELECT LastName, FirstName,JobTitle   
FROM dbo.EmployeeThree;  
GO  
  
SELECT LastName, FirstName,JobTitle  
FROM dbo.EmployeeOne  
UNION   
SELECT LastName, FirstName, JobTitle   
FROM dbo.EmployeeTwo  
UNION   
SELECT LastName, FirstName, JobTitle   
FROM dbo.EmployeeThree;  
GO  
  
SELECT LastName, FirstName,JobTitle   
FROM dbo.EmployeeOne  
UNION ALL  
(  
SELECT LastName, FirstName, JobTitle   
FROM dbo.EmployeeTwo  
UNION  
SELECT LastName, FirstName, JobTitle   
FROM dbo.EmployeeThree  
);  
GO  
  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>예: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] 및[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="e-using-a-simple-union"></a>5. 단순 UNION 사용  
 다음 예제에서는 결과 집합의 내용을 포함 됩니다.는 `CustomerKey` 둘 다의 열은 `FactInternetSales` 및 `DimCustomer` 테이블입니다. ALL 키워드는 사용 되지 않으므로 결과에서 중복 제외 됩니다.  
  
```  
-- Uses AdventureWorks  
  
SELECT CustomerKey   
FROM FactInternetSales    
UNION   
SELECT CustomerKey   
FROM DimCustomer   
ORDER BY CustomerKey;  
```  
  
### <a name="f-using-union-of-two-select-statements-with-order-by"></a>6. 두 SELECT 문에서 ORDER BY와 함께 UNION 사용  
 UNION 문에 SELECT 문의 ORDER BY 절을 포함 하는 경우 모든 SELECT 문의 한 후 해당 절에 포함 되어야 합니다. 다음 예제에서는 잘못 된 경우와 올바르게 사용한 `UNION` 두 `SELECT` 의 열 정렬에 ORDER BY와 함께 문입니다.  
  
```  
-- Uses AdventureWorks  
  
-- INCORRECT  
SELECT CustomerKey   
FROM FactInternetSales    
ORDER BY CustomerKey  
UNION   
SELECT CustomerKey   
FROM DimCustomer  
ORDER BY CustomerKey;  
  
-- CORRECT   
USE AdventureWorksPDW2012;  
  
SELECT CustomerKey   
FROM FactInternetSales    
UNION   
SELECT CustomerKey   
FROM DimCustomer   
ORDER BY CustomerKey;  
```  
  
### <a name="g-using-union-of-two-select-statements-with-where-and-order-by"></a>7. 두 개의 SELECT 문에서 UNION을 사용 하 여 where 및 ORDER BY  
 다음 예제에서는 잘못 된 경우와 올바르게 사용한 `UNION` 두 `SELECT` 문을 경우 위치 및 필요한 ORDER BY 합니다.  
  
```  
-- Uses AdventureWorks  
  
-- INCORRECT   
SELECT CustomerKey   
FROM FactInternetSales   
WHERE CustomerKey >= 11000  
ORDER BY CustomerKey   
UNION   
SELECT CustomerKey   
FROM DimCustomer   
ORDER BY CustomerKey;  
  
-- CORRECT  
USE AdventureWorksPDW2012;  
  
SELECT CustomerKey   
FROM FactInternetSales   
WHERE CustomerKey >= 11000  
UNION   
SELECT CustomerKey   
FROM DimCustomer   
ORDER BY CustomerKey;  
```  
  
### <a name="h-using-union-of-three-select-statements-to-show-effects-of-all-and-parentheses"></a>8. 세 개의 SELECT 문에서 UNION을 사용 하 여 모든 및 괄호  
 다음 예에서는 사용 `UNION` 의 결과를 결합 **같은 테이블** 사용 하는 경우 모든 및 괄호를 보여 주기 위해 `UNION`합니다.  
  
 사용 하 여 첫 번째 예제 `UNION ALL` 표시할 중복 된 레코드 및 반환 각 행이 원본 테이블에 세 번입니다. 두 번째 예에서는 `UNION` 없이 `ALL` 세 가지 결합된 된 결과에서 중복 행을 제거 하려면 `SELECT` 문 및 원본 테이블에서 중복된 행만 반환 합니다.  
  
 세 번째 예에서는 `ALL` 첫 번째 `UNION` 및 두 번째 묶는 괄호 `UNION` 사용 하지 않는 `ALL`합니다. 두 번째 `UNION` 괄호에 있기 때문에 먼저 처리 됩니다. 때문에 테이블에서 중복된 행만 반환는 `ALL` 옵션은 사용 되지 않으며 중복 항목이 제거 됩니다. 이러한 행의 첫 번째 결과와 결합 되 `SELECT` 를 사용 하 여는 `UNION ALL` 키워드입니다. 이 두 집합 간의 중복 행은 제거 되지 않습니다.  
  
```  
-- Uses AdventureWorks  
  
SELECT CustomerKey, FirstName, LastName  
FROM DimCustomer  
UNION ALL   
SELECT CustomerKey, FirstName, LastName  
FROM DimCustomer  
UNION ALL   
SELECT CustomerKey, FirstName, LastName  
FROM DimCustomer;  
  
SELECT CustomerKey, FirstName, LastName  
FROM DimCustomer  
UNION   
SELECT CustomerKey, FirstName, LastName  
FROM DimCustomer  
UNION   
SELECT CustomerKey, FirstName, LastName  
FROM DimCustomer;  
  
SELECT CustomerKey, FirstName, LastName  
FROM DimCustomer  
UNION ALL  
(  
SELECT CustomerKey, FirstName, LastName  
FROM DimCustomer  
UNION   
SELECT CustomerKey, FirstName, LastName  
FROM DimCustomer  
);  
```  
  
## <a name="see-also"></a>관련 항목:  
 [SELECT&#40;Transact-SQL&#41;](../../t-sql/queries/select-transact-sql.md)   
 [예제 &#40;를 선택 합니다. Transact SQL &#41;](../../t-sql/queries/select-examples-transact-sql.md)  
  
  

