---
title: 정보 및 복제 모니터를 사용 하 여 수행할 작업 보기 | Microsoft Docs
ms.custom: ''
ms.date: 11/29/2018
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- viewing publication information
- publications [SQL Server replication], viewing information
- publications [SQL Server replication], Replication Monitor tasks
ms.assetid: 92e28a07-d6a7-461b-a0b3-bd9bc6afcbe5
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 400db44d053caf131ef13947adbd0154875995cf
ms.sourcegitcommit: 7aa6beaaf64daf01b0e98e6c63cc22906a77ed04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54136378"
---
# <a name="view-information-and-perform-tasks-using-replication-monitor"></a>정보 보기 및 복제 모니터를 사용 하 여 작업 수행
복제 모니터에는 다양 한 탭 및 정보 보기 및 다양 한 작업을 수행 하는 옵션을 제공 합니다. 이 문서에서는 보고 복제 모니터를 사용 하는 경우 작업을 수행할 수 있는 다른 작업을 설명 합니다.

## <a name="for-a-publication"></a>게시에 대 한

### <a name="view-information"></a>정보 보기

  복제 모니터에는 선택한 게시에 대한 정보를 포함하는 다음과 같은 탭이 있습니다.  
  
-   **모든 구독** -이 탭은 선택한 게시에 모든 구독에 대 한 정보를 표시 합니다.  
  
-   **에이전트** -이 탭에는 게시에 의해 사용 되는 모든 에이전트에 대 한 정보가 표시 됩니다.  
  
    -   스냅숏 에이전트 - 모든 게시에서 사용    
    -   로그 판독기 에이전트 - 모든 트랜잭션 게시에서 사용    
    -   큐 판독기 에이전트 - 지연 업데이트 구독이 있는 트랜잭션 게시에서 사용  
  
-   **경고** ( [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] 이상을 실행하는 배포자의 경우)   
    -   이 탭에서는 에이전트에 대한 경고를 지정할 수 있습니다.  
  
-   **추적 프로그램 토큰** ( [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] 이상을 실행하는 배포자에 대한 트랜잭션 복제에만 있음)  
  
     이 탭에서는 대기 시간(게시자에서 커밋될 트랜잭션과 구독자에서 상응하는 커밋될 트랜잭션 사이에 경과된 시간)을 측정할 수 있습니다.  
  
 각 탭의 옵션에 대한 자세한 내용을 보려면 오른쪽 창에서 해당 탭을 클릭한 다음 메뉴 모음에서 **도움말** 을 클릭합니다. 복제 모니터를 시작하는 방법은 [복제 모니터 시작](start-the-replication-monitor.md)을 참조하세요.  
  
### <a name="perform-tasks"></a>작업 수행
  
1.  왼쪽 창에서 게시자 그룹을 확장하고 해당 게시자를 확장한 다음 해당 게시를 클릭합니다.    
2.  게시 속성을 보고 수정하려면 해당 게시를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.    
3.  구독에 대한 정보를 보려면 **모든 구독** 탭을 클릭합니다.  
  
     구독 속성을 보고 수정하려면 해당 구독을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다. 이 탭에서 보다 자세한 정보에 액세스하고 태스크를 수행할 수도 있습니다. 자세한 내용은 [정보 보기 및 태스크 수행 복제 모니터를 사용 하 여](view-information-and-perform-tasks-replication-monitor.md)입니다.  
  
4.  에이전트에 대한 정보를 보려면 **에이전트** 탭을 클릭합니다. 이 탭에서 보다 자세한 정보에 액세스하고 태스크를 수행할 수도 있습니다. 자세한 내용은 [정보 보기 및 태스크 수행 복제 모니터를 사용 하 여](view-information-and-perform-tasks-replication-monitor.md)입니다.    
5.  에이전트 경고 및 임계값에 대한 정보를 보려면 **경고** 탭을 클릭합니다. 자세한 내용은 [Set Thresholds and Warnings in Replication Monitor](set-thresholds-and-warnings-in-replication-monitor.md)을 참조하세요.   
6.  추적 프로그램 토큰에 대한 정보를 보려면 **추적 프로그램 토큰** 탭을 클릭합니다. 추적 프로그램 토큰 사용 방법은 [트랜잭션 복제에 대한 대기 시간 측정 및 연결 유효성 검사](measure-latency-and-validate-connections-for-transactional-replication.md)를 참조하십시오.  
  
