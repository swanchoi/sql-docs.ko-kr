---
title: GETDATE (Transact SQL) | Microsoft Docs
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
- GETDATE_TSQL
- GETDATE
dev_langs:
- TSQL
helpviewer_keywords:
- dates [SQL Server], functions
- GETDATE function [SQL Server]
- current date and time [SQL Server]
- time [SQL Server], current
- functions [SQL Server], time
- system date and time [SQL Server]
- system time [SQL Server]
- functions [SQL Server], date and time
- time [SQL Server], functions
- dates [SQL Server], current date and time
- date and time [SQL Server], GETDATE
- dates [SQL Server], system date and time
- time [SQL Server], system
ms.assetid: bebe3b65-2b3e-4c73-bf80-ff1132c680a7
caps.latest.revision: 46
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 1c0cf660d5240e6a5222c44334f31f0beb94a749
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="getdate-transact-sql"></a>GETDATE(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  으로 현재 데이터베이스 시스템 타임 스탬프를 반환 합니다.는 **datetime** 데이터베이스 표준 시간대 오프셋 없는 값입니다. 이 값은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스를 실행하는 컴퓨터의 운영 체제에서 파생됩니다.  
  
> [!NOTE]  
>  SYSDATETIME 및 SYSUTCDATETIME에는 GETDATE 및 GETUTCDATE보다 많은 소수 자릿수 초의 전체 자릿수가 있습니다. SYSDATETIMEOFFSET에는 시스템 표준 시간대 오프셋이 포함되어 있습니다. SYSDATETIME, SYSUTCDATETIME 및 SYSDATETIMEOFFSET은 모든 날짜 및 시간 유형의 변수에 할당할 수 있습니다.  
  
 모든 개요 [!INCLUDE[tsql](../../includes/tsql-md.md)] 날짜 및 시간 데이터 형식 및 함수, 참조 [날짜 및 시간 데이터 형식 및 함수 &#40; Transact SQL &#41; ](../../t-sql/functions/date-and-time-data-types-and-functions-transact-sql.md).  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
GETDATE ( )  
```  
  
## <a name="return-type"></a>반환 형식  
 **datetime**  
  
## <a name="remarks"></a>주의  
 [!INCLUDE[tsql](../../includes/tsql-md.md)]문은 참조할 수 있습니다 GETDATE를 참조할 수 있는 모든 위치는 **datetime** 식입니다.  
  
 GETDATE는 확정적이 아닌 함수입니다. 열에서 이 함수를 참조하는 뷰와 식은 인덱싱될 수 없습니다.  
  
 GETDATE() 함수와 함께 SWITCHOFFSET을 사용하면 쿼리 최적화 프로그램이 GETDATE 값에 대한 정확한 카디널리티 예측을 얻을 수 없기 때문에 쿼리가 느리게 실행될 수 있습니다. 따라서 다음 예와 같이 GETDATE 값을 미리 계산한 다음 해당 값을 쿼리에서 지정하는 것이 좋습니다. 또한 다음에 동일한 쿼리를 실행할 때 쿼리 계획을 다시 쿼리 최적화 프로그램이 OPTION (RECOMPILE) 쿼리 힌트를 사용 합니다. 최적화 프로그램은 GETDATE()에 대한 정확한 카디널리티 예측을 갖게 되므로 보다 효율적인 쿼리 계획을 생성합니다.  
  
```  
DECLARE @dt datetimeoffset = switchoffset (CONVERT(datetimeoffset, GETDATE()), '-04:00');   
SELECT * FROM t    
WHERE c1 > @dt OPTION (RECOMPILE);  
  
```  
  
## <a name="examples"></a>예  
 다음 예에서는 현재 날짜 및 시간을 반환하는 6개의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 시스템 함수를 사용하여 시간, 날짜 또는 두 가지 모두 반환합니다. 값은 순차적으로 반환되므로 소수 자릿수 초가 서로 다를 수 있습니다.  
  
### <a name="a-getting-the-current-system-date-and-time"></a>1. 현재 시스템의 날짜 및 시간 가져오기  
  
```  
SELECT SYSDATETIME()  
    ,SYSDATETIMEOFFSET()  
    ,SYSUTCDATETIME()  
    ,CURRENT_TIMESTAMP  
    ,GETDATE()  
    ,GETUTCDATE();  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `SYSDATETIME()      2007-04-30 13:10:02.0474381`  
  
 `SYSDATETIMEOFFSET()2007-04-30 13:10:02.0474381 -07:00`  
  
 `SYSUTCDATETIME()   2007-04-30 20:10:02.0474381`  
  
 `CURRENT_TIMESTAMP  2007-04-30 13:10:02.047`  
  
 `GETDATE()          2007-04-30 13:10:02.047`  
  
 `GETUTCDATE()       2007-04-30 20:10:02.047`  
  
### <a name="b-getting-the-current-system-date"></a>2. 현재 시스템의 날짜 가져오기  
  
```  
SELECT CONVERT (date, SYSDATETIME())  
    ,CONVERT (date, SYSDATETIMEOFFSET())  
    ,CONVERT (date, SYSUTCDATETIME())  
    ,CONVERT (date, CURRENT_TIMESTAMP)  
    ,CONVERT (date, GETDATE())  
    ,CONVERT (date, GETUTCDATE());  
  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `SYSDATETIME()          2007-05-03`  
  
 `SYSDATETIMEOFFSET()    2007-05-03`  
  
 `SYSUTCDATETIME()       2007-05-04`  
  
 `CURRENT_TIMESTAMP      2007-05-03`  
  
 `GETDATE()              2007-05-03`  
  
 `GETUTCDATE()           2007-05-04`  
  
### <a name="c-getting-the-current-system-time"></a>3. 현재 시스템의 시간 가져오기  
  
```  
SELECT CONVERT (time, SYSDATETIME())  
    ,CONVERT (time, SYSDATETIMEOFFSET())  
    ,CONVERT (time, SYSUTCDATETIME())  
    ,CONVERT (time, CURRENT_TIMESTAMP)  
    ,CONVERT (time, GETDATE())  
    ,CONVERT (time, GETUTCDATE());  
  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `SYSDATETIME()      13:18:45.3490361`  
  
 `SYSDATETIMEOFFSET()13:18:45.3490361`  
  
 `SYSUTCDATETIME()   20:18:45.3490361`  
  
 `CURRENT_TIMESTAMP  13:18:45.3470000`  
  
 `GETDATE()          13:18:45.3470000`  
  
 `GETUTCDATE()       20:18:45.3470000`  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>예: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] 및[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 다음 예제에서는 세 개의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 및 날짜, 시간 또는 둘 다 반환할 시간을 현재 날짜를 반환 하는 시스템 함수입니다. 값은 순차적으로 반환되므로 소수 자릿수 초가 서로 다를 수 있습니다.  
  
### <a name="d-getting-the-current-system-date-and-time"></a>4. 현재 시스템의 날짜 및 시간 가져오기  
  
```  
SELECT SYSDATETIME()  
    ,CURRENT_TIMESTAMP  
    ,GETDATE();  
```  
  
### <a name="e-getting-the-current-system-date"></a>5. 현재 시스템의 날짜 가져오기  
  
```  
SELECT CONVERT (date, SYSDATETIME())  
    ,CONVERT (date, CURRENT_TIMESTAMP)  
    ,CONVERT (date, GETDATE());  
  
```  
  
### <a name="f-getting-the-current-system-time"></a>6. 현재 시스템의 시간 가져오기  
  
```  
SELECT CONVERT (time, SYSDATETIME())  
    ,CONVERT (time, CURRENT_TIMESTAMP)  
    ,CONVERT (time, GETDATE());  
  
```  
  
## <a name="see-also"></a>관련 항목:  
 [CAST 및 CONVERT&#40;Transact-SQL&#41;](../../t-sql/functions/cast-and-convert-transact-sql.md)  
  
  

