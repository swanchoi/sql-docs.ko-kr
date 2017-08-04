---
title: StdevP (MDX) | Microsoft Docs
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
- STDEVP
dev_langs:
- kbMDX
helpviewer_keywords:
- StdevP function [MDX]
ms.assetid: cd8ae7c9-3cef-49f0-bb41-8f577c7b6f31
caps.latest.revision: 30
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: d72eb148aafccc60aa5097c8c7fed7f8b842a583
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="stdevp-mdx"></a>StdevP(MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  편향된 모집단 수식을 사용 하 여 집합에 대해 계산 된 숫자 식의 모집단 표준 편차를 반환 합니다 (으로 나누는  *n* ).  
  
## <a name="syntax"></a>구문  
  
```  
  
StdevP(Set_Expression [ ,Numeric_Expression ] )  
```  
  
## <a name="arguments"></a>인수  
 *Set_Expression*  
 집합을 반환하는 유효한 MDX 식입니다.  
  
 *Numeric_Expression*  
 숫자를 반환하는 셀 좌표의 유효한 숫자 식으로서, 일반적으로 MDX 식입니다.  
  
## <a name="remarks"></a>주의  
 **StdevP** 함수는 편향된 모집단을 사용 하는 동안 수식는 [Stdev](../mdx/stdev-mdx.md) 함수는 비편향된 모집단 수식을 사용 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 편향 모집단 수식을 사용하여 2003년의 처음 3개월 동안 집합된 Internet Order Quantity의 표준 편차를 반환합니다.  
  
```  
WITH MEMBER Measures.x AS   
   StdevP   
   ( { [Date].[Calendar].[Month].[January 2003],  
       [Date].[Calendar].[Month].[February 2003],  
       [Date].[Calendar].[Month].[March 2003]},  
    [Measures].[Internet Order Quantity])  
SELECT Measures.x ON 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>참고 항목  
 [MDX 함수 참조 &#40; Mdx&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
