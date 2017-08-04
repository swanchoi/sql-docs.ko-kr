---
title: Unorder (MDX) | Microsoft Docs
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
- UNORDER
dev_langs:
- kbMDX
helpviewer_keywords:
- Unorder function
ms.assetid: a805df2a-6320-45bc-989f-90e85faf027f
caps.latest.revision: 36
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 9b5ed088bc1dd8203e7bdcb13d763dccb75eb49a
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="unorder-mdx"></a>Unorder(MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  지정한 집합에서 강제 적용된 순서를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Unorder(Set_Expression)   
```  
  
## <a name="arguments"></a>인수  
 *Set_Expression*  
 집합을 반환하는 유효한 MDX 식입니다.  
  
## <a name="remarks"></a>주의  
 **Unorder** 함수 제거와 같은 다른 함수 또는 문에 의해 집합에 포함 되는 튜플에 적용 된 순서는 [순서](../mdx/order-mdx.md) 함수입니다. 반환 된 집합의 튜플 순서는 **Unorder** 함수는 결정적이 지 않습니다.  
  
 **Unorder** 함수를 사용 하는 힌트를으로 [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] 집합 처리에 대 한 쿼리 최적화에 대 한 합니다. 집합 내의 튜플 순서가 계산 이나 쿼리에 중요 한를 사용 하 여는 **Unorder** 함수에는 이러한 경우에는 성능상의 이점을 제공할 수 있습니다. 예를 들어는 [NonEmpty (MDX)](../mdx/nonempty-mdx.md) 함수 성능이 좋아질 수 있습니다이 함수에 제공 된 집합은 보다 정렬 하지 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] 있지만, 순서를 보존 해야와 [!INCLUDE[ssASCurrent](../includes/ssascurrent-md.md)], 쿼리 프로세서에서이 함수의 자동으로 수행 하려고 많은 함수에 대해 같은 **Sum** 및 **집계**합니다. 성능 이점은 **Unorder** 는 수백만 개의 튜플로 구성 된 매우 큰 집합 뚜렷하게 나타날 수만 있습니다.  
  
## <a name="example"></a>예제  
 다음 의사 코드에서는 이 함수에 대한 구문을 보여 줍니다.  
  
```  
NonEmpty (UnOrder (<set_expression>))  
```  
  
## <a name="see-also"></a>참고 항목  
 [MDX 함수 참조 &#40; Mdx&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
