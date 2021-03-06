---
title: 일부 동기 복제본이 동기화되지 않음 | Microsoft Docs
ms.custom: ''
ms.date: 05/17/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql13.swb.agdashboard.agp5synchronized.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: e58ed56e-4c30-42e6-a9fc-a8c401620e02
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 7c1fb484897fbfc75736dfc78cb5b6da078a91df
ms.sourcegitcommit: 63b4f62c13ccdc2c097570fe8ed07263b4dc4df0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2018
ms.locfileid: "51602323"
---
# <a name="some-synchronous-replicas-are-not-synchronized"></a>일부 동기 복제본이 동기화되지 않음
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
## <a name="introduction"></a>소개  
  
|||  
|-|-|  
|**정책 이름**|동기 복제본 데이터 동기화 상태|  
|**문제점**|일부 동기 복제본이 동기화되지 않았습니다.|  
|**범주**|**경고**|  
|**패싯**|가용성 그룹|  
  
## <a name="description"></a>설명  
 이 정책은 모든 가용성 복제본의 데이터 동기화 상태를 롤업하여 예상되는 동기화 상태가 아닌 가용성 복제본이 있는지 확인합니다. SYNCHRONIZING 상태가 아닌 비동기 복제본이 있거나 SYNCHRONIZED 상태가 아닌 동기 복제본이 있으면 정책은 비정상 상태에 있습니다. 그렇지 않으면 정책은 정상 상태입니다.  
  
> [!NOTE]  
>  이 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]릴리스의 경우 가능한 원인 및 해결 방법에 대한 자세한 내용은 TechNet Wiki의 [일부 동기 복제본이 동기화되지 않음](https://go.microsoft.com/fwlink/p/?LinkId=220853) 을 참조하세요.  
  
## <a name="possible-causes"></a>가능한 원인  
 이 가용성 그룹에서 하나 이상의 동기 복제본이 현재 동기화되지 않았습니다. 복제본 동기화 상태는 SYNCHRONIZING 또는 NOT SYNCHRONIZING일 수 있습니다.  
  
## <a name="possible-solution"></a>가능한 해결 방법  
 가용성 복제본 정책 상태를 사용하여 잘못된 동기화 상태의 가용성 복제본을 찾은 다음 가용성 복제본에서 문제를 해결합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Always On 가용성 그룹 개요&#40;SQL Server&#41;](../../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [Always On 대시보드 사용&#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
