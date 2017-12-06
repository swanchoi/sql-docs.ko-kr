---
title: "백업 및 AP PDW에 대 한 하드웨어 개요 로드"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.prod: sql-non-specified
ms.prod_service: mpp-data-warehouse
ms.service: 
ms.component: analytics-platform-system
ms.suite: sql
ms.custom: 
ms.technology: mpp-data-warehouse
description: "종단 간 데이터 웨어하우징 솔루션 Analytics Platform System (APS)와 SQL Server 병렬 데이터 웨어하우스 (PDW)를 배포 하려면 데이터 웨어하우스를 백업 하 고 데이터를 로드 하기 위한 계획을 만들어야 할 수 있습니다."
ms.date: 10/20/2016
ms.topic: article
ms.assetid: 3a2ae046-f8d8-4a5c-b3c1-6ecee005df6c
caps.latest.revision: "9"
ms.openlocfilehash: 0bdf529aacf1644f55cd44da3d0a7590e509a323
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="backup-and-loading-hardware-overview"></a>백업 및 하드웨어 개요를 로드 합니다.
종단 간 데이터 웨어하우징 솔루션 Analytics Platform System (APS)와 SQL Server 병렬 데이터 웨어하우스 (PDW)를 배포 하려면 데이터 웨어하우스를 백업 하 고 데이터를 로드 하기 위한 계획을 만들어야 할 수 있습니다. 이 가이드를 사용 하 여를 확보 하 고 비즈니스 요구 사항을 충족 하는 백업 하 고 로드할 서버를 구성 합니다.  
  
## <a name="acquire-and-configure-backup-servers"></a>획득 하 고 백업 서버를 구성 합니다.  
![백업 프로세스](media/backup-process.png "프로세스를 백업 합니다.")  
  
PDW 데이터베이스를 백업 하려면 하나 이상의 서버를 백업 해야 합니다. 기존 하드웨어를 사용 하거나 새 하드웨어를 구입할 수 있습니다. 자세한 내용은 참조 [를 획득 하 고 백업 서버를 구성](acquire-and-configure-backup-server.md)합니다. 이러한 지침에는 한 [서버 용량 계획 워크시트 백업](backup-capacity-planning-worksheet.md) 백업에 대 한 적합 한 솔루션을 계획할 수 있도록 합니다.  
  
## <a name="acquire-and-configure-loading-servers"></a>획득 하 고 서버를 로드를 구성 합니다.  
![로드 프로세스](media/loading-process.png "로드 프로세스")  
  
데이터를 로드 하려면 하나 이상의 서버를 로드 해야 합니다. 사용자 고유의 기존 ETL 또는 다른 서버를 사용할 수 있습니다 또는 새 서버를 구매할 수 있습니다. 자세한 내용은 참조 [Acquire 로드 서버를 구성 하 고](acquire-and-configure-loading-server.md)합니다. 이러한 지침에는 한 [서버 용량 계획 워크시트 로드](loading-server-capacity-planning-worksheet.md) 로드에 대 한 적합 한 솔루션을 계획할 수 있도록 합니다.  
  
## <a name="see-also"></a>관련 항목:  
[백업 및 복원 개요](backup-and-restore-overview.md)  
[부하 개요](load-overview.md)  
  