---
title: "개체 요소 (차원) (XMLA) | Microsoft Docs"
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
- Object Element (Dimension)
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#Object
- urn:schemas-microsoft-com:xml-analysis#Object
- microsoft.xml.analysis.object
helpviewer_keywords:
- Object element
ms.assetid: db7feb39-7cc1-4b54-8979-77ce402ef71f
caps.latest.revision: 11
author: jeannt
ms.author: jeannt
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 9d66d84632079ce1cb0d27d505086896ad36f571
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="object-element-dimension-xmla"></a>Object 요소(차원)(XMLA)
  차원에 대 한 개체 참조가 포함 부모 [삽입](../../../analysis-services/xmla/xml-elements-commands/insert-element-xmla.md), [업데이트](../../../analysis-services/xmla/xml-elements-commands/update-element-xmla.md), 또는 [Drop](../../../analysis-services/xmla/xml-elements-commands/drop-element-xmla.md) 명령을 실행 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<Insert> <!-- or any of the parent elements in the Element Relationships table -->  
...  
   <Object>  
      <Database>...</Database>  
      <Cube>...</Cube>  
      <Dimension>...</Dimension>  
   </Object>  
...  
</Insert>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특징|설명|  
|--------------------|-----------------|  
|데이터 형식 및 길이|없음|  
|기본값|없음|  
|카디널리티|1-1: 한 번만 나타나는 필수 요소입니다.|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|-------------|  
|부모 요소|[Drop](../../../analysis-services/xmla/xml-elements-commands/drop-element-xmla.md), [삽입](../../../analysis-services/xmla/xml-elements-commands/insert-element-xmla.md), [업데이트](../../../analysis-services/xmla/xml-elements-commands/update-element-xmla.md)|  
|자식 요소|[큐브](../../../analysis-services/xmla/xml-elements-properties/cube-element-xmla.md), [데이터베이스](../../../analysis-services/xmla/xml-elements-properties/database-element-xmla.md), [차원](../../../analysis-services/xmla/xml-elements-properties/dimension-element-xmla.md)|  
  
## <a name="remarks"></a>주의  
  
## <a name="see-also"></a>관련 항목:  
 [속성 &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  