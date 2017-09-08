---
title: "선택 (Transact SQL) | Microsoft Docs"
ms.custom: 
ms.date: 08/09/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SELECT_TSQL
- SELECT
dev_langs:
- TSQL
helpviewer_keywords:
- retrieving rows
- SELECT statement [SQL Server]
- SELECT statement [SQL Server], about SELECT statement
- row retrieval [SQL Server], SELECT statement
- DML [SQL Server], SELECT statement
- data manipulation language [SQL Server], SELECT statement
- row retrieval [SQL Server]
- queries [SQL Server], results
ms.assetid: dc85caea-54d1-49af-b166-f3aa2f3a93d0
caps.latest.revision: 51
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 3cebbb09ffbc437ebdb4c0d0f5fdc5cf5a59adea
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="select-transact-sql"></a>SELECT (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  데이터베이스에서 행을 검색 하 고 하나 이상의 행 또는 열에서 하나 이상의 테이블을 선택할 수 있게 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]합니다. SELECT 문의 전체 구문은 복잡하지만 주요 절은 다음과 같이 요약할 수 있습니다.  
  
[으로 {[XMLNAMESPACES] [ \<common_table_expression >]}]
  
 선택 *select_list* [INTO *new_table* ]  
  
 [에서 *b l e _* ] [여기서 *c h _ c* ]  
  
 [GROUP BY *group_by_expression* ]  
  
 [필요 *c h _ c* ]  
  
 [ORDER BY *order_expression* [ASC | DESC]]  
  
 UNION, EXCEPT 및 INTERSECT 연산자를 결합 하거나 하나의 결과 집합으로 결과 비교 하는 쿼리 사이의 사용할 수 있습니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
-- Syntax for SQL Server and Azure SQL Database  
  
<SELECT statement> ::=    
    [ WITH { [ XMLNAMESPACES ,] [ <common_table_expression> [,...n] ] } ]  
    <query_expression>   
    [ ORDER BY { order_by_expression | column_position [ ASC | DESC ] }   
  [ ,...n ] ]   
    [ <FOR Clause>]   
    [ OPTION ( <query_hint> [ ,...n ] ) ]   
<query_expression> ::=   
    { <query_specification> | ( <query_expression> ) }   
    [  { UNION [ ALL ] | EXCEPT | INTERSECT }  
        <query_specification> | ( <query_expression> ) [...n ] ]   
<query_specification> ::=   
SELECT [ ALL | DISTINCT ]   
    [TOP ( expression ) [PERCENT] [ WITH TIES ] ]   
    < select_list >   
    [ INTO new_table ]   
    [ FROM { <table_source> } [ ,...n ] ]   
    [ WHERE <search_condition> ]   
    [ <GROUP BY> ]   
    [ HAVING < search_condition > ]   
```  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
[ WITH <common_table_expression> [ ,...n ] ]  
SELECT <select_criteria>  
[;]  
  
<select_criteria> ::=  
    [ TOP ( top_expression ) ]   
    [ ALL | DISTINCT ]   
    { * | column_name | expression } [ ,...n ]   
    [ FROM { table_source } [ ,...n ] ]  
    [ WHERE <search_condition> ]   
    [ GROUP BY <group_by_clause> ]   
    [ HAVING <search_condition> ]   
    [ ORDER BY <order_by_expression> ]  
    [ OPTION ( <query_option> [ ,...n ] ) ]  
  
```  
  
## <a name="remarks"></a>주의  
 SELECT 문은 복잡하기 때문에 자세한 구문 요소와 인수가 다음과 같은 절로 표시됩니다.  
  
