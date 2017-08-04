---
title: "단항 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- kbMDX
helpviewer_keywords:
- unary operators
ms.assetid: bf1b5518-6040-4484-9ce8-79c0eb4373a9
caps.latest.revision: 27
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 5b5aea52fb028a9c1d5345e60d4bfa400ecaa735
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="unary-operators"></a>단항 연산자
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  MDX의 단항 연산자는 숫자 식의 음수 값 또는 양수 값을 반환하는 등의 단일 피연산자에 대한 연산을 수행합니다.  
  
 다음 표에서는 MDX가 지원하는 단항 연산자를 나열합니다.  
  
|연산자|Description|  
|--------------|-----------------|  
|[-(음수)](../mdx/negative-mdx.md)|숫자 식의 음수 값을 반환합니다.|  
|[+ (양수)](../mdx/positive-mdx.md)|숫자 식의 양수 값을 반환합니다.|  
  
 다음 예에서는 음수 측정 값을 반환하는 단항 연산자의 사용 방법을 설명합니다.  
  
```  
WITH   
   MEMBER [Measures].[NegDiscountAmount] AS  
   -[Measures].[Discount Amount]  
SELECT   
   {[Measures].[Discount Amount],[Measures].[NegDiscountAmount]} on COLUMNS,  
   NON EMPTY [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
WHERE [Product].[Category].[Bikes]  
```  
  
 또한 MDX가 특수 한 단항 연산자를 사용 하 여 수행한 집계 작업을 확인 하는 [RollupChildren](../mdx/rollupchildren-mdx.md) 함수입니다. 이러한 특수 한 단항 연산자에 대 한 자세한 내용은 참조 하십시오. [차원에 사용자 지정 집계 추가](../analysis-services/multidimensional-models/bi-wizard-add-a-custom-aggregation-to-a-dimension.md)합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [연산자 &#40; MDX 구문 &#41;](../mdx/operators-mdx-syntax.md)  
  
  
