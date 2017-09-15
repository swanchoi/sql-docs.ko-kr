---
title: "부모 속성 (ADO MD) | Microsoft Docs"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- Parent
- Member::Parent
helpviewer_keywords:
- Parent property [ADO MD]
ms.assetid: 32c278c1-d8e1-4bb7-9ecd-2fbfdffee34b
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: baee402a130847f732583db8de376c120acb1bfb
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="parent-property-ado-md"></a>ADO MD parent 속성
현재 부모 멤버를 나타냅니다 [멤버](../../../ado/reference/ado-md-api/member-object-ado-md.md) 계층에 있습니다.  
  
## <a name="return-values"></a>반환 값  
 반환 된 [멤버](../../../ado/reference/ado-md-api/member-object-ado-md.md) 개체를 읽기 전용입니다.  
  
## <a name="remarks"></a>주의  
 (루트) 계층의 최상위 수준에 있는 구성원에 부모가 없습니다. 이 속성은의 경우에 지원 **멤버** 에 속하는 개체는 [수준](../../../ado/reference/ado-md-api/level-object-ado-md.md) 개체입니다. 이 속성에서 참조 되는 동안 오류가 발생 **멤버** 에 속하는 개체는 [위치](../../../ado/reference/ado-md-api/position-object-ado-md.md) 개체입니다.  
  
## <a name="applies-to"></a>적용 대상  
 [Member 개체(ADO MD)](../../../ado/reference/ado-md-api/member-object-ado-md.md)  
  
## <a name="see-also"></a>관련 항목:  
 [Children 속성(ADO MD)](../../../ado/reference/ado-md-api/children-property-ado-md.md)