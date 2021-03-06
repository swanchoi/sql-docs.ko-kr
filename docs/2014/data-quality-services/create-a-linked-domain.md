---
title: 연결된 도메인 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.linkeddomain.f1
ms.assetid: fd99d422-c53d-4d7c-9cdd-303c703683b6
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 800326d3255180087cb7603435e2d0e1a8c8e029
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2019
ms.locfileid: "56033654"
---
# <a name="create-a-linked-domain"></a>연결된 도메인 만들기
  이 항목에서는 DQS( [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] )의 기술 자료에서 연결된 도메인을 만드는 방법에 대해 설명합니다. 이전의 다른 기존 도메인에서 연결된 도메인을 만들고 해당 도메인의 모든 값, 규칙 및 속성을 상속(이름 및 설명 제외)할 수 있습니다. 연결된 도메인 집합을 하나로 관리할 수 있습니다. 하나의 도메인을 다른 도메인에 연결하여 다른 도메인의 콘텐츠를 상속하는 도메인을 만들 수 있습니다.  
  
## <a name="scenarios"></a>시나리오  
 연결된 도메인은 다음 시나리오에서 특히 유용합니다.  
  
### <a name="mapping-multiple-fields-to-domains-that-share-values-rules-and-properties"></a>값, 규칙 및 속성을 공유하는 도메인에 여러 필드 매핑  
 두 필드를 같은 도메인에 매핑할 수 없지만 하나의 필드를 도메인에 매핑한 다음 두 번째 필드를 첫 번째 도메인과 연결된 도메인에 매핑할 수 있습니다. 이러한 방식으로 이름 및 설명을 제외하고 콘텐츠 및 속성이 같은 두 개의 서로 다른 도메인에 필드를 매핑할 수 있습니다 자세한 내용은 [Map two fields to linked domains](#Map)을 참조하세요.  
  
### <a name="controlling-data-flow-to-composite-domains"></a>복합 도메인에 대한 데이터 흐름 제어  
 연결된 도메인을 사용하여 필드와 복합 도메인 간의 데이터 흐름을 제어할 수 있습니다. 한 필드의 데이터가 복합 도메인으로 이동하는 시점과 유사한 다른 필드의 데이터가 복합 도메인으로 이동하지 않는 시점을 차별화할 수 있습니다. 이 작업을 수행하려면 연결된 두 도메인 중 하나만 복합 도메인의 일부로 지정하면 됩니다. 도메인 뷰에서는 연결된 도메인이 서로 동일합니다. 즉, 연결된 도메인에는 같은 정보가 포함되어 있습니다. 그러나 복합 도메인 뷰에서는 연결된 도메인이 서로 다릅니다. 한 도메인은 복합 도메인에 참여하지만 다른 도메인은 그렇지 않습니다.  
  
 예를 들어 고객 이름, 고객 성 및 아버지의 이름입니다. 고객 이름과 아버지의 이름을 둘 다 이름 도메인에 매핑하고 이름 도메인과 성 도메인을 전체 이름 복합 도메인의 일부로 지정한 경우를 가정해 보겠습니다. 이 경우의 문제는 아버지의 이름이 성 없이 복합 도메인에 추가된다는 점입니다. 그러나 두 이름 필드를 각각 서로 다른 도메인에 연결하고 두 도메인을 연결한 경우 고객 이름 도메인은 전체 복합 도메인에 추가하고 아버지의 이름 필드는 복합 도메인에 추가하지 않을 수 있습니다. 이렇게 하면 아버지의 이름이 복합 도메인에 추가되지 않습니다.  
  
##  <a name="BeforeYouBegin"></a> 시작하기 전에  
  
###  <a name="Prerequisites"></a> 필수 구성 요소  
 연결된 도메인을 만들려면 연결할 기존 도메인과 기술 자료가 있어야 합니다.  
  
###  <a name="Security"></a> 보안  
  
####  <a name="Permissions"></a> Permissions  
 연결된 도메인을 만들려면 DQS_MAIN 데이터베이스에 대한 dqs_kb_editor 또는 dqs_administrator 역할이 있어야 합니다.  
  
##  <a name="Create"></a> 연결된 도메인 만들기  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)] [Data Quality Client 응용 프로그램을 실행합니다](../../2014/data-quality-services/run-the-data-quality-client-application.md).  
  
2.  [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] 홈 화면에서 기술 자료를 열거나 만듭니다. **도메인 관리** 를 작업으로 선택한 다음 **열기** 또는 **만들기**를 클릭합니다. 자세한 내용은 [기술 자료 만들기](../../2014/data-quality-services/create-a-knowledge-base.md) 또는 [기술 자료 열기](../../2014/data-quality-services/open-a-knowledge-base.md)를 참조하세요.  
  
3.  **도메인 관리** 페이지의 **도메인 목록** 에서 새 도메인을 연결할 도메인을 마우스 오른쪽 단추로 클릭한 다음 **연결된 도메인 만들기**를 클릭합니다.  
  
    > [!NOTE]  
    >  연결된 도메인을 만드는 데에만 사용되는 아이콘은 없습니다. 이 작업을 수행하려면 상황에 맞는 메뉴의 명령을 사용해야 합니다.  
  
4.  **도메인 만들기** 대화 상자에서 기술 자료에 고유한 이름과 설명(최대 256자)을 입력합니다. 연결된 도메인 이름이 올바른지 확인합니다.  
  
5.  **확인** 을 클릭하여 연결된 도메인 만들기를 완료합니다.  
  
6.  필요한 경우 도메인 속성 탭에서 연결된 도메인의 이름 또는 설명을 변경할 수 있습니다.  
  
7.  **마침** 을 클릭하여 [도메인 관리 작업 종료](../../2014/data-quality-services/end-the-domain-management-activity.md)에 설명된 대로 도메인 관리 작업을 완료합니다.  
  
##  <a name="Map"></a> Map two fields to linked domains  
  
1.  기술 자료 검색 작업에 대한 기술 자료를 열어 데이터베이스와 테이블 또는 뷰에 매핑합니다.  
  
2.  필드 하나를 도메인에 매핑한 다음 두 번째 필드를 같은 도메인에 매핑합니다.  
  
3.  도메인이 이미 사용 중임을 나타내는 팝업이 표시되면 예를 클릭하여 연결된 도메인을 만듭니다.  
  
4.  도메인 만들기 대화 상자에서 도메인 이름과 설명을 입력한 다음 확인을 클릭합니다.  
  
##  <a name="FollowUp"></a> 후속 작업: 연결된 도메인을 만든 후  
 연결된 도메인을 만든 후 도메인에 대해 다른 도메인 관리 태스크를 수행하거나, 기술 자료 검색을 수행하여 도메인에 정보를 추가하거나, 도메인에 일치 정책을 추가할 수 있습니다. 자세한 내용은 [기술 자료 검색 수행](../../2014/data-quality-services/perform-knowledge-discovery.md), [도메인 관리](../../2014/data-quality-services/managing-a-domain.md) 또는 [일치 정책 만들기](../../2014/data-quality-services/create-a-matching-policy.md)를 참조하세요.  
  
##  <a name="Behavior"></a> 연결된 도메인의 동작  
 연결된 도메인에 대한 설정을 다음과 같이 변경할 수 있습니다.  
  
-   연결된 도메인의 이름 및 설명을 변경할 수 있습니다.  
  
-   **데이터 형식**, **선행 값 사용**또는 **출력 형식** 속성에 대한 도메인 속성을 변경하려면 연결한 도메인을 선택하고 해당 도메인에 대한 **도메인 속성** 탭에서 이러한 설정을 변경합니다. 연결된 도메인의 속성에서는 이러한 설정을 변경할 수 없습니다. 자세한 내용은 [도메인 만들기](../../2014/data-quality-services/create-a-domain.md)을 참조하세요.  
  
-   도메인 관리 페이지의 **참조 데이터**, **도메인 규칙**, **도메인 값**및 **용어 기반 관계** 탭에 있는 설정은 연결된 도메인 또는 연결된 대상 도메인에 대해 변경할 수 있으며 이러한 변경 내용은 다른 도메인에 상속됩니다.  
  
 연결된 도메인에는 다음과 같은 특성이 있습니다.  
  
-   두 도메인의 연결을 해제할 수 없습니다. 연결을 제거하려면 연결된 도메인 중 하나를 삭제해야 합니다.  
  
-   도메인 관리 페이지의 도메인 목록에서 연결된 도메인을 선택하면 **값** 테이블이 있는 창에서 연결된 도메인을 나타내는 문자열에 해당 도메인이 연결된 도메인임을 나타내는 표시가 포함됩니다.  
  
-   다른 도메인이 연결되어 있는 도메인을 삭제하면 두 도메인이 모두 삭제됩니다. 그러나 연결된 도메인을 삭제한 경우에는 연결된 대상 도메인은 삭제되지 않습니다.  
  
-   연결된 도메인은 자체가 다른 도메인에 연결되어 있는 도메인에 연결할 수 없습니다.  
  
-   복합 도메인에 대한 연결된 도메인 또는 연결된 복합 도메인을 만들 수 없습니다.  
  
-   도메인 관리 탭 중 하나에서 연결된 도메인을 두 번 클릭하면 도메인이 편집할 수 있도록 열리고 이름 문자열에 해당 도메인이 연결된 도메인임을 알리는 표시가 나타납니다.  
  
  
