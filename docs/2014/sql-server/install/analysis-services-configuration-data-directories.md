---
title: Analysis Services 구성-데이터 디렉터리 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
ms.assetid: ef732855-b7af-4f40-a619-5573c1c354bb
author: heidisteen
ms.author: heidist
manager: craigg
ms.openlocfilehash: f01bec92621022c875ff43c479356df1a35b8157
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48147683"
---
# <a name="analysis-services-configuration---data-directories"></a>Analysis Services 구성 - 데이터 디렉터리
  다음 표의 기본 디렉터리는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 설치 중에 사용자가 구성할 수 있습니다. 이러한 파일에 대한 액세스 권한은 설치 중에 만들어져 프로비전되는 SQLServerMSASUser$\<instance> 보안 그룹의 멤버와 로컬 관리자에게 부여됩니다.  
  
## <a name="uielement-list"></a>UIElement 목록  
  
|Description|기본 디렉터리|권장 사항|  
|-----------------|-----------------------|---------------------|  
|데이터 루트 디렉터리|C:\Program Files\Microsoft SQL Server\MSAS12 합니다. \<InstanceID > \OLAP\Data\|\Program files\Microsoft SQL Server\ 폴더가 제한 된 권한으로 보호 되어 있는지 확인 합니다. [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 성능은 대부분의 구성에서 데이터 디렉터리가 있는 저장소의 성능에 따라 달라집니다. 이 디렉터리는 시스템에 연결된 성능이 가장 높은 스토리지에 두십시오. 장애 조치(Failover) 클러스터 설치의 경우 공유 디스크에 데이터 디렉터리를 만들어야 합니다.|  
|로그 파일 디렉터리|C:\Program Files\Microsoft SQL Server\MSAS12 합니다. \<InstanceID > \OLAP\Log\|에 대 한 디렉터리 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 로그 파일인 이며 FlightRecorder 로그를 포함 합니다. 비행 레코더 기간을 늘려야 하는 경우 로그 디렉터리에 적절한 공간이 있는지 확인하십시오.|  
|임시 디렉터리|C:\Program Files\Microsoft SQL Server\MSAS12 합니다. \<InstanceID > \OLAP\Temp\|고성능 저장소 하위 시스템에 Temp 디렉터리를 배치 합니다.|  
|백업 디렉터리|C:\Program Files\Microsoft SQL Server\MSAS12 합니다. \<InstanceID > \OLAP\Backup\|에 대 한 디렉터리 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 기본 백업 파일입니다. SharePoint용 PowerPivot 설치 시에는 PowerPivot 시스템 서비스에서 PowerPivot 데이터 파일도 캐시합니다.<br /><br /> 데이터 손실을 방지할 수 있도록 적절한 권한을 설정하고 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 서비스를 위한 사용자 그룹에 백업 디렉터리에 대한 적절한 쓰기 권한이 있는지 확인하십시오. 백업 디렉터리에는 매핑된 드라이브를 사용할 수 없습니다.|  
  
## <a name="notes"></a>참고  
  
-   SharePoint 팜에 배포된 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 인스턴스는 응용 프로그램 파일, 데이터 파일 및 속성을 콘텐츠 데이터베이스와 서비스 응용 프로그램 데이터베이스에 저장합니다.  
  
-   기존 설치에 기능을 추가할 경우 이전에 설치한 기능의 위치를 변경하거나 새 기능의 위치를 지정할 수 없습니다.  
  
-   기본이 아닌 설치 디렉터리를 지정하는 경우 설치 폴더가 이 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]인스턴스에 대해 고유한지 확인해야 합니다. 이 대화 상자의 어떠한 디렉터리도 다른 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]인스턴스의 디렉터리와 공유되지 않아야 합니다. [!INCLUDE[ssDE](../../includes/ssde-md.md)] 인스턴스 내의 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 및 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 구성 요소도 별도의 디렉터리에 설치해야 합니다.  
  
-   다음과 같은 위치에는 프로그램 파일 및 데이터 파일을 설치할 수 없습니다.  
  
    -   이동식 디스크 드라이브  
  
    -   압축 파일 시스템  
  
    -   시스템 파일이 있는 디렉터리  
  
## <a name="see-also"></a>관련 항목  
 [SQL Server 기본 인스턴스 및 명명된 인스턴스의 파일 위치](../../../2014/sql-server/install/file-locations-for-default-and-named-instances-of-sql-server.md)  
  
  
