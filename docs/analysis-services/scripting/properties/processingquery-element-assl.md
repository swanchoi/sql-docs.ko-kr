---
title: "ProcessingQuery 요소 (ASSL) | Microsoft Docs"
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
- ProcessingQuery Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- ProcessingQuery element
ms.assetid: d18e6f4b-c24c-4f73-8b85-4b6e8a82a695
caps.latest.revision: 12
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: f9c2d9f0607e51f754657a5cbd2750eff5fc173a
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="processingquery-element-assl"></a>ProcessingQuery 요소(ASSL)
  증분 처리 상태 알림을 위해 실행할 쿼리의 매개 변수가 있는 텍스트를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<IncrementalProcessingNotification>  
   ...  
   <ProcessingQuery>...</ProcessingQuery>  
   ...  
</IncrementalProcessingNotification>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특징|설명|  
|--------------------|-----------------|  
|데이터 형식 및 길이|문자열|  
|기본값|없음|  
|카디널리티|1-1: 한 번만 나타나는 필수 요소입니다.|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|-------------|  
|부모 요소|[IncrementalProcessingNotification](../../../analysis-services/scripting/objects/incrementalprocessingnotification-element-assl.md)|  
|자식 요소|없음|  
  
## <a name="remarks"></a>주의  
 테이블에는 [DataSourceView](../../../analysis-services/scripting/objects/datasourceview-element-assl.md) 에서 참조 하는 **ProcessingQuery** 형제 요소로 식별 됩니다 [TableID](../../../analysis-services/scripting/properties/tableid-element-assl.md)합니다.  
  
 부모에 해당 하는 요소 **ProcessingQuery** Analysis Management Objects (AMO) 개체 모델은 <xref:Microsoft.AnalysisServices.IncrementalProcessingNotification>합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [속성 &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  