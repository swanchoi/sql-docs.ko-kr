---
title: "값 요소 (ASSL) | Microsoft Docs"
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
- Value Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- Value
helpviewer_keywords:
- Value element
ms.assetid: a2fad411-73fd-42df-b4e1-df2cb8454182
caps.latest.revision: 36
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 5b31ced28db41575887a07ccf6c6e303aea5aaf1
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="value-element-assl"></a>Value 요소(ASSL)
  부모 요소의 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<AlgorithmParameter> <!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <Value>...</Value>  
   ...  
</AlgorithmParameter>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특징|설명|  
|--------------------|-----------------|  
|데이터 형식 및 길이|아래 표를 참조 합니다.|  
|기본값|없음|  
|카디널리티|1-1: 한 번만 나타나는 필수 요소입니다.|  
  
|상위 항목 또는 부모|데이터 형식|  
|------------------------|---------------|  
|[AlgorithmParameter](../../../analysis-services/scripting/objects/algorithmparameter-element-assl.md)|모든 simpleType|  
|[ServerProperty](../../../analysis-services/scripting/objects/serverproperty-element-assl.md)|모든 simpleType|  
|나머지|문자열|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|-------------|  
|부모 요소|[AlgorithmParameter](../../../analysis-services/scripting/objects/algorithmparameter-element-assl.md), [주석](../../../analysis-services/scripting/objects/annotation-element-assl.md), [Kpi](../../../analysis-services/scripting/objects/kpi-element-assl.md), [ReportFormatParameter](../../../analysis-services/scripting/objects/reportformatparameter-element-asl.md), [ReportParameter](../../../analysis-services/scripting/objects/reportparameter-element-assl.md), [ServerProperty](../../../analysis-services/scripting/objects/serverproperty-element-assl.md)|  
|자식 요소|없음|  
  
## <a name="remarks"></a>주의  
 **값** 요소는 부모 개체와 연결 된 값을 포함 합니다. 예상 값은 **값** 다음 표에 설명 된 대로 요소는 부모 요소에 따라 달라 집니다.  
  
|부모 요소|필요한 값|  
|--------------------|--------------------|  
|[AlgorithmParameter](../../../analysis-services/scripting/objects/algorithmparameter-element-assl.md)|알고리즘 매개 변수 값|  
|[주석](../../../analysis-services/scripting/objects/annotation-element-assl.md)|주석 값|  
|[Kpi](../../../analysis-services/scripting/objects/kpi-element-assl.md)|KPI(핵심 성과 지표) 값을 계산하는 데 사용되는 MDX(Multidimensional Expressions) 식|  
|[ReportFormatParameter](../../../analysis-services/scripting/objects/reportformatparameter-element-asl.md)|보고서 형식 매개 변수 값|  
|[ReportParameter](../../../analysis-services/scripting/objects/reportparameter-element-assl.md)|보고서 매개 변수 값을 계산하는 데 사용되는 식|  
|[ServerProperty](../../../analysis-services/scripting/objects/serverproperty-element-assl.md)|현재 실행 중인 인스턴스의 서버 속성 값|  
  
 부모에 해당 하는 요소 **값** Analysis Management Objects (AMO) 개체 모델은 <xref:Microsoft.AnalysisServices.AlgorithmParameter>, <xref:Microsoft.AnalysisServices.Annotation>, <xref:Microsoft.AnalysisServices.Kpi>, <xref:Microsoft.AnalysisServices.ReportParameter>, 및 <xref:Microsoft.AnalysisServices.ServerProperty>합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [속성 &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  