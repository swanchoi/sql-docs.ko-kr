---
title: Qtd (MDX) | Microsoft Docs
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
- QTD
dev_langs:
- kbMDX
helpviewer_keywords:
- Qtd function
ms.assetid: c1fe47e0-9c2b-466f-8d6d-e2b1c16a69cb
caps.latest.revision: 30
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: d4fcbfa3ac5c02dc04181bb32c8baca10a56fa0e
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="qtd-mdx"></a>Qtd(MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  첫 번째 형제 항목부터 지정 된 멤버에서 끝나며 하 여 제한 된 지정된 된 멤버와 같은 수준에서 멤버의 형제 집합을 반환 된 *분기* 시간 차원의 수준입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Qtd( [ Member_Expression ] )  
```  
  
## <a name="arguments"></a>인수  
 *Member_Expression*  
 멤버를 반환하는 유효한 MDX 식입니다.  
  
## <a name="remarks"></a>주의  
 경우 지정 되지 않은 멤버 expressionis, 기본값은 있으며 수준 유형이 인 첫 번째 계층의 현재 멤버 *분기* 유형의 첫 번째 차원에 *시간* 측정값 그룹에 있습니다.  
  
 **Qtd** 함수에 대 한 바로 가기 함수는는 [PeriodsToDate &#40; Mdx&#41; ](../mdx/periodstodate-mdx.md) 함수는 수준 식 인수가 설정은 *분기*합니다. 즉, `Qtd(Member_Expression)`은 `PeriodsToDate(Quarter_Level_Expression, Member_Expression)`과 동일합니다.  
  
## <a name="example"></a>예제  
 합계를 반환 하는 다음 예제는 `Measures.[Order Quantity]` 멤버에 포함 된 2003 년 3 분기의 첫 2 개월에 걸쳐 집계는 `Date` 차원에서는 **Adventure Works** 큐브.  
  
```  
WITH MEMBER [Date].[Calendar].[First2MonthsSecondSemester2003] AS  
    Aggregate(  
        QTD([Date].[Calendar].[Month].[August 2003])  
    )  
SELECT   
    [Date].[Calendar].[First2MonthsSecondSemester2003] ON COLUMNS,  
    [Product].[Category].Children ON ROWS  
FROM  
    [Adventure Works]  
WHERE  
    [Measures].[Order Quantity]  
```  
  
## <a name="see-also"></a>참고 항목  
 [MDX 함수 참조 &#40; Mdx&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