## <a name="for-a-publisher"></a>게시자에 대 한
  복제 모니터는 선택한 게시자에 대한 정보를 표시하는 다음 탭을 제공합니다.  
  
-   **게시** -이 탭에는 선택한 게시자에서 모든 게시에 대 한 정보 표시 됩니다.  
  
-   **구독 조사 목록** -오류, 경고 또는 경고가 발생 하거나 성능이 선택한 게시자에서 사용 가능한 모든 게시의 구독에 대 한 정보를 표시 하려면이 탭 됩니다.  [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]이전 버전을 실행하는 배포자의 경우 이 탭이 표시되지 않습니다.  
  
-   **에이전트** 탭-이 탭 에이전트 및 사용 되는 작업에 대 한 자세한 내용은 모든 유형의 복제 하 여 표시 합니다. 이 탭에서는 각 에이전트 및 작업을 시작하고 중지할 수 있습니다.  
  
 각 탭의 옵션에 대한 자세한 내용을 보려면 오른쪽 창에서 해당 탭을 클릭한 다음 메뉴 모음에서 **도움말** 을 클릭합니다. 복제 모니터를 시작하는 방법은 [복제 모니터 시작](start-the-replication-monitor.md)을 참조하세요.  
  
### <a name="view-information-and-perform-tasks"></a>정보 보기 및 작업 수행
  
1.  왼쪽 창에서 게시자 그룹을 확장한 다음 해당 게시자를 클릭합니다.    
2.  모든 게시에 대한 정보를 보려면 **게시** 탭을 클릭합니다.    
3.  구독에 대한 정보를 보려면 **구독 조사 목록** 탭을 클릭합니다. 다음과 같이 이 탭에서 자세한 정보에 액세스하고 태스크를 수행할 수도 있습니다.    
    -   구독과 연결된 에이전트에 대한 자세한 내용을 보려면 해당 구독을 마우스 오른쪽 단추로 클릭한 다음 **자세히 보기**를 클릭합니다.    
    -   구독 속성을 보려면 해당 구독을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.    
    -   밀어넣기 구독을 동기화하려면 해당 구독을 마우스 오른쪽 단추로 클릭한 다음 **동기화 시작**을 클릭합니다.    
    -   구독을 다시 초기화하려면 해당 구독을 마우스 오른쪽 단추로 클릭한 다음 **구독 다시 초기화**를 클릭합니다.   
4.  에이전트에 대한 정보를 보려면 **에이전트** 탭을 클릭합니다. 이 탭에서 다음과 같이 보다 자세한 정보에 액세스하고 태스크를 수행할 수도 있습니다.    
    -   에이전트에 대한 자세한 정보(예: 정보 메시지 및 오류 메시지)를 보려면 에이전트를 마우스 오른쪽 단추로 클릭한 다음 **자세히 보기**를 클릭합니다.    
    -   에이전트를 실행하는 작업에 대한 자세한 정보(예: 일정, 자세한 작업 단계 정보 등)를 보려면 에이전트를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.    
    -   에이전트에 대한 프로필을 관리하려면 에이전트를 마우스 오른쪽 단추로 클릭한 다음 **에이전트 프로필**을 클릭합니다. 자세한 내용은 [복제 에이전트 프로필 작업](../agents/replication-agent-profiles.md)을 참조하세요.    
    -   실행 중이지 않은 에이전트를 시작하려면 에이전트를 마우스 오른쪽 단추로 클릭한 다음 **에이전트 시작**을 클릭합니다.    
    -   실행 중인 에이전트를 중지하려면 에이전트를 마우스 오른쪽 단추로 클릭한 다음 **에이전트 중지**를 클릭합니다.  
  
