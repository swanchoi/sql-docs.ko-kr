---
title: "SQL Server 2016 서비스 업데이트 설치 | Microsoft Docs"
ms.custom:
- SQL2016_New_Updated
ms.date: 08/31/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- setup-install
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d6c962b-c8d0-49f7-a2ac-00ad8dca930a
caps.latest.revision: 13
author: MikeRayMSFT
ms.author: mikeray
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: c0e1316d3444a08aaf114de18d1b7d9f5450aa9f
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="install-sql-server-servicing-updates"></a>SQL Server 서비스 업데이트 설치
  이 항목에서는 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]용 업데이트 설치에 대한 정보를 제공합니다. 이 섹션에서는 다음과 같은 정보를 제공합니다.  
  
-   새로 설치하는 동안 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 용 업데이트 설치  
  
-   설치 후 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 용 업데이트 설치.  
  
 시스템이 최신 보안 업데이트로 업데이트되도록 고객이 적절한 시기에 최신 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 업데이트를 확인하고 설치하는 것이 좋습니다.  
  
## <a name="installing-updates-for-includesscurrentincludessscurrent-mdmd-during-a-new-installation"></a>새로 설치하는 동안 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 용 업데이트 설치  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 설치 프로그램에서 최신 제품 업데이트를 주 제품 설치와 통합하여 주 제품과 해당 업데이트가 동시에 설치되게 할 수 있습니다. 제품 업데이트는 다음 위치에서 적용 가능한 업데이트를 검색할 수 있습니다.  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)] Update  
  
-   WSUS(Windows Server Update Services)  
  
-   로컬 폴더  
  
-   네트워크 공유  
  
 설치 프로그램에서 최신 버전의 적용 가능한 업데이트를 찾으면 이를 다운로드하고 현재의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 설치 프로세스와 통합합니다. 제품 업데이트에는 누적 업데이트, 서비스 팩 또는 서비스 팩과 누적 업데이트가 포함될 수 있습니다.  
  
## <a name="installing-updates-for-includesscurrentincludessscurrent-mdmd-after-it-has-already-been-installed"></a>설치 후 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 용 업데이트 설치  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]인스턴스가 설치된 경우 GDR(General Distribution Release), SP(서비스 팩) 및 CU(누적 업데이트)를 포함한 최신 보안 업데이트와 중요 업데이트를 적용하는 것이 좋습니다. 자세한 내용은 [2016년 3월에 발표한 SQL Server ISM(증분 서비스 모델)](http://blogs.msdn.microsoft.com/sqlreleaseservices/announcing-updates-to-the-sql-server-incremental-servicing-model-ism/)을 참조하세요. 
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 업데이트는 MU( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Update), WSUS(Windows Server Update Services) 및 Microsoft 다운로드 센터를 통해 제공됩니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 용 보안 및 중요 업데이트는 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Update를 통해 제공되며 이러한 업데이트를 보려면 제어판의 Windows Update 애플릿을 통해 MU를 선택해야 합니다.  
  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Update를 통해 업데이트를 받으면 무인 모드에서 모든 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 기능을 최신 버전으로 업데이트합니다. 더 많은 유연성이 필요하거나 인터넷 또는 WSUS 액세스가 없을 경우 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Download Center에서 업데이트를 얻어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [설치 마법사에서 SQL Server 2016 설치&#40;설치 프로그램&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md)   
 [SQL Server 2016 인스턴스에 기능 추가&#40;설치 프로그램&#41;](../../database-engine/install-windows/add-features-to-an-instance-of-sql-server-2016-setup.md)   
 [실패한 SQL Server 2016 설치 복구](../../database-engine/install-windows/repair-a-failed-sql-server-installation.md)  
  
  
