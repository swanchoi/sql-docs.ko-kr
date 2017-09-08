---
title: NULLIF (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 08/16/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- NULLIF
- NULLIF_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- null values [SQL Server], equivalent expressions
- expressions [SQL Server], null values
- NULLIF function
- equivalent expressions [SQL Server]
ms.assetid: 44c7b67e-74c7-4bb9-93a4-7a3016bd2feb
caps.latest.revision: 48
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: e07e3960466d782911c20ced9ce6d88a10406bc2
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="nullif-transact-sql"></a>NULLIF(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  지정된 두 식이 같으면 Null 값을 반환합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
NULLIF ( expression , expression )  
```  
  
## <a name="arguments"></a>인수  
 *expression*  
 유효한 스칼라 [식](../../t-sql/language-elements/expressions-transact-sql.md)합니다.  
  
## <a name="return-types"></a>반환 형식  
 첫 번째과 같은 유형을 반환 *식*합니다.  
  
 NULLIF는 첫 번째 개체가 반환 *식* 두 식이 같지 않으면 합니다. NULLIF는 첫 번째 형식의 null 값을 반환 식이 같으면 *식*합니다.  
  
## <a name="remarks"></a>주의  
 NULLIF는 두 식이 동일하며 결과 식이 NULL인 검색된 CASE 식과 동일합니다.  
  
 NULLIF 함수 내에 RAND()와 같은 시간에 종속적인 함수를 사용하지 않는 것이 좋습니다. 이 인해 함수를 두 번 평가 하 고 두 호출에서 다른 결과 반환할 수 없습니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-returning-budget-amounts-that-have-not-changed"></a>1. 변경되지 않은 예산 반환  
 다음 예에서는 부서(`budgets`), 금년도 예산(`dept`) 및 전년도 예산(`current_year`)을 보여 주는 `previous_year` 테이블을 만듭니다. 금년 예산이 전년도 예산에서 변하지 않은 부서에는 `NULL`이 예산이 아직 결정되지 않은 부서에는 `0`이 사용됩니다. 예산이 결정된 부서만의 평균을 계산하고 이전 연도의 예산 값(`previous_year` 값 사용. 여기서 `current_year`는 `NULL`임)을 포함하려면 `NULLIF` 함수와 `COALESCE` 함수를 결합합니다.  
  
```sql  
CREATE TABLE dbo.budgets  
(  
   dept            tinyint   IDENTITY,  
   current_year      decimal   NULL,  
   previous_year   decimal   NULL  
);  
INSERT budgets VALUES(100000, 150000);  
INSERT budgets VALUES(NULL, 300000);  
INSERT budgets VALUES(0, 100000);  
INSERT budgets VALUES(NULL, 150000);  
INSERT budgets VALUES(300000, 250000);  
GO    
SET NOCOUNT OFF;  
SELECT AVG(NULLIF(COALESCE(current_year,  
   previous_year), 0.00)) AS 'Average Budget'  
FROM budgets;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```
 Average Budget  
 --------------  
 212500.000000  
 (1 row(s) affected)
 ```  
  
### <a name="b-comparing-nullif-and-case"></a>2. NULLIF 및 CASE 비교  
 `NULLIF`와 `CASE`의 유사점을 보여 주기 위해 다음 쿼리는 `MakeFlag` 및 `FinishedGoodsFlag` 열의 값이 같은지 여부를 평가합니다. 첫 번째 쿼리에서는 `NULLIF`를 사용합니다. 두 번째 쿼리에서는 `CASE` 식을 사용합니다.  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT ProductID, MakeFlag, FinishedGoodsFlag,   
   NULLIF(MakeFlag,FinishedGoodsFlag)AS 'Null if Equal'  
FROM Production.Product  
WHERE ProductID < 10;  
GO  
  
SELECT ProductID, MakeFlag, FinishedGoodsFlag,'Null if Equal' =  
   CASE  
       WHEN MakeFlag = FinishedGoodsFlag THEN NULL  
       ELSE MakeFlag  
   END  
FROM Production.Product  
WHERE ProductID < 10;  
GO  
```  

### <a name="c-returning-budget-amounts-that-contain-no-data"></a>C: 데이터가 없는 예산 반환  
 다음 예제에서는 `budgets` 테이블 데이터를 로드 및 사용 하 여 `NULLIF` 모두 null을 반환 하려면 `current_year` 또는 `previous_year` 데이터를 포함 합니다.  
  
```sql  
CREATE TABLE budgets (  
   dept           tinyint,  
   current_year   decimal(10,2),  
   previous_year  decimal(10,2)  
);  
  
INSERT INTO budgets VALUES(1, 100000, 150000);  
INSERT INTO budgets VALUES(2, NULL, 300000);  
INSERT INTO budgets VALUES(3, 0, 100000);  
INSERT INTO budgets VALUES(4, NULL, 150000);  
INSERT INTO budgets VALUES(5, 300000, 300000);  
  
SELECT dept, NULLIF(current_year,  
   previous_year) AS LastBudget  
FROM budgets;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```
 dept   LastBudget  
 ----   -----------  
 1      100000.00  
 2      null 
 3      0.00  
 4      null  
 5      null
 ```  
  
## <a name="see-also"></a>관련 항목:  
 [대/소문자 &#40; Transact SQL &#41;](../../t-sql/language-elements/case-transact-sql.md)   
 [decimal 및 numeric&#40; Transact SQL &#41;](../../t-sql/data-types/decimal-and-numeric-transact-sql.md)   
 [시스템 함수 &#40; Transact SQL &#41;](../../relational-databases/system-functions/system-functions-for-transact-sql.md)  
  
  

