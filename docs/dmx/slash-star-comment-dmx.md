---
title: "슬래시 (/ / 주석) (DMX) 별 | Microsoft Docs"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- DMX
helpviewer_keywords:
- commenting characters
- forward slash-asterisk character pairs
- /*...*/ (comment)
ms.assetid: 163976cc-aa47-4eda-bd98-03c1a397f80e
caps.latest.revision: 15
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 5bfaadd08f5a9aba145c754f281cf1d2c8e38496
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="slash-star-comment-dmx"></a>슬래시 별 (주석) (DMX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]에서 실행되지 않는 텍스트 문자열을 나타냅니다. 주석 문자 사이 오는 텍스트는 계산 되지 않습니다 / * 및 \*/ 합니다. 주석을 DMX(Data Mining Extensions) 문 안에 중첩하거나 코드 줄 끝에 포함하거나 별도의 줄에 삽입할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
/* Comment_Text */  
```  
  
#### <a name="parameters"></a>매개 변수  
 *Comment_Text*  
 주석 텍스트를 포함하는 문자열입니다.  
  
## <a name="remarks"></a>주의  
 여러 줄로 이루어진 주석은로 표시 되어야 합니다 / * 및 \*/ 합니다.  
  
 주석의 길이에는 제한이 없습니다.  
  
 DMX에서 다른 종류의 주석 사용 하는 방법에 대 한 자세한 내용은 참조 [의견 &#40; DMX &#41;](../dmx/comments-dmx.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [이중 슬래시 &#40; 설명 &#41; &#40; DMX &#41;](../dmx/double-slash-comment-dmx.md)   
 [-&#40; 설명 &#41; &#40; DMX &#41; 요약](../dmx/comment-dmx-summary.md)   
 [Data Mining Extensions &#40; DMX &#41; 연산자 참조](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [연산자 &#40; DMX &#41;](../dmx/operators-dmx.md)  
  
  
