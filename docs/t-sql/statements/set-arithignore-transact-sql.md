---
title: SET ARITHIGNORE (Transact SQL) | Microsoft Docs
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
- SET ARITHIGNORE
- SET_ARITHIGNORE_TSQL
- ARITHIGNORE
- ARITHIGNORE_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- SET ARITHIGNORE statement
- overflow errors [SQL Server]
- ARITHIGNORE option
- divide-by-zero errors
ms.assetid: 71b2c2a5-c83a-4dfe-8469-237987a6e503
caps.latest.revision: 40
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 779510e1a7a302fc4bfd4a730b88db9c4b4a4b1b
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="set-arithignore-transact-sql"></a>SET ARITHIGNORE(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  쿼리 실행 중 오버플로 또는 0으로 나누기 오류에서 오류 메시지를 반환할지 여부를 제어합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
-- Syntax for SQL Server and Azure SQL Database  
    
SET ARITHIGNORE { ON | OFF }  
[ ; ]  
```  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
SET ARITHIGNORE OFF   
[ ; ]  
```  
  
## <a name="remarks"></a>주의  
 SET ARITHIGNORE 설정은 오류 메시지 반환 여부만 제어합니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]는 이 설정에 관계없이 오버플로 또는 0으로 나누기 오류와 연관된 계산에서 NULL을 반환합니다. SET ARITHABORT 설정을 사용하여 쿼리 종료 여부를 결정할 수 있습니다. 그러나 이 설정은 INSERT, UPDATE, DELETE 문 실행 중에 발생한 오류에는 영향을 주지 않습니다.  
  
 SET ARITHABORT 옵션이나 SET ARITHIGNORE 옵션 중 하나가 OFF이고 SET ANSI_WARNINGS 옵션이 ON이면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 0으로 나누기 또는 오버플로 오류가 발생할 경우 여전히 오류 메시지를 반환합니다.  
  
 SET ARITHIGNORE 옵션은 실행 시간 또는 런타임에 설정되며, 구문 분석 시에는 설정되지 않습니다.  
  
 이 설정에 대한 현재 설정을 보려면 다음 쿼리를 실행합니다.  
  
```  
DECLARE @ARITHIGNORE VARCHAR(3) = 'OFF';  
IF ( (128 & @@OPTIONS) = 128 ) SET @ARITHIGNORE = 'ON';  
SELECT @ARITHIGNORE AS ARITHIGNORE;  
  
```  
  
## <a name="permissions"></a>Permissions  
 public 역할의 멤버 자격이 필요합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 `SET ARITHIGNORE`의 두 가지 설정을 사용하여 두 가지 유형의 쿼리 오류를 보여 줍니다.  
  
```  
SET ARITHABORT OFF;  
SET ANSI_WARNINGS OFF  
GO  
  
PRINT 'Setting ARITHIGNORE ON';  
GO  
-- SET ARITHIGNORE ON and testing.  
SET ARITHIGNORE ON;  
GO  
SELECT 1 / 0 AS DivideByZero;  
GO  
SELECT CAST(256 AS TINYINT) AS Overflow;  
GO  
  
PRINT 'Setting ARITHIGNORE OFF';  
GO  
-- SET ARITHIGNORE OFF and testing.  
SET ARITHIGNORE OFF;  
GO  
SELECT 1 / 0 AS DivideByZero;  
GO  
SELECT CAST(256 AS TINYINT) AS Overflow;  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>예: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] 및[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 다음 예제는 0으로 나누기와 오버플로 오류입니다. ARITHIGNORE가 OFF입니다. 때문에이 예제에서는 이러한 오류에 대 한 오류 메시지를 반환 하지 않습니다.  
  
```  
-- SET ARITHIGNORE OFF and testing.  
SET ARITHIGNORE OFF;  
SELECT 1 / 0 AS DivideByZero;  
SELECT CAST(256 AS TINYINT) AS Overflow;  
  
```  
  
## <a name="see-also"></a>관련 항목:  
 [SET 문&#40;Transact-SQL&#41;](../../t-sql/statements/set-statements-transact-sql.md)   
 [SET arithabort&#40; Transact SQL &#41;](../../t-sql/statements/set-arithabort-transact-sql.md)  
  
  

