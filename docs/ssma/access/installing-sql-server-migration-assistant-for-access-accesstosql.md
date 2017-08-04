---
title: "SQL Server Migration Assistant for Access (AccessToSQL) 설치 | Microsoft Docs"
ms.prod: sql-non-specified
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
helpviewer_keywords:
- installing SSMA
- instructions, installation
- instructions, upgrade
- licensing SSMA
- prerequisites for installing SSMA
- procedure, installation
- procedure, licensing
- procedure, upgrading
- removing SSMA
- Setup
- uninstalling SSMA
- upgrading SSMA
ms.assetid: dd50eebd-75df-4e0d-8c4d-88b511aae4c7
caps.latest.revision: 31
author: sabotta
ms.author: carlasab
manager: lonnyb
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 2915318b5bbe85ad21a5e5095a7322013dfa7b44
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="installing-sql-server-migration-assistant-for-access-accesstosql"></a>SQL Server Migration Assistant for Access (AccessToSQL) 설치
[!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Migration Assistant (SSMA) 액세스를 위해 Windows Installer 기반 마법사를 사용 하 여 설치 됩니다. 이 항목의 SSMA 최신 버전에 대 한 링크는 설치 필수 구성 요소에 대 한 정보 및 설치, 라이선스, 제거 및 SSMA 업그레이드에 대 한 지침을 제공 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
SSMA를 설치 하기 전에 시스템에는 다음 요구 사항을 충족 하는지 확인 합니다.  
  
-   Windows 7 또는 이후 버전 또는 Windows Server 2008 또는 이상 버전  
  
-   [!INCLUDE[msCoName](../../includes/msconame_md.md)]Windows Installer 3.1 또는 이후 버전입니다.  
  
-   [!INCLUDE[msCoName](../../includes/msconame_md.md)] .NET Framework 버전 4.0 또는 이후 버전입니다. .NET Framework 버전 4.0에서 사용할 수는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 제품 디스크에서의 [Microsoft.NET Framework 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=48882) 웹 사이트입니다.  
  
-   에 대 한 액세스 및의 대상 인스턴스를 호스트 하는 컴퓨터에 대 한 권한이 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]SQL Azure DB 위치 하는 마이그레이션 데이터베이스 개체 및 데이터입니다.  
  
-   DAO 12.0 또는 14.0 공급자 버전입니다. Microsoft Office 2010/2007 제품에서 DAO 공급자를 설치 하거나 Microsoft 웹 사이트에서 다운로드할 수 있습니다.  
  
-   SQL Server 액세스 SNAC (Native Client) 버전 10.5 이상 SQL Azure로 마이그레이션에 대 한 합니다. SNAC의 최신 버전을 가져올 수 [Microsoft® SQL Server® 2008 R2 기능 팩](http://go.microsoft.com/fwlink/?LinkId=196940)  
  
-   4GB RAM 권장 합니다.  
  
## <a name="installing-ssma"></a>SSMA를 설치합니다.  
SSMA는 웹 다운로드입니다. 최신 버전을 다운로드 하려면 참조는 [SQL Server Migration Assistant 다운로드 페이지](http://aka.ms/ssmaforaccess)합니다.  
  
SSMA를 설치 하기 전에 최신 버전을 다운로드 한 후의 설치 파일을 추출 해야 합니다.  
  
**SSMA를 설치 하려면**  
  
1.  SSMA를 두 번 클릭 액세스용  *n* 합니다. Install.exe 여기서  *n*  는 빌드 번호입니다.  
  
2.  시작 페이지에서 클릭 **다음**합니다.  
  
    설치 필수 구성 요소가 없는 필수 구성 요소를 먼저 설치 해야 한다는 나타내는 메시지가 표시 됩니다. 모든 필수 구성 요소를 설치 하 고 다음 설치 프로그램을 다시 실행 했는지 확인 합니다.  
  
3.  최종 사용자 사용권 계약을 읽어보십시오. 동의 하면 선택 **사용권 계약에 동의**, 클릭 하 고 **다음**합니다.  
  
4.  설치 유형 선택 페이지에서 클릭 **일반**합니다.  
  
5.  **설치**를 클릭합니다.  
  
> [!IMPORTANT]  
> 1.  새 버전을 설치 하기 전에 Access 용 SSMA의 모든 이전 버전을 제거 하십시오.  
  
기본 설치 위치는 C:\Program Files\Microsoft SQL Server Migration Assistant for Access입니다.  
  
## <a name="uninstalling-ssma-for-access"></a>Access 용 SSMA를 제거  
SSMA를 사용 하 여 제거 **프로그램 추가 / 제거** 제어판에서. 알아 두어야 하는 프로그램 제거지 않습니다 하지 SSMA 프로젝트 파일을 삭제 하거나 로그 파일.  
  
**SSMA를 제거 하려면**  
  
1.  클릭 **시작**, 클릭 **제어판**, 클릭 하 고 **프로그램 추가 / 제거**합니다.  
  
2.  선택 **Microsoft SQL Server Migration Assistant for Access**, 클릭 하 고 **제거**합니다.  
  
## <a name="upgrading-to-a-later-version"></a>이후 버전으로 업그레이드  
Access 용 SSMA의 이후 버전으로 업그레이드 하려면 먼저 Access 용 SSMA를 제거 하 고 최신 버전을 설치 해야 합니다. 제거 및 설치를 위한이 항목의 앞부분에 나오는 지침을 따릅니다.  
  
Access 용 SSMA의 이전 버전에서 프로젝트를 열면 프로젝트를 최신 버전으로 변환 하려면 SSMA 묻습니다. 클릭 해야 **예** SSMA의 최신 버전의 프로젝트와 함께 작동 하도록 합니다.  
  
## <a name="see-also"></a>관련 항목:  
[Access 데이터베이스 마이그레이션을 준비](http://msdn.microsoft.com/en-us/9b80a9e0-08e7-4b4d-b5ec-cc998d3f5114)  
[SQL Server에 대 한 액세스 데이터베이스 마이그레이션](http://msdn.microsoft.com/en-us/76a3abcf-2998-4712-9490-fe8d872c89ca)  
[SQL Server에 대 한 액세스 응용 프로그램 연결](http://msdn.microsoft.com/en-us/82374ad2-7737-4164-a489-13261ba393d4)  
  
