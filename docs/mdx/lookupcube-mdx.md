---
title: LookupCube (MDX) | Microsoft Docs
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
- LOOKUPCUBE
dev_langs:
- kbMDX
helpviewer_keywords:
- LookupCube function
ms.assetid: 243fa101-328a-4016-86e0-d8b5977e15a9
caps.latest.revision: 32
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 41aed2def9e470d39f006b314f51dbb61bf63b47
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="lookupcube-mdx"></a>LookupCube(MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  같은 데이터베이스에서 지정된 또 다른 큐브에 대해 계산된 MDX 식의 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Numeric expression syntax  
LookupCube(Cube_Name, Numeric_Expression )  
  
String expression syntax  
LookupCube(Cube_Name, String_Expression )  
```  
  
## <a name="arguments"></a>인수  
 *Cube_Name*  
 큐브의 이름을 지정하는 유효한 문자열 식입니다.  
  
 *Numeric_Expression*  
 숫자를 반환하는 셀 좌표의 유효한 숫자 식으로서, 일반적으로 MDX 식입니다.  
  
 *String_Expression*  
 문자열을 반환하는 셀 좌표의 유효한 문자열 식으로서, 일반적으로 유효한 MDX 식입니다.  
  
## <a name="remarks"></a>주의  
 숫자 식이 지정 되는 **LookupCube** 함수는 지정 된 큐브의 특정된 숫자 식을 계산 하 고 결과 숫자 값을 반환 합니다.  
  
 문자열 식이 지정 되는 **LookupCube** 함수는 지정 된 큐브의 특정된 문자열 식을 계산 하 고 결과 문자열 값을 반환 합니다.  
  
 **LookupCube** 기반이 MDX를 쿼리 하는 원본 큐브에 포함 되어 있는 동일한 데이터베이스 내의 큐브에서 작동 하는 함수는 **LookupCube** 함수가 실행 되 고 있습니다.  
  
> [!IMPORTANT]  
>  현재 쿼리의 컨텍스트는 쿼리되는 큐브에는 적용되지 않으므로 숫자 또는 문자열 식에 필요한 현재 멤버를 모두 지정해야 합니다.  
  
 사용 하 여 모든 계산의 **LookupCube** 함수는 성능이 저하 될 가능성이 있습니다. 이 함수를 사용하는 대신 필요한 모든 데이터가 하나의 큐브에 있도록 솔루션을 다시 설계하는 것이 좋습니다.  
  
## <a name="examples"></a>예  
 다음 쿼리에서는 LookupCube를 사용하는 방법을 보여 줍니다.  
  
 `WITH MEMBER MEASURES.LOOKUPCUBEDEMO AS`  
  
 `LOOKUPCUBE("Adventure Works", "[Measures].[In" + "ternet Sales Amount]")`  
  
 `SELECT MEASURES.LOOKUPCUBEDEMO  ON 0`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>관련 항목:  
 [MDX 함수 참조 &#40; Mdx&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
