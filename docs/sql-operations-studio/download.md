---
title: "다운로드 하 여 Microsoft SQL 작업 Studio (미리 보기) 설치 | Microsoft Docs"
description: "다운로드 및 설치 Microsoft SQL 작업 (미리 보기) 용 Studio 창, macOS 등 또는 Linux"
ms.custom: tools|sos
ms.date: 12/19/2017
ms.prod: sql-non-specified
ms.reviewer: alayu; erickang; sstein
ms.suite: sql
ms.prod_service: sql-tools
ms.component: sos
ms.tgt_pltfrm: 
ms.topic: article
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 3a34a03b447e26f072b6c8064cd115333600fef4
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="download-and-install-sql-operations-studio-preview"></a>다운로드 하 고 SQL 작업 Studio (미리 보기) 설치

[!INCLUDE[name-sos](../includes/name-sos.md)]Windows, macOS 등 및 Linux에서 실행 됩니다.

최신 릴리스를 설치 및 다운로드는 *년 12 월 공개 미리 보기*:

|플랫폼|다운로드|릴리스 날짜|
|:---|:---|:---|
|Windows|[설치 관리자](https://go.microsoft.com/fwlink/?linkid=865305)<br>[.zip](https://go.microsoft.com/fwlink/?linkid=865304)|2017 년 12 월 19 |
|MacOS|[.zip](https://go.microsoft.com/fwlink/?linkid=865306)|2017 년 12 월 19 |
|Linux|[. d](https://go.microsoft.com/fwlink/?linkid=865308)<br>[.rpm](https://go.microsoft.com/fwlink/?linkid=865309)<br>[. tar.gz](https://go.microsoft.com/fwlink/?linkid=865307)|2017 년 12 월 19|

최신 릴리스에 대 한 자세한 내용은 참조는 [릴리스 정보](release-notes.md)합니다.

## <a name="get-sql-operations-studio-preview-for-windows"></a>Windows에 대 한 SQL 작업 Studio (미리 보기) 가져오기

이 버전의 [!INCLUDE[name-sos](../includes/name-sos-short.md)] 표준 Windows 설치 관리자 환경 및.zip 포함 됩니다. 

**설치 관리자**

1. 다운로드 및 실행 된 [ [!INCLUDE[name-sos](../includes/name-sos-short.md)] Windows 용 설치 관리자](https://go.microsoft.com/fwlink/?linkid=865305)합니다.
1. 시작 된 [!INCLUDE[name-sos-short](../includes/name-sos-short.md)] 앱.


**.zip 파일**

1. 다운로드 [ [!INCLUDE[name-sos](../includes/name-sos-short.md)] Windows 용.zip](https://go.microsoft.com/fwlink/?linkid=865304)합니다.
2. 다운로드 한 파일을 찾아 압축을 풉니다.
3. `\sqlops-windows\sqlops.exe`을 실행합니다.


## <a name="get-sql-operations-studio-preview-for-macos"></a>MacOS에 대 한 SQL 작업 Studio (미리 보기) 가져오기

1. 다운로드 [ [!INCLUDE[name-sos](../includes/name-sos-short.md)] macOS에 대 한](https://go.microsoft.com/fwlink/?linkid=865306)합니다.
2. Zip 내용의 확장 하려면 두 번 클릭 합니다.
3. 있도록 [!INCLUDE[name-sos](../includes/name-sos-short.md)] 에서 사용할 수는 *실행 패드*를 끌어 *sqlops.app* 에 *응용 프로그램* 폴더입니다.


## <a name="get-sql-operations-studio-preview-for-linux"></a>Linux에 대 한 SQL 작업 Studio (미리 보기) 가져오기

1. 다운로드 [ [!INCLUDE[name-sos](../includes/name-sos-short.md)] Linux 용](https://go.microsoft.com/fwlink/?linkid=865307)합니다.
1. 파일 및 실행을 추출 하려면 [!INCLUDE[name-sos](../includes/name-sos-short.md)]새 터미널 창을 열고 다음 명령을 입력 합니다.

   ```bash
   cd ~
   cp ~/Downloads/sqlops-linux-<version string>.tar.gz ~
   tar -xvf ~/sqlops-linux-<version string>.tar.gz
   echo 'export PATH="$PATH:~/sqlops-linux-x64"' >> ~/.bashrc
   source ~/.bashrc
   sqlops
   ```

   > [!NOTE]
   > Ubuntu 및 Redhat에서 누락 된 종속성을 할 수 있습니다. 다음 명령을 사용 하 여 linux 버전에 따라 이러한 종속성을 설치 합니다.
   
   **Ubuntu:** 
   ```bash
   sudo apt-get install libxss1

   sudo apt-get install libgconf-2-4

   sudo apt-get install libunwind8
   ```

   **Redhat:** 
   ```bash
   yum install libXScrnSaver
   ```

## <a name="uninstall-sql-operations-studio-preview"></a>SQL 작업 Studio (미리 보기)를 제거 합니다.

설치한 경우 [!INCLUDE[name-sos-short](../includes/name-sos-short.md)] 동일한 방식으로 모든 Windows 응용 프로그램을 제거 하면 제거 하 여 Windows installer를 사용 합니다.

설치한 경우 [!INCLUDE[name-sos-short](../includes/name-sos-short.md)] .zip 또는 다른 보관 다음 단순히 파일을 삭제 합니다.

## <a name="supported-operating-systems"></a>지원되는 운영 체제

[!INCLUDE[name-sos](../includes/name-sos-short.md)]Windows, macOS 등 및 Linux에서 실행 하 고 다음 플랫폼에서 지원 됩니다.

### <a name="windows"></a>Windows
- Windows 10(64비트)
- Windows 8.1(64비트)
- Windows 8(64비트)
- Windows 7 (SP1) (64 비트)-필요 [KB2533623](https://www.microsoft.com/en-us/download/details.aspx?id=26767)
- Windows Server 2016
- Windows Server 2012 R2(64비트)
- Windows Server 2012(64비트)
- Windows Server 2008 R2(64비트)

### <a name="macos"></a>MacOS
- macOS 10.13 높은 시에라
- macOS 10.12 시에라

### <a name="linux"></a>Linux
- Red Hat Enterprise Linux 7.4
- Red Hat Enterprise Linux 7.3
- SUSE Linux Enterprise Server v12 SP2
- Ubuntu 16.04



## <a name="next-steps"></a>Next Steps

시작 하려면 다음 퀵 스타트 중 하나를 참조 합니다.
- [연결 및 SQL Server 쿼리](quickstart-sql-server.md)
- [연결 및 Azure SQL 데이터베이스 쿼리](quickstart-sql-database.md)
- [연결 및 Azure 데이터 웨어하우스를 쿼리 합니다.](quickstart-sql-dw.md)

에 기여 [!INCLUDE[name-sos](../includes/name-sos-short.md)]:
- [https://github.com/Microsoft/sqlopsstudio](https://github.com/Microsoft/sqlopsstudio) 

[Microsoft 개인정보취급방침](https://go.microsoft.com/fwlink/?LinkId=521839) 및 [사용 현황 데이터 수집](usage-data-collection.md)합니다.