## <a name="for-a-subscription"></a>에 대 한 구독 

  복제 모니터는 구독에 대한 정보가 들어 있는 다음 탭을 제공합니다.  
  
-   **모든 구독** -이 탭은 선택한 게시에 모든 구독에 대 한 정보를 표시 합니다.  
  
-   **구독 조사 목록** -오류, 경고 또는 경고가 발생 하거나 성능이 선택한 게시자에서 사용 가능한 모든 게시의 구독에 대 한 정보를 표시 하려면이 탭 됩니다.  [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]이전 버전을 실행하는 배포자의 경우 이 탭이 표시되지 않습니다.  
  
 각 탭의 옵션에 대한 자세한 내용을 보려면 오른쪽 창에서 해당 탭을 클릭한 다음 메뉴 모음에서 **도움말** 을 클릭합니다. 복제 모니터를 시작하는 방법은 [복제 모니터 시작](start-the-replication-monitor.md)을 참조하세요.  
  
### <a name="all-subscriptions-tab"></a>모든 구독 탭  
  
1.  왼쪽 창에서 게시자 그룹을 확장하고 해당 게시자를 확장한 다음 해당 게시를 클릭합니다.   
2.  구독에 대한 정보를 보려면 **모든 구독** 탭을 클릭합니다. '동기화 중'과 같은 특정 상태에 있는 구독만 보려면 **표시** 드롭다운 목록에서 옵션을 선택합니다.   
3.  구독 속성을 보고 수정하려면 해당 구독을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다. 이 탭에서 보다 자세한 정보에 액세스하고 태스크를 수행할 수도 있습니다. 자세한 내용은 [정보 보기 및 태스크 수행 복제 모니터를 사용 하 여](view-information-and-perform-tasks-replication-monitor.md)입니다.  
  
### <a name="subscription-watch-list-tab"></a>구독 조사 목록 탭  
  
1.  왼쪽 창에서 게시자 그룹을 확장한 다음 해당 게시자를 클릭합니다.   
2.  구독에 대한 정보를 보려면 **구독 조사 목록** 탭을 클릭합니다.  
3.  **\<SubscriptionType> 구독 표시** 드롭다운 목록에서 표시할 구독 유형을 선택합니다. '동기화 중'과 같은 특정 상태에 있는 구독만 보려면 **표시** 드롭다운 목록에서 옵션을 선택합니다.    
4.  구독 속성을 보고 수정하려면 해당 구독을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다. 이 탭에서 보다 자세한 정보에 액세스하고 태스크를 수행할 수도 있습니다. 자세한 내용은 [정보 보기 및 태스크 수행 복제 모니터를 사용 하 여](view-information-and-perform-tasks-replication-monitor.md)입니다.  

## <a name="for-publication-agents"></a>게시 에이전트에 대 한

  복제 모니터에는 선택한 게시와 연결된 에이전트에 대한 정보가 포함된 **에이전트** 탭이 있습니다. 배포 에이전트 및 병합 에이전트는 구독을 사용 하 여 연결 자세한 내용은 [정보 보기 및 태스크 수행 복제 모니터를 사용 하 여](view-information-and-perform-tasks-replication-monitor.md)입니다.  
  
 이 탭에는 다음 에이전트에 대한 정보가 표시됩니다.    
-   스냅숏 에이전트 - 모든 게시에서 사용    
-   로그 판독기 에이전트 - 모든 트랜잭션 게시에서 사용    
-   큐 판독기 에이전트 - 지연 업데이트 구독이 활성화된 트랜잭션 게시에서 사용  
  
 이 탭의 옵션에 대한 자세한 내용을 보려면 메뉴 모음의 **도움말** 을 클릭하세요. 복제 모니터를 시작하는 방법은 [복제 모니터 시작](start-the-replication-monitor.md)을 참조하세요.  
  