|||  
|-|-|  
|[WITH XMLNAMESPACES](../../t-sql/xml/with-xmlnamespaces.md)<br /><br /> [WITH common_table_expression](../../t-sql/queries/with-common-table-expression-transact-sql.md)|[필요](../../t-sql/queries/select-having-transact-sql.md)|  
|[SELECT 절](../../t-sql/queries/select-clause-transact-sql.md)|[공용 구조체](../../t-sql/language-elements/set-operators-union-transact-sql.md)|  
|[INTO 절](../../t-sql/queries/select-into-clause-transact-sql.md)|[EXCEPT 및 INTERSECT](../../t-sql/language-elements/set-operators-except-and-intersect-transact-sql.md)|  
|[FROM](../../t-sql/queries/from-transact-sql.md)|[ORDER BY](../../t-sql/queries/select-order-by-clause-transact-sql.md)|  
|[WHERE](../../t-sql/queries/where-transact-sql.md)|[FOR 절](../../t-sql/queries/select-for-clause-transact-sql.md)|  
|[기준으로 그룹화](../../t-sql/queries/select-group-by-transact-sql.md)|[OPTION 절](../../t-sql/queries/option-clause-transact-sql.md)|  
  
 SELECT 문에서 절의 순서는 매우 중요합니다. 선택 사항인 절은 생략할 수 있지만 이러한 절을 사용할 때는 적절한 순서로 표시해야 합니다.  
  
 사용자 정의 함수 내의 SELECT 문은 함수에서 로컬인 변수에 값을 할당하는 식이 문의 선택 목록에 포함된 경우에만 허용됩니다.  
  
 서버 이름 부분에 OPENDATASOURCE 함수를 사용하여 네 부분으로 구성한 이름은 SELECT 문에서 테이블 이름이 표시될 수 있는 곳이면 어디든 테이블 원본으로 사용할 수 있습니다. 네 부분으로 된 이름을 지정할 수 없습니다 [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]합니다.  
  
 SELECT 문에는 원격 테이블과 관련된 몇몇 구문 제한이 적용됩니다.  
  
## <a name="logical-processing-order-of-the-select-statement"></a>SELECT 문의 논리적 처리 순서  
 다음 단계에서는 SELECT 문의 논리적 처리 순서(바인딩 순서)를 보여 줍니다. 이 순서에 따라 특정 단계에서 정의한 개체를 후속 단계의 절에 사용할 수 있는 시기가 결정됩니다. 예를 들어 쿼리 프로세스가 FROM 절에 정의된 테이블 또는 뷰에 바인딩(액세스)할 수 있는 경우 이러한 개체 및 해당 열을 모든 후속 단계에서 사용할 수 있습니다. 반면, SELECT 절은 8단계이므로 해당 절에서 정의된 열 별칭 또는 파생 열을 이전 절에서 참조할 수는 없습니다. 그러나 ORDER BY 절 등의 후속 절에서는 이러한 항목을 참조할 수 있습니다. 이 목록에서 순서가 다를 수 있습니다 및 문의 실제 실행은 쿼리 프로세서에 의해 결정 됩니다.  
  
1.  FROM  
2.  ON  
3.  JOIN  
4.  WHERE  
5.  GROUP BY  
6.  WITH CUBE 또는 WITH ROLLUP  
7.  HAVING  
8.  SELECT  
9. DISTINCT  
10. ORDER BY  
11. 맨 위로 이동  
  
## <a name="permissions"></a>Permissions  
 데이터를 선택하려면 테이블이나 뷰에 대한 **SELECT** 권한이 있어야 합니다. 이 권한은 스키마에 대한 **SELECT** 권한이나 테이블에 대한 **CONTROL** 권한과 같은 상위 범위에서 상속할 수 있습니다. 멤버 자격이 필요 또는 **db_datareader** 또는 **db_owner** 고정 데이터베이스 역할 또는 **sysadmin** 고정된 서버 역할입니다. 사용 하 여 새 테이블 만들기 **SELECTINTO** 둘 다 있어야는 **CREATETABLE** 권한, 및 **ALTERSCHEMA** 새 테이블을 소유 하는 스키마에 대 한 권한이 있습니다.  
  
## <a name="examples"></a>예:   
다음 예에서는 [!INCLUDE[ssawPDW](../../includes/ssawpdw-md.md)] 데이터베이스를 사용합니다.
  
### <a name="a-using-select-to-retrieve-rows-and-columns"></a>1. SELECT를 사용하여 행 및 열 검색  
 이 섹션에서는 세 개의 코드 예를 보여 줍니다. 이 첫 번째 코드 예제에서는 모든 행 (WHERE 절 없이 지정) 및 모든 열을 반환 합니다 (사용 하는 `*`)에서 `DimEmployee` 테이블입니다.  
  
```sql  
SELECT *  
FROM DimEmployee  
ORDER BY LastName;  
```  
  
 테이블 별칭 지정을 사용 하 여 동일한 결과 달성 하기 위해 다음 예제입니다.  
  
```sql  
SELECT e.*  
FROM DimEmployee AS e  
ORDER BY LastName;  
```  
  
 이 예에서는 모든 행 (WHERE 절 없이 지정) 및 열의 하위 집합 반환 (`FirstName`, `LastName`, `StartDate`)에서 `DimEmployee` 테이블에 `AdventureWorksPDW2012` 데이터베이스입니다. 세 번째 열 머리글 이름이 `FirstDay`합니다.  
  
