---
title: "PHP SQL 드라이버 보안 고려 사항 | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security considerations
ms.assetid: a8c1a570-9204-454f-b94c-ba34f54d487c
caps.latest.revision: 37
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 2a7423bcfcfd28073840ad7f8c9ee2e7424507bc
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="security-considerations-for-php-sql-driver"></a>PHP SQL 드라이버 보안 고려 사항
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

이 항목에서는 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]를 사용하는 응용 프로그램 개발, 배포 및 실행과 관련된 보안 고려 사항을 설명합니다. SQL Server 보안에 대한 자세한 내용을 보려면 [데이터 보안 및 준수](http://go.microsoft.com/fwlink/?LinkId=129225)를 참조하세요.  
  
## <a name="connect-using-windows-authentication"></a>Windows 인증을 사용하여 연결  
다음과 같은 이유로 가능하면 SQL Server에 연결하는 데 Windows 인증을 사용해야 합니다.  
  
-   **인증하는 동안 네트워크를 통해 자격 증명이 전달되지 않습니다.** 데이터베이스 연결 문자열에 사용자 이름 및 암호가 포함되지 않습니다. 이는 구성 파일 내의 연결 문자열을 보거나 네트워크를 모니터링하여 악성 사용자 또는 공격자가 자격 증명을 가져올 수 없다는 것을 의미합니다.  
  
-   **사용자가 중앙 집중식 계정 관리를 받습니다.** 암호 만료 기간, 최소 암호 길이 및 잘못된 로그온 요청이 여러 번 있을 경우 계정 잠금 등의 보안 정책을 강제로 적용합니다.  
  
Windows 인증을 사용하여 서버에 연결하는 방법에 대한 정보는 [방법: Windows 인증을 사용하여 연결](../../connect/php/how-to-connect-using-windows-authentication.md)을 참조하세요.  
  
Windows 인증을 사용하여 연결할 때 SQL Server가 Kerberos 인증 프로토콜을 사용할 수 있도록 환경을 구성하는 것이 좋습니다. 자세한 내용은 [SQL Server 2005의 인스턴스에 대한 원격 연결을 만들 때 Kerberos 인증을 사용하고 있는지 확인하는 방법](http://go.microsoft.com/fwlink/?LinkId=121862) 또는 [Kerberos 인증 및 SQL Server](http://go.microsoft.com/fwlink/?LinkId=129226)를 참조하세요.  
  
## <a name="use-encrypted-connections-when-transferring-sensitive-data"></a>중요한 데이터를 전송할 때 암호화된 연결 사용  
중요한 데이터가 전송되거나 SQL Server에서 검색될 때마다 암호화된 연결을 사용해야 합니다. 암호화 된 연결을 설정 하는 방법에 대 한 정보를 참조 하십시오. [(SQL Server 구성 관리자) 데이터베이스 엔진에 암호화 연결 사용 하는 방법을](http://go.microsoft.com/fwlink/?LinkId=121864)합니다. [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]를 사용하여 보안 연결을 설정하려면 서버에 연결할 때 연결 암호화 특성을 사용합니다. 연결 특성에 대한 자세한 내용은 [Connection Options](../../connect/php/connection-options.md)을 참조하세요.  
  
## <a name="use-parameterized-queries"></a>매개 변수가 있는 쿼리 사용  
매개 변수가 있는 쿼리를 사용하여 SQL 주입 공격의 위험을 줄일 수 있습니다. 매개 변수가 있는 쿼리를 실행하는 예제를 보려면 [How to: Perform Parameterized Queries](../../connect/php/how-to-perform-parameterized-queries.md)을 참조하세요.  
  
SQL 주입 공격 및 관련된 보안 고려 사항에 대한 자세한 내용은 [SQL 주입](http://go.microsoft.com/fwlink/?LinkId=104224)을 참조하세요.  
  
## <a name="do-not-accept-server-or-connection-string-information-from-end-users"></a>최종 사용자에게서 서버 또는 연결 문자열 정보 허용하지 않음  
최종 사용자가 서버 또는 연결 문자열 정보를 응용 프로그램에 제출할 수 없도록 응용 프로그램을 작성합니다. 서버 및 연결 문자열 정보에 대해 엄격한 제어를 유지하면 악성 활동에 대한 노출 영역이 줄어듭니다.  
  
## <a name="turn-warningsaserrors-on-during-application-development"></a>응용 프로그램을 개발하는 동안 WarningsAsErrors 설정  
드라이버에서 표시하는 경고가 오류로 간주되도록 **WarningsAsErrors** 설정이 **true** 로 설정된 응용 프로그램을 개발합니다. 그러면 응용 프로그램을 배포하기 전에 경고를 전달할 수 있습니다. 자세한 내용은 [Handling Errors and Warnings](../../connect/php/handling-errors-and-warnings.md)을 참조하세요.  
  
## <a name="secure-logs-for-deployed-application"></a>배포된 응용 프로그램에 대한 보안 로그  
배포된 응용 프로그램에 대해 로그가 보안 위치에 기록되거나 해당 로깅이 해제되었는지 확인합니다. 그러면 로그 파일에 기록된 정보에 최종 사용자가 액세스할 가능성이 차단됩니다. 자세한 내용은 [Logging Activity](../../connect/php/logging-activity.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
[PHP SQL 드라이버 프로그래밍 가이드](../../connect/php/programming-guide-for-php-sql-driver.md)
  
