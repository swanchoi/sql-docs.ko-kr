---
title: DATEPART(SSIS 식) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- dates [Integration Services], DATEPART
- DATEPART function
ms.assetid: 3e590094-fc49-4144-805f-fdc1bf2fe509
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: 22225f9a1791185ed78dfc75d92c3dbced7be3ff
ms.sourcegitcommit: 5a8678bf85f65be590676745a7fe4fcbcc47e83d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58375071"
---
# <a name="datepart-ssis-expression"></a>DATEPART(SSIS 식)
  날짜의 특정 부분을 나타내는 정수를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
DATEPART(datepart, date)  
```  
  
## <a name="arguments"></a>인수  
 *날짜 부분*  
 새 값을 반환할 날짜 부분을 지정하는 매개 변수입니다.  
  
 *date*  
 유효한 날짜 또는 날짜 형식의 문자열을 반환하는 식입니다.  
  
## <a name="result-types"></a>결과 형식  
 DT_I4  
  
## <a name="remarks"></a>Remarks  
 인수가 Null이면 DATEPART 결과도 Null입니다.  
  
 날짜 리터럴은 다음의 날짜 데이터 형식 중 하나로 명시적 캐스팅되어야 합니다. 자세한 내용은 [Integration Services Data Types](../data-flow/integration-services-data-types.md)을 참조하세요.  
  
 다음 표에서는 식 계산기가 인식하는 날짜 부분 및 약어를 나열합니다. 날짜 부분 이름은 대/소문자를 구분하지 않습니다.  
  
|날짜 부분|약어|  
|--------------|-------------------|  
|Year|yy, yyyy|  
|Quarter|qq, q|  
|Month|mm, m|  
|Dayofyear|dy, y|  
|Day|dd, d|  
|Week|wk, ww|  
|Weekday|dw|  
|Hour|Hh|  
|Minute|mi, n|  
|둘째|ss, s|  
|Millisecond|Ms|  
  
## <a name="ssis-expression-examples"></a>SSIS 식 예  
 이 예에서는 날짜 리터럴의 월을 나타내는 정수가 반환됩니다. 날짜 형식이 "mm/dd/yyyy"이면 이 예에서는 11이 반환됩니다.  
  
```  
DATEPART("month", (DT_DBTIMESTAMP)"11/04/2002")  
```  
  
 이 예에서는 **ModifiedDate** 열의 일 부분을 나타내는 정수를 반환합니다.  
  
```  
DATEPART("dd", ModifiedDate)  
```  
  
 이 예에서는 현재 날짜의 연도를 나타내는 정수를 반환합니다.  
  
```  
DATEPART("yy",GETDATE())  
```  
  
## <a name="see-also"></a>관련 항목  
 [DATEADD&#40;SSIS 식&#41;](dateadd-ssis-expression.md)   
 [DATEDIFF&#40;SSIS 식&#41;](datediff-ssis-expression.md)   
 [DAY&#40;SSIS 식&#41;](day-ssis-expression.md)   
 [MONTH&#40;SSIS 식&#41;](month-ssis-expression.md)   
 [YEAR&#40;SSIS 식&#41;](year-ssis-expression.md)   
 [함수&#40;SSIS 식&#41;](functions-ssis-expression.md)  
  
  
