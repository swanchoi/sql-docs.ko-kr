---
title: "NamingTemplateTranslation 요소 (ASSL) | Microsoft Docs"
ms.custom: 
ms.date: 03/17/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- NamingTemplateTranslation Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- NamingTemplateTranslation
helpviewer_keywords:
- NamingTemplateTranslation element
ms.assetid: 4a97a31d-23bc-4afd-a4dc-bc0ad7121f08
caps.latest.revision: 29
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: aa966a46acf8f6ce0c40b7c2ffb341552afa4e99
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="namingtemplatetranslation-element-assl"></a>NamingTemplateTranslation 요소(ASSL)
  지역화 된 번역을 제공 된 [NamingTemplate](../../../analysis-services/scripting/properties/namingtemplate-element-assl.md) 요소는 부모에 대 한 [DimensionAttribute](../../../analysis-services/scripting/data-type/dimensionattribute-data-type-assl.md) 데이터 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<NamingTemplateTranslations>  
   <NamingTemplateTranslation xsi:type="Translation">...</NamingTemplateTranslation>  
</NamingTemplateTranslations>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특징|설명|  
|--------------------|-----------------|  
|데이터 형식 및 길이|[번역](../../../analysis-services/scripting/objects/translation-element-assl.md)|  
|기본값|없음|  
|카디널리티|0-1: 한 번만 나타날 수 있는 선택적 요소입니다.|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|-------------|  
|부모 요소|[NamingTemplateTranslations](../../../analysis-services/scripting/collections/namingtemplatetranslations-element-assl.md)|  
|자식 요소|없음|  
  
## <a name="remarks"></a>주의  
 값은 **NamingTemplateTranslation** 요소 부모 특성에만 사용 됩니다 (의 값 즉,는 [사용량](../../../analysis-services/scripting/properties/usage-element-dimensionattribute-assl.md) 의 요소는 **DimensionAttribute** 로 설정 된 부모 *부모*)의 지역화 된 번역을 저장 하는 **NamingTemplate** 지정된 된 언어에 대 한 값입니다.  
  
 부모에 해당 하는 요소 **NamingTemplateTranslations** Analysis Management Objects (AMO) 개체 모델은 <xref:Microsoft.AnalysisServices.DimensionAttribute>합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [NamingTemplate 요소 &#40; ASSL &#41;](../../../analysis-services/scripting/properties/namingtemplate-element-assl.md)   
 [개체 &#40; ASSL &#41;](../../../analysis-services/scripting/objects/objects-assl.md)  
  
  