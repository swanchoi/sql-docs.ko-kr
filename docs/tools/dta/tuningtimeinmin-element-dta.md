---
title: TuningTimeInMin 요소 (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TuningTimeInMin element
ms.assetid: 4973d9ac-20fd-4ac3-bc9f-5d60e39fdb7d
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 908b4b6b8f4551fd5b611997dabedc5f1cf1c474
ms.sourcegitcommit: 0f7cf9b7ab23df15624d27c129ab3a539e8b6457
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51292414"
---
# <a name="tuningtimeinmin-element-dta"></a>TuningTimeInMin 요소(DTA)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  튜닝 세션의 최대 길이(분)를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <TuningTimeInMin>...</TuningTimeInMin>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특징|설명|  
|--------------------|-----------------|  
|**데이터 형식 및 길이**|**unsignedInt**, 길이 제한 없음|  
|**기본값**|480분(8시간)|  
|**발생 빈도**|**NumberOfEvents** 요소에 값을 지정하지 않은 경우 지정해야 합니다.|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|--------------|  
|**부모 요소**|[TuningOptions 요소&#40;DTA&#41;](../../tools/dta/tuningoptions-element-dta.md)|  
|**자식 요소**|없음|  
  
## <a name="example"></a>예제  
  
## <a name="description"></a>설명  
 다음 코드 예에서는 최대 튜닝 시간을 12시간으로 설정하는 방법을 보여 줍니다.  
  
## <a name="code"></a>코드  
  
```  
<DTAInput>  
  <Server>...</Server>  
  <Workload>...</Workload>  
  <TuningOptions>  
    <TuningTimeInMin>720</TuningTimeInMin>  
...code removed here...  
</DTAInput>  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 입력 파일 참조&#40;데이터베이스 엔진 튜닝 관리자&#41;](../../tools/dta/xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
