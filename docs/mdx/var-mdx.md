---
title: Var (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 14caf6e96b41fdf2e7f8b4d20f16852e890bd166
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34743922"
---
# <a name="var-mdx"></a>Var(MDX)


  비편향된 모집단 수식을 사용 하 여 집합에 대해 계산 된 숫자 식의 표본 분산을 반환 합니다 (으로 나누는 *n*).  
  
## <a name="syntax"></a>구문  
  
```  
  
Var(Set_Expression [ ,Numeric_Expression ] )  
```  
  
## <a name="arguments"></a>인수  
 *Set_Expression*  
 집합을 반환하는 유효한 MDX 식입니다.  
  
 *Numeric_Expression*  
 숫자를 반환하는 셀 좌표의 유효한 숫자 식으로서, 일반적으로 MDX 식입니다.  
  
## <a name="remarks"></a>Remarks  
 **Var** 함수는 지정 된 집합에 대해 계산 된 지정 된 숫자 식의 비편향된 분산을 반환 합니다.  
  
 **Var** 함수는 비편향된 모집단 수식을 사용 및 [VarP](../mdx/varp-mdx.md) 함수는 편향된 모집단 수식을 사용 합니다.  
  
## <a name="see-also"></a>관련 항목  
 [MDX 함수 참조 &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
