---
title: 엔터티 권한(Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- entities [Master Data Services], permissions
- permissions [Master Data Services], entities
ms.assetid: 22785062-4faf-46ee-bffa-01cbd6d5a5b3
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 7945561aa40e6d62841bfda9cfc74792e7d7813c
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52813395"
---
# <a name="entity-permissions-master-data-services"></a>엔터티 권한(Master Data Services)
  엔터티 권한은 다음에 적용됩니다.  
  
-   리프 멤버 및 통합 멤버 둘 다의 **이름** 및 **코드**를 포함하여 엔터티의 모든 특성  
  
-   엔터티의 모든 컬렉션  
  
-   명시적 계층 멤버 자격 및 관계  
  
 엔터티에 대한 사용 권한이 있는 경우 해당 엔터티, 명시적 계층 및 컬렉션에서 멤버를 추가하거나 제거할 수 있습니다.  
  
> [!NOTE]  
>  이러한 사용 권한은 사용자 인터페이스의 **탐색기** 기능 영역에만 적용됩니다.  
  
|사용 권한|Description|  
|----------------|-----------------|  
|**읽기 전용**|엔터티가 표시되지만 사용자가 멤버를 추가, 제거 또는 변경할 수 없습니다.|  
|**Update**|엔터티가 표시되고 사용자가 멤버를 추가, 제거 및 변경할 수 있습니다.|  
|**거부**|엔터티가 표시되지 않습니다.|  
  
## <a name="see-also"></a>관련 항목  
 [모델 개체 사용 권한 할당&#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md)   
 [모델 개체 권한&#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md)   
 [엔터티&#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md)  
  
  
