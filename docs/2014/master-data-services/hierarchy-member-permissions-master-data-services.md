---
title: 계층 멤버 권한(Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- members [Master Data Services], permissions
- permissions [Master Data Services], members
ms.assetid: b3880eed-1bf6-4f65-ab23-b08c194cc858
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: a7e762a450a28f1d07e58a0baa6f7f3ff3948681
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52797045"
---
# <a name="hierarchy-member-permissions-master-data-services"></a>계층 멤버 권한(Master Data Services)
  계층 멤버 권한은 선택 사항이며 사용자에게 특정 멤버에 대한 제한된 액세스 권한을 부여하려는 경우에만 사용해야 합니다. **계층 멤버** 탭에서 아무 권한도 할당하지 않을 경우 사용자의 권한은 전적으로 **모델** 탭에서 할당한 권한을 기반으로 합니다.  
  
 계층 멤버 권한은 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] UI(사용자 인터페이스)의 **계층 멤버** 탭에 있는 **사용자 및 그룹 권한** 기능 영역에서 할당됩니다. 이러한 사용 권한은 사용자가 UI의 **탐색기** 기능 영역에서 액세스할 수 있는 멤버를 결정합니다.  
  
 **계층 멤버** 탭에서 각 계층은 트리 구조로 표시됩니다. 트리의 노드에 사용 권한을 할당하면 하위 수준에서 권한이 명시적으로 할당된 경우를 제외하고 모든 자식이 해당 권한을 상속합니다.  
  
> [!NOTE]  
>  계층의 노드에 사용 권한을 할당하면 같은 수준 이상의 다른 모든 노드에 있는 모든 멤버는 암시적으로 거부됩니다.  
  
 **탐색기**에서는 멤버가 표시되는 모든 곳에 멤버 권한이 적용됩니다. 예를 들어, 멤버 **읽기 전용** 속한 하 모든 엔터티, 계층 및 컬렉션에서 읽기 전용 권한입니다.  
  
 계층 멤버 권한은 할당 대상 모델 버전과 해당 버전의 모든 이후 복사본에 적용되며, 할당 대상 버전보다 이전 버전에는 적용되지 않습니다.  
  
|사용 권한|Description|  
|----------------|-----------------|  
|**읽기 전용**|멤버가 표시되지만 사용자가 멤버를 변경할 수 없습니다. 또한 사용자는 멤버가 속한 모든 명시적 계층이나 컬렉션에서 멤버를 이동할 수도 없습니다.<br /><br /> 참고: 할당 하는 경우 **읽기 전용** 권한을 **루트**, 아래의 멤버 **루트** 는 읽기 전용입니다; 단, 명시적 계층 및 컬렉션에서 이동할 수 멤버 **루트** 새 멤버를 추가할 수 있습니다 **루트**입니다.|  
|**Update**|멤버가 표시되며 사용자가 멤버를 변경할 수 있습니다. 또한 사용자는 멤버가 속한 모든 명시적 계층이나 컬렉션에서 멤버를 이동할 수도 있습니다.|  
|**거부**|멤버가 표시되지 않습니다.|  
  
 **계층 멤버** 탭에서 할당하는 사용 권한은 즉시 적용되지 않습니다. 사용 권한이 적용되는 주기는 **데이터베이스의 시스템 설정 테이블에 지정된** 멤버 보안 처리 간격 설정 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 에 따라 다릅니다. [멤버 권한 즉시 적용&#40;Master Data Services&#41;](immediately-apply-member-permissions-master-data-services.md)의 단계를 수행하여 멤버 권한을 즉시 적용할 수 있습니다.  
  
> [!NOTE]  
>  재귀 계층, 명시적 캡이 포함된 파생 계층 및 숨겨진 수준이 있는 파생 계층에는 계층 멤버 권한을 할당할 수 없습니다.  
  
## <a name="possible-overlapping-permissions"></a>겹칠 수 있는 사용 권한  
 멤버에 사용 권한을 할당할 때 겹치는 사용 권한을 확인해야 할 수 있습니다.  
  
### <a name="when-a-member-belongs-to-multiple-hierarchies"></a>멤버가 여러 계층에 속한 경우  
 둘 이상의 계층이 같은 멤버를 포함할 수 있습니다.  
  
-   한 계층 노드에 할당 되 면 **업데이트** 권한과 다른 할당 된 **읽기 전용**, 노드의 멤버 권한은 **읽기 전용**합니다.  
  
-   한 계층 노드에 할당 되 면 **업데이트** 또는 **읽기 전용** 권한과 다른 노드에 할당 됩니다 **거부**, 다음 노드의 멤버가 표시 되지 않습니다.  
  
## <a name="see-also"></a>관련 항목:  
 [계층 멤버 권한 할당&#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)   
 [사용 권한이 결정되는 방식&#40;Master Data Services&#41;](../../2014/master-data-services/how-permissions-are-determined-master-data-services.md)   
 [멤버&#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md)   
 [계층&#40;Master Data Services&#41;](../../2014/master-data-services/hierarchies-master-data-services.md)   
 [멤버 권한 즉시 적용&#40;Master Data Services&#41;](immediately-apply-member-permissions-master-data-services.md)  
  
  
