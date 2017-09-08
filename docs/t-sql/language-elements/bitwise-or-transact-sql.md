---
title: "| (비트 OR) (Transact SQL) | Microsoft Docs"
ms.custom: 
ms.date: 01/10/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '|'
- '|_TSQL'
- Bitwise OR
- bitwise
- OR
dev_langs:
- TSQL
helpviewer_keywords:
- OR operator
- bitwise OR (|)
- '| (bitwise OR operator)'
ms.assetid: 86a3b87f-9688-4eaf-a552-29f1b01d880a
caps.latest.revision: 43
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 932b8cc8997a2faec55e56786a80e511fa9c273a
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="-bitwise-or-transact-sql"></a>|(비트 OR)(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  [!INCLUDE[tsql](../../includes/tsql-md.md)] 문에서 이진 식으로 변환되는 두 개의 지정된 정수 값 간에 비트 논리 OR 연산을 수행합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```   
expression | expression  
```  
  
## <a name="arguments"></a>인수  
 *expression*  
 유효한 [식](../../t-sql/language-elements/expressions-transact-sql.md) 정수 데이터 형식 범주 또는 **비트**, **이진**, 또는 **varbinary** 데이터 형식입니다. *식* 비트 연산을 위해 이진 숫자로 취급 됩니다.  
  
> [!NOTE]  
>  하나의 *식* 될 수 **이진** 또는 **varbinary** 연산의 데이터 형식입니다.  
  
## <a name="result-types"></a>결과 형식  
 반환 된 **int** 입력된 값이 **int**, **smallint** 입력된 값이 **smallint**, 또는 **tinyint** 입력된 값이 **tinyint**합니다.  
  
## <a name="remarks"></a>주의  
 비트 | 연산자는 양쪽 식에 해당 비트를 취하면서 두 식 간에 비트 논리 OR를 수행합니다. 결과의 비트는 입력 식의 두 비트(확인 중인 현재 비트) 중 하나 또는 둘 모두의 값이 1이면 1로 설정됩니다. 입력 식에 값이 1인 비트가 없으면 결과의 비트는 0으로 설정됩니다.  
  
 왼쪽 및 오른쪽 식의 경우에 다른 정수 데이터 형식 (예를 들어 왼쪽 *식* 은 **smallint** 및 오른쪽 *식* 은  **int**), 더 작은 데이터 형식의 인수를 더 큰 데이터 형식으로 변환 합니다. 이 예제는 **smallint***식* 변환할는 **int**합니다.  
  
## <a name="examples"></a>예  
 다음 예제에서는 있는 테이블 **int** 데이터 원래 값을 표시 하려면 형식 및 테이블에 하나의 행에 넣습니다.  
  
```tsql  
CREATE TABLE bitwise  
(   
 a_int_value int NOT NULL,  
b_int_value int NOT NULL  
);  
GO  
INSERT bitwise VALUES (170, 75);  
GO  
```  
  
 비트 OR 연산을 수행 하는 다음 쿼리는 **a_int_value** 및 **b_int_value** 열입니다.  
  
```  
SELECT a_int_value | b_int_value  
FROM bitwise;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
-----------   
235           
  
(1 row(s) affected)  
```  
  
 170의 이진 표현 (**a_int_value** 또는 `A`아래)은 `0000 0000 1010 1010`합니다. 75의 이진 표현 (**b_int_value** 또는 `B`아래)은 `0000 0000 0100 1011`합니다. 이 두 값에 비트 OR 연산을 수행하면 10진수 235에 해당되는 이진 결과 `0000 0000 1110 1011`이 산출됩니다.  
  
```  
(A | B)  
0000 0000 1010 1010  
0000 0000 0100 1011  
-------------------  
0000 0000 1110 1011  
```  
  
## <a name="see-also"></a>관련 항목:  
 [연산자 &#40; Transact SQL &#41;](../../t-sql/language-elements/operators-transact-sql.md)   
 [비트 연산자 &#40; Transact SQL &#41;](../../t-sql/language-elements/bitwise-operators-transact-sql.md)   
 [&#124; = &#40; 비트 OR EQUALS &#41; &#40; Transact SQL &#41;](../../t-sql/language-elements/bitwise-or-equals-transact-sql.md)   
 [복합 연산자 &#40; Transact SQL &#41;](../../t-sql/language-elements/compound-operators-transact-sql.md)  
  
  


