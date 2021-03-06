---
title: NonEmpty (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 91e6d478397cf9fa77a6ca33748b5a4515034471
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34742302"
---
# <a name="nonempty-mdx"></a>NonEmpty(MDX)


  지정된 집합과 두 번째 집합의 교차곱을 기준으로, 지정된 집합에서 비어 있지 않은 튜플의 집합을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
NONEMPTY(set_expression1 [,set_expression2])  
```  
  
## <a name="arguments"></a>인수  
 *set_expression1*  
 집합을 반환하는 유효한 MDX 식입니다.  
  
 *set_expression2*  
 집합을 반환하는 유효한 MDX 식입니다.  
  
## <a name="remarks"></a>Remarks  
 이 함수는 지정된 첫 번째 집합의 튜플 중 두 번째 집합의 튜플에 대해 계산될 때 비어 있지 않은 튜플을 반환합니다. **NonEmpty** 계산 함수는 사용 및 중복 튜플을 유지 합니다. 두 번째 집합이 지정되지 않은 경우 이 식은 큐브의 특성 계층 멤버와 측정값의 현재 좌표 컨텍스트에서 계산됩니다.  
  
> [!NOTE]  
>  대신이 함수는 사용 되지 않는 사용 하 여 [NonEmptyCrossjoin &#40;MDX&#41; ](../mdx/nonemptycrossjoin-mdx.md) 함수입니다.  
  
> [!IMPORTANT]  
>  비어 있지 않음 특성은 튜플 자체가 아니라 튜플에서 참조하는 셀의 특성입니다.  
  
## <a name="examples"></a>예  
 다음 쿼리는 간단한 예를 보여 줍니다. **NonEmpty**, null이 아닌 값이 1 일 2001 년 7 월 Internet Sales Amount에 대 한 포함 하는 모든 고객을 반환 합니다.  
  
 `SELECT [Measures].[Internet Sales Amount] ON 0,`  
  
 `NONEMPTY(`  
  
 `[Customer].[Customer].[Customer].MEMBERS`  
  
 `, {([Date].[Calendar].[Date].&[20010701], [Measures].[Internet Sales Amount])}`  
  
 `)`  
  
 `ON 1`  
  
 `FROM [Adventure Works]`  
  
 고객과 사용 하 여 구입 날짜가 들어 있는 튜플 집합을 반환 하는 다음 예제는 **필터** 함수 및 **NonEmpty** 마지막 날짜를 찾고 각 고객이 제품을 구매 하는 함수:  
  
 `WITH SET MYROWS AS FILTER`  
  
 `(NONEMPTY`  
  
 `([Customer].[Customer Geography].[Customer].MEMBERS`  
  
 `* [Date].[Date].[Date].MEMBERS`  
  
 `, [Measures].[Internet Sales Amount]`  
  
 `) AS MYSET`  
  
 `, NOT(MYSET.CURRENT.ITEM(0)`  
  
 `IS MYSET.ITEM(RANK(MYSET.CURRENT, MYSET)).ITEM(0))`  
  
 `)`  
  
 `SELECT [Measures].[Internet Sales Amount] ON 0,`  
  
 `MYROWS ON 1`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>관련 항목  
 [DefaultMember &#40;MDX&#41;](../mdx/defaultmember-mdx.md)   
 [필터 &#40;MDX&#41;](../mdx/filter-mdx.md)   
 [IsEmpty &#40;MDX&#41;](../mdx/isempty-mdx.md)   
 [MDX 함수 참조 &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)   
 [NonEmptyCrossjoin &#40;MDX&#41;](../mdx/nonemptycrossjoin-mdx.md)  
  
  
