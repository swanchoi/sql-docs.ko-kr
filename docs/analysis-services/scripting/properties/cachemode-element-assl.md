---
title: "CacheMode 요소 (ASSL) | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- CacheMode Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- CacheMode element
ms.assetid: bfb8f7bb-ccd3-4dfe-a36a-1cea15edfe40
caps.latest.revision: 13
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 4a5af62efbab01b78a68af1ec7f94caeaaaea22a
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="cachemode-element-assl"></a>CacheMode 요소(ASSL)
  마이닝 구조를 처리하는 동안 검색된 학습 데이터에 사용되는 캐싱 메커니즘을 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<MiningStructure>  
   ...  
   <CacheMode>...</CacheMode>  
   ...  
</MiningStructure>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특징|설명|  
|--------------------|-----------------|  
|데이터 형식 및 길이|String(열거형)|  
|기본값|*KeepTrainingCases*|  
|카디널리티|0-1: 한 번만 나타날 수 있는 선택적 요소입니다.|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|-------------|  
|부모 요소|[MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md)|  
|자식 요소|없음|  
  
## <a name="remarks"></a>주의  
 이 요소의 값은 다음 표에 있는 문자열 중 하나로 제한됩니다.  
  
|값|Description|  
|-----------|-----------------|  
|*KeepTrainingCases*|학습 사례가 처리 도중과 처리 후에 캐시됩니다.|  
|*ClearAfterProcessing*|학습 사례가 처리 도중에 캐시되지만 처리 후에는 삭제됩니다.|  
  
## <a name="remarks"></a>주의  
 부모에 해당 하는 요소 **CacheMode** Analysis Management Objects (AMO) 개체 모델은 <xref:Microsoft.AnalysisServices.MiningStructure>합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [속성 &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  