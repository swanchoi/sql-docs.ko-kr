---
title: MSSQLSERVER_833 | Microsoft 문서
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 833 (Database Engine error)
ms.assetid: 14129cc4-be80-4772-9e3f-0e5da4d0696b
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: db70d1757073a48ab09f31cfb3570570e54a48cd
ms.sourcegitcommit: aa4f594ec6d3e85d0a1da6e69fa0c2070d42e1d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59241651"
---
# <a name="mssqlserver833"></a>MSSQLSERVER_833
    
## <a name="details"></a>설명  
  
|||  
|-|-|  
|제품 이름|SQL Server|  
|이벤트 ID|833|  
|이벤트 원본|MSSQLSERVER|  
|구성 요소|SQLEngine|  
|심볼 이름|BUF_LONG_IO|  
|메시지 텍스트|SQL Server 데이터베이스의 파일 [%ls]를 완료 하려면 %d 초 보다 오래 걸리는 I/O 요청이 %d 개가 발생 합니다.`[%ls] (%d)`합니다.  OS 파일 핸들은 0x%p입니다.  가장 최근의 시간 초과 I/O의 오프셋은 %#016I64x입니다.|  
  
## <a name="explanation"></a>설명  
 이 메시지는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 가 디스크에서 읽기 또는 쓰기 요청을 실행하여 해당 요청이 반환되는 데 15초 이상 소요되었음을 나타냅니다. 이 오류는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 보고하고 IO 하위 시스템에 문제가 있음을 나타냅니다.  
  
### <a name="possible-causes"></a>가능한 원인  
 이 문제는 시스템 성능 문제, 하드웨어 오류, 펌웨어 오류, 디바이스 드라이버 문제 또는 IO 프로세스의 필터 드라이버 조정으로 인해 발생할 수 있습니다.  
  
## <a name="user-action"></a>사용자 동작  
 하드웨어 관련 오류 메시지에 대한 시스템 이벤트 로그를 검사하여 이 오류의 문제를 해결합니다. 또한 사용 가능한 경우 하드웨어 관련 로그를 검사합니다.  
  
 성능 모니터를 사용하여 다음 카운터를 검사합니다.  
  
-   **Average Disk Sec/Transfer**  
  
-   **Average Disk Queue Length**  
  
-   **Current Disk Queue Length**  
  
 예를 들어 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 를 실행하는 컴퓨터의 **Average Disk Sec/Transfer** 시간은 일반적으로 15밀리초 미만입니다. **Average Disk Sec/Transfer** 값이 증가하는 경우 이는 I/O 하위 시스템이 I/O 요구를 최적으로 따라가고 있지 못함을 나타냅니다.  
  
> [!NOTE]  
>  바이러스 백신 프로그램으로 인해 디스크 액세스가 느려질 수 있습니다. 액세스 속도를 높이려면 활성 바이러스 검사의 오류 메시지에서 지정한 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터 파일을 제외하십시오.  
  
 I/O 오류에 대한 자세한 내용은 [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))(Microsoft SQL Server I/O 기본 사항, 2장) 및 [https://support.microsoft.com/kb/897284](https://support.microsoft.com/kb/897284)의 기술 자료 아티클을 참조하세요.  
  
  
