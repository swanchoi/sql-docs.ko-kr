---
title: NULL(SSIS 식) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- NULL function
- null values [Integration Services]
ms.assetid: df144237-3fbb-41ac-8624-efd92b6522b9
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: 2713a1d1f8f5db05f07bafc14ee8ce96314d46b1
ms.sourcegitcommit: 7ccb8f28eafd79a1bddd523f71fe8b61c7634349
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2019
ms.locfileid: "58275206"
---
# <a name="null-ssis-expression"></a>NULL(SSIS 식)
  요청한 데이터 형식의 Null 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
NULL(typespec)  
```  
  
## <a name="arguments"></a>인수  
 *typespec*  
 유효한 데이터 형식입니다. 자세한 내용은 [Integration Services Data Types](../../integration-services/data-flow/integration-services-data-types.md)을 참조하세요.  
  
## <a name="result-types"></a>결과 형식  
 Null 값을 가진 유효한 데이터 형식입니다.  
  
## <a name="remarks"></a>Remarks  
 인수가 Null이면 NULL 결과도 Null입니다.  
  
 일부 데이터 형식의 Null 값을 요청하려면 매개 변수가 필요합니다. 다음 표에서는 이러한 데이터 형식과 해당 매개 변수를 보여 줍니다.  
  
|데이터 형식|매개 변수|예제|  
|---------------|---------------|-------------|  
|DT_STR|*charcount*<br /><br /> *codepage*|(DT_STR,30,1252)는 1252 코드 페이지를 사용하여 30자를 DT_STR 데이터 형식으로 캐스팅합니다.|  
|DT_WSTR|*charcount*|(DT_WSTR,20)은 20자를 DT_WSTR 데이터 형식으로 캐스팅합니다.|  
|DT_BYTES|*bytecount*|(DT_BYTES,50)은 50바이트를 DT_BYTES 데이터 형식으로 캐스팅합니다.|  
|DT_DECIMAL|*소수 자릿수*|(DT_DECIMAL,2)는 소수 자릿수 2를 사용하여 숫자 값을 DT_DECIMAL 데이터 형식으로 캐스팅합니다.|  
|DT_NUMERIC|*전체 자릿수*<br /><br /> *scale*|(DT_NUMERIC,10,3)은 전체 자릿수 10, 소수 자릿수 3을 사용하여 숫자 값을 DT_NUMERIC 데이터 형식으로 캐스팅합니다.|  
|DT_TEXT|*codepage*|(DT_TEXT,1252)는 1252 코드 페이지를 사용하여 값을 DT_TEXT 데이터 형식으로 캐스팅합니다.|  
  
## <a name="expression-examples"></a>식 예  
 이 예에서는 DT_STR, DT_DATE 및 DT_BOOL 데이터 형식의 Null 값을 반환합니다.  
  
```  
NULL(DT_STR,10,1252)  
NULL(DT_DATE)  
NULL(DT_BOOL)  
```  
  
## <a name="see-also"></a>참고 항목  
 [ISNULL&#40;SSIS 식&#41;](../../integration-services/expressions/isnull-ssis-expression.md)   
 [함수&#40;SSIS 식&#41;](../../integration-services/expressions/functions-ssis-expression.md)  
  
  
