---
title: "Aliases 요소 (ASSL) | Microsoft Docs"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- Aliases Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- Aliases
helpviewer_keywords:
- Aliases element
ms.assetid: 9de9e683-d30d-4d61-b32d-c5a946825742
caps.latest.revision: 35
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: a2c0b1eb29df31046b0cb8175be382af50a920a3
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="aliases-element-assl"></a>Aliases 요소(ASSL)
  컬렉션을 포함 [별칭](../../../analysis-services/scripting/properties/alias-element-assl.md) 와 관련 된 요소는 [계정](../../../analysis-services/scripting/objects/account-element-assl.md) 요소  
  
## <a name="syntax"></a>구문  
  
```xml  
  
<Account>  
      ...  
   <Aliases>  
      <Alias>...</Alias>  
      </Aliases>  
      ...  
</Account>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특징|설명|  
|--------------------|-----------------|  
|데이터 형식 및 길이|없음(컬렉션)|  
|기본값|없음(컬렉션)|  
|카디널리티|0-1: 한 번만 나타날 수 있는 선택적 요소입니다.|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|-------------|  
|부모 요소|[계정](../../../analysis-services/scripting/objects/account-element-assl.md)|  
|자식 요소|[별칭](../../../analysis-services/scripting/properties/alias-element-assl.md)|  
  
## <a name="remarks"></a>주의  
 부모에 해당 하는 요소 **별칭** Analysis Management Objects (AMO) 개체 모델은 <xref:Microsoft.AnalysisServices.Account>합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [Accounts 요소 &#40; ASSL &#41;](../../../analysis-services/scripting/collections/accounts-element-assl.md)   
 [Database 요소 &#40; ASSL &#41;](../../../analysis-services/scripting/objects/database-element-assl.md)   
 [컬렉션 &#40; ASSL &#41;](../../../analysis-services/scripting/collections/collections-assl.md)  
  
  