### <a name="view-information-and-perform-tasks"></a>정보 보기 및 작업 수행 
  
1.  왼쪽 창에서 게시자 그룹을 확장하고 해당 게시자를 확장한 다음 해당 게시를 클릭합니다.    
2.  **에이전트** 탭을 클릭하여 에이전트에 대한 정보를 봅니다. 이 탭에서 다음과 같이 보다 자세한 정보에 액세스하고 태스크를 수행할 수도 있습니다.  
  
    -   에이전트에 대한 자세한 정보(예: 정보 메시지 및 오류 메시지)를 보려면 에이전트를 마우스 오른쪽 단추로 클릭한 다음 **자세히 보기**를 클릭합니다.    
    -   에이전트를 실행하는 작업에 대한 자세한 정보(예: 일정, 자세한 작업 단계 정보 등)를 보려면 에이전트를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.    
    -   에이전트에 대한 프로필을 관리하려면 에이전트를 마우스 오른쪽 단추로 클릭한 다음 **에이전트 프로필**을 클릭합니다. 자세한 내용은 [복제 에이전트 프로필 작업](../agents/replication-agent-profiles.md)을 참조하세요.  
    -   실행 중이지 않은 에이전트를 시작하려면 에이전트를 마우스 오른쪽 단추로 클릭한 다음 **에이전트 시작**을 클릭합니다.  
      -   실행 중인 에이전트를 중지하려면 에이전트를 마우스 오른쪽 단추로 클릭한 다음 **에이전트 중지**를 클릭합니다.  

## <a name="for-subscription-agents"></a>구독 에이전트에 대 한

### <a name="view-information-and-perform-tasks"></a>정보 보기 및 태스크 수행
  복제 모니터에서는 구독과 연결된 에이전트 정보에 액세스할 수 있는 두 가지 탭을 제공합니다.  
  
-   **모든 구독** -이 탭은 선택한 게시에 모든 구독에 대 한 정보를 표시 합니다.  
  
-   **구독 조사 목록** -오류, 경고 또는 경고가 발생 하거나 성능이 선택한 게시자에서 사용 가능한 모든 게시의 구독에 대 한 정보를 표시 하려면이 탭 됩니다.  [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]이전 버전을 실행하는 배포자의 경우 이 탭이 표시되지 않습니다.  
  
 각 탭의 옵션에 대한 자세한 내용을 보려면 오른쪽 창에서 해당 탭을 클릭한 다음 메뉴 모음에서 **도움말** 을 클릭합니다. 복제 모니터를 시작하는 방법은 [복제 모니터 시작](start-the-replication-monitor.md)을 참조하세요.  
  
### <a name="view-information-and-perform-tasks"></a>정보 보기 및 작업 수행 
  
