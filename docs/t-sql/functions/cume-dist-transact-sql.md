---
title: CUME_DIST (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CUME_DIST
- CUME_DIST_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- CUME_DIST function
- analytic functions, CUME_DIST
ms.assetid: 491b07f3-9ffd-4cdd-93e5-5abb636fc5ef
caps.latest.revision: 19
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 22364fce2c5c8bfa2707f1f270dd728735096a31
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="cumedist-transact-sql"></a>CUME_DIST(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-asdb-asdw-xxx_md](../../includes/tsql-appliesto-ss2012-asdb-asdw-xxx-md.md)]

[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 값 그룹에 있는 값의 누적 분포를 계산합니다. 즉, CUME_DIST는 값 그룹에서 지정한 값의 상대적 위치를 계산합니다. 행에 대해 *r*오름차순으로 정렬의 CUME_DIST 가정 하 고 *r* 보다 값이 있는 행 수의 값 보다 낮은 크거나 *r*행의 수로 나눈, 파티션 또는 쿼리 결과 집합의 계산 합니다. CUME_DIST는 PERCENT_RANK 함수와 비슷합니다.
  
![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>구문  
  
```sql
CUME_DIST( )  
    OVER ( [ partition_by_clause ] order_by_clause )  
  
```  
  
## <a name="arguments"></a>인수  
통해 **(** [ *partition_by_clause* ] *order_by_clause***)**  
*partition_by_clause* 함수가 적용 되는 파티션으로 FROM 절에서 생성 한 결과 집합을 나눕니다. 지정하지 않을 경우 쿼리 결과 집합의 모든 행이 단일 그룹으로 취급됩니다. *order_by_clause* 작업이 수행 되는 논리적 순서를 결정 합니다. *order_by_clause* 가 필요 합니다. \<s 또는 range 절 > OVER 구문 CUME_DIST 함수에 지정할 수 없습니다. 자세한 내용은 참조 [OVER 절 &#40; Transact SQL &#41; ](../../t-sql/queries/select-over-clause-transact-sql.md).
  
## <a name="return-types"></a>반환 형식
**float(53)**
  
## <a name="remarks"></a>주의  
CUME_DIST가 반환하는 값 범위는 0보다 크고 1보다 작거나 같습니다. 동일한 값은 항상 동일한 누적 분포 값으로 계산되어야 합니다. NULL 값은 기본적으로 포함되며 가능한 가장 낮은 값으로 취급됩니다.
  
CUME_DIST는 비결정적입니다. 자세한 내용은 [Deterministic and Nondeterministic Functions](../../relational-databases/user-defined-functions/deterministic-and-nondeterministic-functions.md)을 참조하세요.
  
## <a name="examples"></a>예  
다음 예에서는 CUME_DIST 함수를 사용하여 지정한 부서 내 각 직원의 연봉을 백분율로 계산합니다. CUME_DIST 함수가 반환하는 값은 같은 동일 부서 내에서 현재 직원보다 연봉이 적거나 같은 직원의 백분율을 나타냅니다. PERCENT_RANK 함수는 부서 내 직원의 연봉을 백분율 순위로 계산합니다. 결과 집합의 행을 부서별로 분할하기 위해 PARTITION BY 절이 지정되었습니다. OVER 절에서 ORDER BY 절은 각 파티션의 행을 논리적으로 정렬합니다. SELECT 문의 ORDER BY 절은 결과 집합의 표시 순서를 결정합니다.
  
```sql
USE AdventureWorks2012;  
GO  
SELECT Department, LastName, Rate,   
       CUME_DIST () OVER (PARTITION BY Department ORDER BY Rate) AS CumeDist,   
       PERCENT_RANK() OVER (PARTITION BY Department ORDER BY Rate ) AS PctRank  
FROM HumanResources.vEmployeeDepartmentHistory AS edh  
    INNER JOIN HumanResources.EmployeePayHistory AS e    
    ON e.BusinessEntityID = edh.BusinessEntityID  
WHERE Department IN (N'Information Services',N'Document Control')   
ORDER BY Department, Rate DESC;  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```sql
  
Department             LastName               Rate                  CumeDist               PctRank  
---------------------- ---------------------- --------------------- ---------------------- ----------------------  
Document Control       Arifin                 17.7885               1                      1  
Document Control       Norred                 16.8269               0.8                    0.5  
Document Control       Kharatishvili          16.8269               0.8                    0.5  
Document Control       Chai                   10.25                 0.4                    0  
Document Control       Berge                  10.25                 0.4                    0  
Information Services   Trenary                50.4808               1                      1  
Information Services   Conroy                 39.6635               0.9                    0.888888888888889  
Information Services   Ajenstat               38.4615               0.8                    0.666666666666667  
Information Services   Wilson                 38.4615               0.8                    0.666666666666667  
Information Services   Sharma                 32.4519               0.6                    0.444444444444444  
Information Services   Connelly               32.4519               0.6                    0.444444444444444  
Information Services   Berg                   27.4038               0.4                    0  
Information Services   Meyyappan              27.4038               0.4                    0  
Information Services   Bacon                  27.4038               0.4                    0  
Information Services   Bueno                  27.4038               0.4                    0  
(15 row(s) affected)  
```  
  
## <a name="see-also"></a>참고 항목
[PERCENT_RANK &#40; Transact SQL &#41;](../../t-sql/functions/percent-rank-transact-sql.md)
  
  
