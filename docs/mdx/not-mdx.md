---
title: "없습니다 (MDX) | Microsoft Docs"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- NOT
dev_langs:
- kbMDX
helpviewer_keywords:
- NOT operator [MDX]
ms.assetid: c11bd3b0-54b3-4a6d-babc-6067722194db
caps.latest.revision: 26
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: b6da446a370065c3782ac3c76445988d266b60d7
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="not-mdx"></a>NOT(MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  숫자 식에 논리 부정을 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
NOT Expression1  
```  
  
#### <a name="parameters"></a>매개 변수  
 *Expression1*  
 숫자 값을 반환하는 유효한 MDX 식입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 하는 부울 값 **false** 으로 계산 되는 인수 **true**, 그렇지 않으면 **true**합니다.  
  
## <a name="remarks"></a>주의  
 **하지** 연산자는 부울 값으로 식을 처리 (0, 0,으로 **false**, 그렇지 않으면 **true**) 연산자가 논리 부정을 수행 하기 전에. 다음 표에서 설명 방법을 **하지** 연산자가 논리 부정을 수행 합니다.  
  
|*Expression1*|반환 값|  
|-------------------|------------------|  
|**true**|**false**|  
|**false**|**true**|  
  
## <a name="see-also"></a>관련 항목:  
 [MDX 연산자 참조 &#40; Mdx&#41;](../mdx/mdx-operator-reference-mdx.md)  
  
  
