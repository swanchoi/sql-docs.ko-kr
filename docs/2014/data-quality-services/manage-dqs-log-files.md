---
title: DQS 로그 파일 관리 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- logging
- log files
- dqs log files
ms.assetid: 4fccfd24-aede-4882-be69-ec1e82682e16
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 3d6bc56129d32c181dc37b2c1cdd4015830c0adc
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2019
ms.locfileid: "56013414"
---
# <a name="manage-dqs-log-files"></a>DQS 로그 파일 관리
  DQS([!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] ) 로그 파일은 [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]및 [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)]관련 문제를 진단하고 해결하는 데 도움이 됩니다. [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]및 [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)]에 대해 로그 파일이 개별적으로 생성됩니다.  
  
 [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] 를 사용하여 [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] 기능 및 모듈의 로그 심각도 설정을 구성할 수 있습니다. 또한 [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] 컴퓨터에서 DQS_MAIN 데이터베이스 및 XML 파일의 DQS 로그 구성 설정을 수동으로 변경하여 DQS 로그 파일의 다른 (고급) 설정을 구성할 수도 있습니다.  
  
##  <a name="DQSServer"></a> Data Quality 서버 로그 파일  
 [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] 로그 파일 DQServerLog.DQS_MAIN.log에는 [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]에서 실행된 작업에 대한 로그가 포함됩니다. SQL Server의 기본 인스턴스를 설치한 경우 DQServerLog.DQS_MAIN.log 파일은 C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log에 있습니다. [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] 로그 파일에는 다음과 같은 정보 조각이 각각 파이프(|)로 구분되어 포함됩니다.  
  
-   날짜 및 시간  
  
-   스레드 이름  
  
-   스레드 ID  
  
-   로그 심각도(치명적, 오류, 경고, 정보 및 디버그)  
  
    > [!NOTE]  
    >  디버그 로그 심각도는 자세히와 동일합니다.  
  
-   UID(내부 DQS 인프라 ID)  
  
-   Namespace  
  
-   클래스 및 메서드  
  
-   메시지  
  
 또한 로그 파일은 애플리케이션 버전, 컴퓨터 이름, 사용자 이름 및 운영 체제에 대한 정보를 표시합니다.  
  
 [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] 로그 파일의 예제 항목은 다음과 같습니다.  
  
```  
23-08-2013 01:45:29|[]|4|INFO|PUID|InfInfoModuleStarting|Microsoft.Ssdqs.Core.Startup.ServerInit|Starting DQS ServerInit: version [12.0.0.0], machine name [DQS-TEST], user name [NT Service\MSSQLSERVER], operating system [Microsoft Windows NT 6.1.7600.0]...  
```  
  
 DQServerLog.DQS_MAIN.log 파일은 롤링 파일이며 기존 로그 파일이 [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] 로그 구성 설정에 지정된 롤링 파일 크기 제한을 초과하면 새 로그 파일이 생성됩니다. 자세한 내용은 [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md)을 참조하세요.  
  
##  <a name="DQSClient"></a> Data Quality 클라이언트 로그 파일  
 [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] 로그 파일 DQClientLog.log에는 클라이언트 쪽 로그가 포함됩니다. [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] 로그 파일은 %APPDATA%\SSDQS\Log에 있습니다. [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] 로그 파일에는 서버 로그 파일과 유사하지만 클라이언트 쪽에 대한 정보 집합이 포함됩니다.  
  
 [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] 로그 파일과 마찬가지로 [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] 로그 파일도 롤링 파일이며 기존 로그 파일이 [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] 로그 구성 설정에 지정된 롤링 파일 크기 제한을 초과하면 새 로그 파일이 생성됩니다. 자세한 내용은 [Configure Advanced Settings for DQS Log Files](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md)을 참조하세요.  
  
##  <a name="DQSCleansing"></a> DQS 정리 구성 요소 로그 파일  
 [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] 로그 파일 DQSSSISLog.log에는 [!INCLUDE[ssDQSCleansingLong](../includes/ssdqscleansinglong-md.md)]를 사용하여 수행된 작업에 대한 로그가 포함됩니다. [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] 구성 요소 로그 파일은 %APPDATA%\SSDQS\Log에 있습니다. [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)] 로그 파일에는 서버 로그 파일과 유사하지만 [!INCLUDE[ssDQSCleansing](../includes/ssdqscleansing-md.md)]에 대한 정보 집합이 포함됩니다.  
  
##  <a name="RT"></a> 관련 태스크  
  
|태스크 설명|항목|  
|----------------------|-----------|  
|[!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]를 사용하여 DQS 로그 파일의 로그 심각도 설정을 구성하는 방법에 대해 설명합니다.|[DQS 로그 파일에 대한 심각도 수준 구성](../../2014/data-quality-services/configure-severity-levels-for-dqs-log-files.md)|  
|DQS 로그 파일의 고급 설정을 수동으로 구성하는 방법에 대해 설명합니다.|[DQS 로그 파일에 대한 고급 설정 구성](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md)|  
  
## <a name="see-also"></a>관련 항목  
 [DQS 관리](../../2014/data-quality-services/dqs-administration.md)  
  
  