```sql  
SELECT FirstName, LastName, StartDate AS FirstDay  
FROM DimEmployee   
ORDER BY LastName;  
```  
  
 이 예제에 대 한 행만 반환 `DimEmployee` 있는 `EndDate` NULL이 아니어야 및 `MaritalStatus` 의 AM' (기혼).  
  
```sql  
SELECT FirstName, LastName, StartDate AS FirstDay  
FROM DimEmployee   
WHERE EndDate IS NOT NULL   
AND MaritalStatus = 'M'  
ORDER BY LastName;  
```  
  
### <a name="b-using-select-with-column-headings-and-calculations"></a>2. SELECT에 열 머리글 및 계산 사용  
 모든 행을 반환 하는 다음 예제는 `DimEmployee` , 테이블을 기반으로 하는 각 직원에 대 한 총 급여 계산의 `BaseRate` 및 40 시간 작업 주입니다.  
  
```sql  
SELECT FirstName, LastName, BaseRate, BaseRate * 40 AS GrossPay  
FROM DimEmployee  
ORDER BY LastName;  
```  
  
### <a name="c-using-distinct-with-select"></a>3. SELECT에 DISTINCT 사용  
 다음 예제에서는 `DISTINCT` 의 모든 고유 이름 목록을 생성 하는 `DimEmployee` 테이블입니다.  
  
```sql  
SELECT DISTINCT Title  
FROM DimEmployee  
ORDER BY Title;  
```  
  
### <a name="d-using-group-by"></a>4. GROUP BY 사용  
 다음 예제에서는 각 날짜에 모든 판매에 대 한 총 금액을 찾습니다.  
  
```sql  
SELECT OrderDateKey, SUM(SalesAmount) AS TotalSales  
FROM FactInternetSales  
GROUP BY OrderDateKey  
ORDER BY OrderDateKey;  
```  
  
 때문에 `GROUP BY` 절, 모든 판매의 합계를 포함 하는 하나의 행은 각 날짜에 대해 반환 됩니다.  
  
### <a name="e-using-group-by-with-multiple-groups"></a>5. GROUP BY에 여러 그룹 사용  
 다음 예제에서는 인터넷 판매의 합계와 평균 가격 각 날짜에 대 한 주문 날짜 및 프로 모션 키로 그룹화 합니다.  
  
```sql  

SELECT OrderDateKey, PromotionKey, AVG(SalesAmount) AS AvgSales, SUM(SalesAmount) AS TotalSales  
FROM FactInternetSales  
GROUP BY OrderDateKey, PromotionKey  
ORDER BY OrderDateKey;   
```  
  
### <a name="f-using-group-by-and-where"></a>6. GROUP BY 및 WHERE 사용  
 다음 예에서는 2002 년 8 월 1 일 이후의 주문 날짜에 있는 행만 검색 한 후 그룹에 결과 저장 합니다.  
  
```sql  
SELECT OrderDateKey, SUM(SalesAmount) AS TotalSales  
FROM FactInternetSales  
WHERE OrderDateKey > '20020801'  
GROUP BY OrderDateKey  
ORDER BY OrderDateKey;  
```  
  
### <a name="g-using-group-by-with-an-expression"></a>7. GROUP BY에 식 사용  
 다음 예에서는 식으로 그룹화를 수행합니다. 식에 집계 함수가 없는 경우 식으로 그룹화를 수행할 수 있습니다.  
  
```sql  
SELECT SUM(SalesAmount) AS TotalSales  
FROM FactInternetSales  
GROUP BY (OrderDateKey * 10);  
```  
  
### <a name="h-using-group-by-with-order-by"></a>8. GROUP BY 및 ORDER BY 사용  
 다음 예제에서는 기준으로 주문을 만들고 하루에 판매량 합계를 찾습니다.  
  
```sql  
SELECT OrderDateKey, SUM(SalesAmount) AS TotalSales  
FROM FactInternetSales  
GROUP BY OrderDateKey  
ORDER BY OrderDateKey;  
```  
  
### <a name="i-using-the-having-clause"></a>9. HAVING 절 사용  
 이 쿼리에서 사용 하 여는 `HAVING` 결과 제한 하는 절.  
  
```sql  
SELECT OrderDateKey, SUM(SalesAmount) AS TotalSales  
FROM FactInternetSales  
GROUP BY OrderDateKey  
HAVING OrderDateKey > 20010000  
ORDER BY OrderDateKey;  
```  
  
## <a name="see-also"></a>관련 항목:  
 [예제 &#40;를 선택 합니다. Transact SQL &#41;](../../t-sql/queries/select-examples-transact-sql.md)  
 [힌트 &#40; Transact SQL &#41;](../../t-sql/queries/hints-transact-sql.md)
  

