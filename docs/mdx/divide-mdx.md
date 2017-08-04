---
title: "나누기 (MDX) | Microsoft Docs"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 9fe4a47b-d5e8-4dc7-ad4a-3e47ab463f03
caps.latest.revision: 5
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 2f05c20a10b72b3c919672fd528a4222c6d204d7
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="divide-mdx"></a>나누기(MDX)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  나누기를 수행하고 0으로 나누기에 대한 대체 결과 또는 BLANK()를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Divide (<numerator>, <denominator> [,<alternateresult>])  
```  
  
## <a name="arguments"></a>인수  
 *분자*  
 피제수 또는 나누어지는 숫자입니다.  
  
 *분모*  
 제수 또는 나눌 숫자입니다.  
  
 *alternateresult*  
 (선택 사항) 0으로 나누면 오류가 발생하는 경우 반환되는 값입니다. 제공되지 않으면 기본값은 BLANK()입니다.  
  
## <a name="remarks"></a>주의  
 0으로 나누기의 대체 결과는 상수여야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MDX 함수 참조 &#40; Mdx&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
