---
title: "CubePermission 요소 (ASSL) | Microsoft Docs"
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
- CubePermission Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- CubePermission
helpviewer_keywords:
- CubePermission element
ms.assetid: b144b623-ff20-4ead-91ad-4c718f3b140b
caps.latest.revision: 36
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 6db733a91b405ef5eed6a6dd5a5a7f977aa33266
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="cubepermission-element-assl"></a>CubePermission 요소(ASSL)
  특정 멤버의 사용 권한을 정의 [역할](../../../analysis-services/scripting/objects/role-element-assl.md) 요소의 특정 [큐브](../../../analysis-services/scripting/objects/cube-element-assl.md) 요소입니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<CubePermissions>  
   <CubePermission>  
      <!-- The following elements extend Permission -->  
      <ReadSourceData>...</ReadSourceData>  
            <DimensionPermissions>...</DimensionPermissions>  
            <CellPermissions>...</CellPermissions>  
   </CubePermission>  
</CubePermissions>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특징|설명|  
|--------------------|-----------------|  
|데이터 형식 및 길이|[사용 권한](../../../analysis-services/scripting/data-type/permission-data-type-assl.md)|  
|기본값|없음|  
|카디널리티|0-n: 한 번 이상 나타날 수 있는 선택적 요소입니다.|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|-------------|  
|부모 요소|[CubePermissions](../../../analysis-services/scripting/collections/cubepermissions-element-assl.md)|  
|자식 요소|[CellPermissions](../../../analysis-services/scripting/collections/cellpermissions-element-assl.md), [DimensionPermissions](../../../analysis-services/scripting/collections/dimensionpermissions-element-assl.md), [ReadSourceData](../../../analysis-services/scripting/properties/readsourcedata-element-assl.md)|  
  
## <a name="remarks"></a>주의  
 Analysis Management Objects (AMO) 개체 모델의 해당 요소는 <xref:Microsoft.AnalysisServices.CubePermission>합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [Cube 요소 &#40; ASSL &#41;](../../../analysis-services/scripting/objects/cube-element-assl.md)   
 [개체 &#40; ASSL &#41;](../../../analysis-services/scripting/objects/objects-assl.md)  
  
  