1.  왼쪽 창에서 게시자 그룹을 확장하고 해당 게시자를 확장한 다음 해당 게시를 클릭합니다.   
2.  **모든 구독** 탭을 클릭하여 구독에 대한 정보를 봅니다. 이 탭에서 다음과 같이 보다 자세한 정보에 액세스하고 태스크를 수행할 수도 있습니다.  
  
    -   구독과 연결된 에이전트에 대한 자세한 내용을 보려면 해당 구독을 마우스 오른쪽 단추로 클릭한 다음 **자세히 보기**를 클릭합니다. 자세한 정보에는 에이전트 기록과 오류 메시지, 트랜잭션 복제에 대한 성능 통계 및 병합 복제에 대한 아티클 수준의 동기화 통계가 포함됩니다.    
         시작된 세부 정보 창의 탭은 구독 유형에 따라 다릅니다. 스냅숏 구독의 경우 **배포자에서 구독자로의 연결 기록**탭이고, 트랜잭션 구독의 경우 **게시자에서 배포자로의 연결 기록**탭, **배포자에서 구독자로의 연결 기록**탭 및 **배포되지 않은 명령**탭이고, 병합 구독의 경우 **동기화 기록**탭입니다.    
    -   밀어넣기 구독을 동기화하려면 해당 구독을 마우스 오른쪽 단추로 클릭한 다음 **동기화 시작**을 클릭합니다.    
    -   구독을 다시 초기화하려면 해당 구독을 마우스 오른쪽 단추로 클릭한 다음 **구독 다시 초기화**를 클릭합니다.    
    -   단일 병합 구독의 유효성을 검사하려면 구독을 마우스 오른쪽 단추로 클릭한 다음 **구독 유효성 검사**를 클릭합니다. 병합 게시에 대한 모든 구독의 유효성을 검사하려면 해당 게시를 마우스 오른쪽 단추로 클릭한 다음 **모든 구독 유효성 검사**를 클릭합니다. 트랜잭션 게시에 대한 모든 구독의 유효성을 검사하려면 해당 게시를 마우스 오른쪽 단추로 클릭한 다음 **구독 유효성 검사**를 클릭합니다.    
    -   에이전트에 대한 프로필을 관리하려면 에이전트를 마우스 오른쪽 단추로 클릭한 다음 **에이전트 프로필**을 클릭합니다. 자세한 내용은 [복제 에이전트 프로필 작업](../agents/replication-agent-profiles.md)을 참조하세요.  
  
### <a name="view-information-and-perform-tasks"></a>정보 보기 및 작업 수행
  
1.  왼쪽 창에서 게시자 그룹을 확장한 다음 해당 게시자를 클릭합니다.   
2.  **구독 조사 목록** 탭을 클릭하여 구독에 대한 정보를 봅니다. 이 탭에서 다음과 같이 보다 자세한 정보에 액세스하고 태스크를 수행할 수도 있습니다.    
    -   구독과 연결된 에이전트에 대한 자세한 내용을 보려면 해당 구독을 마우스 오른쪽 단추로 클릭한 다음 **자세히 보기**를 클릭합니다. 자세한 정보에는 에이전트 기록과 오류 메시지, 트랜잭션 복제에 대한 성능 통계 및 병합 복제에 대한 아티클 수준의 동기화 통계가 포함됩니다.    
         시작된 세부 정보 창의 탭은 구독 유형에 따라 다릅니다. 스냅숏 구독의 경우 **배포자에서 구독자로의 연결 기록**탭이고, 트랜잭션 구독의 경우 **게시자에서 배포자로의 연결 기록**탭, **배포자에서 구독자로의 연결 기록**탭 및 **성능**탭이고, 병합 구독의 경우 **동기화 기록**탭입니다.    
    -   밀어넣기 구독을 동기화하려면 해당 구독을 마우스 오른쪽 단추로 클릭한 다음 **동기화 시작**을 클릭합니다.    
    -   구독을 다시 초기화하려면 해당 구독을 마우스 오른쪽 단추로 클릭한 다음 **구독 다시 초기화**를 클릭합니다.    
    -   단일 병합 구독의 유효성을 검사하려면 구독을 마우스 오른쪽 단추로 클릭한 다음 **구독 유효성 검사**를 클릭합니다. 병합 게시에 대한 모든 구독의 유효성을 검사하려면 해당 게시를 마우스 오른쪽 단추로 클릭한 다음 **모든 구독 유효성 검사**를 클릭합니다. 트랜잭션 게시에 대한 모든 구독의 유효성을 검사하려면 해당 게시를 마우스 오른쪽 단추로 클릭한 다음 **구독 유효성 검사**를 클릭합니다.    
    -   에이전트에 대한 프로필을 관리하려면 에이전트를 마우스 오른쪽 단추로 클릭한 다음 **에이전트 프로필**을 클릭합니다. 자세한 내용은 [복제 에이전트 프로필 작업](../agents/replication-agent-profiles.md)을 참조하세요.  
  

## <a name="see-also"></a>관련 항목  
 [게시 속성 보기 및 수정](../publish/view-and-modify-publication-properties.md)   
 [복제 모니터링](../monitoring-replication.md)  
  