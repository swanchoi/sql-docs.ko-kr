---
title: "ForeignKeyColumn 요소 (ASSL) | Microsoft Docs"
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
- ForeignKeyColumn Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- ForeignKeyColumn
helpviewer_keywords:
- ForeignKeyColumn element
ms.assetid: 6c00dcc6-8d5b-4293-8b72-c7a22e298c8d
caps.latest.revision: 38
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: cc3000d1bdab66434e4cc8134567da46f87f0544
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="foreignkeycolumn-element-assl"></a>ForeignKeyColumn 요소(ASSL)
  관계형 데이터 원본에 대한 부모 테이블로의 조인을 식별합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<ForeignKeyColumns>  
   <ForeignKeyColumn xsi:type="DataItem">...</ForeignKeyColumn>  
</ForeignKeyColumns>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특징|설명|  
|--------------------|-----------------|  
|데이터 형식 및 길이|[DataItem](../../../analysis-services/scripting/data-type/dataitem-data-type-assl.md)|  
|기본값|없음|  
|카디널리티|0-n: 두 번 이상 나타날 수 있는 선택적 요소입니다.|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|-------------|  
|부모 요소|[ForeignKeyColumns](../../../analysis-services/scripting/collections/foreignkeycolumns-element-assl.md)|  
|자식 요소|없음|  
  
## <a name="remarks"></a>주의  
 에 대 한 자세한 내용은 **DataItem** 테이블의 Analysis Services Scripting Language (ASSL) 개체 및 속성을 포함 하 여는 **DataItem** 입력을 참조 하십시오. [DataItem 데이터 Type&#40; ASSL &#41; ](../../../analysis-services/scripting/data-type/dataitem-data-type-assl.md).  
  
 부모에 해당 하는 요소는 **ForeignKeyColumns** Analysis Management Objects (AMO) 개체 모델에서 컬렉션은 <xref:Microsoft.AnalysisServices.TableMiningStructureColumn>합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [TableMiningStructureColumn 데이터 형식 &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/tableminingstructurecolumn-data-type-assl.md)   
 [MiningStructureColumn 데이터 형식 &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/miningstructurecolumn-data-type-assl.md)   
 [MiningStructure 요소 &#40; ASSL &#41;](../../../analysis-services/scripting/objects/miningstructure-element-assl.md)   
 [개체 &#40; ASSL &#41;](../../../analysis-services/scripting/objects/objects-assl.md)  
  
  