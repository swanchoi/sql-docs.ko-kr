---
title: 데이터베이스 미러링 끝점의 AlwaysOn 가용성 그룹 (SQL Server PowerShell) 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], endpoint
ms.assetid: 6197bbe7-67d4-446d-ba5f-cabfa5df77f1
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 77df7902f5dd1673736f4a993c4e29c50d7accc0
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48157523"
---
# <a name="create-a-database-mirroring-endpoint-for-alwayson-availability-groups-sql-server-powershell"></a>AlwaysOn 가용성 그룹에 대한 데이터베이스 미러링 엔드포인트 만들기(SQL Server PowerShell)
  이 항목에서는 PowerShell을 사용하여 [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]에서 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]에 사용할 데이터베이스 미러링 엔드포인트를 만드는 방법에 대해 설명합니다.  
  
 **항목 내용**  
  
-   **시작하기 전 주의 사항:**  [보안](#Security)  
  
-   **데이터베이스 미러링 엔드포인트를 만드는 데 사용되는 도구:**[PowerShell](#PowerShellProcedure)  
  
## <a name="before-you-begin"></a>시작하기 전 주의 사항  
  
###  <a name="Security"></a> 보안  
  
> [!IMPORTANT]  
>  RC4 알고리즘은 더 이상 사용되지 않습니다. [!INCLUDE[ssNoteDepFutureDontUse](../../../includes/ssnotedepfuturedontuse-md.md)] AES를 사용하는 것이 좋습니다.  
  
####  <a name="Permissions"></a> Permissions  
 CREATE ENDPOINT 권한 또는 sysadmin 고정 서버 역할의 멤버 자격이 필요합니다. 자세한 내용은 [GRANT 엔드포인트 사용 권한&amp;#40;Transact-SQL&amp;#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql)을 참조하세요.  
  
##  <a name="PowerShellProcedure"></a> PowerShell 사용  
 **데이터베이스 미러링 엔드포인트를 만들려면**  
  
1.  데이터베이스 미러링 엔드포인트를 만들 서버 인스턴스로 디렉터리를 변경(`cd`)합니다.  
  
2.  ph x="1" /&gt; cmdlet을 사용하여 엔드포인트를 만든 다음 `Set-SqlHadrEndpoint`를 사용하여 엔드포인트를 시작합니다.  
  
###  <a name="PShellExample"></a> 예제(PowerShell)  
 다음 PowerShell 명령은 SQL Server 인스턴스(*Machine*\\*Instance*)에 데이터베이스 미러링 엔드포인트를 만듭니다. 이 엔드포인트는 포트 5022를 사용합니다.  
  
> [!IMPORTANT]  
>  이 예는 데이터베이스 미러링 엔드포인트가 현재 없는 서버 인스턴스에서만 작동합니다.  
  
```  
# Create the endpoint.  
$endpoint = New-SqlHadrEndpoint MyMirroringEndpoint -Port 5022 -Path SQLSERVER:\SQL\Machine\Instance  
  
# Start the endpoint  
Set-SqlHadrEndpoint -InputObject $endpoint -State "Started"  
  
```  
  
##  <a name="RelatedTasks"></a> 관련 태스크  
 **데이터베이스 미러링 엔드포인트를 구성하려면**  
  
-   [Windows 인증에 대한 데이터베이스 미러링 엔드포인트 만들기&amp;#40;Transact-SQL&amp;#41;](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [데이터베이스 미러링 엔드포인트에 대한 인증서 사용&amp;#40;Transact-SQL&amp;#41;](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [데이터베이스 미러링 엔드포인트의 아웃바운드 연결에 대한 인증서 사용 허용&amp;#40;Transact-SQL&amp;#41;](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [데이터베이스 미러링 엔드포인트의 인바운드 연결에 대한 인증서 사용 허용&amp;#40;Transact-SQL&amp;#41;](../../database-mirroring/database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [서버 네트워크 주소 지정&#40;데이터베이스 미러링&#41;](../../database-mirroring/specify-a-server-network-address-database-mirroring.md)  
  
-   [가용성 복제본 추가 또는 수정 시 엔드포인트 URL 지정&amp;#40;SQL Server&amp;#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 **데이터베이스 미러링 엔드포인트에 대한 정보를 보려면**  
  
-   [sys.database_mirroring_endpoints&#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
## <a name="see-also"></a>관련 항목  
 [가용성 그룹 만들기&#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md)   
 [AlwaysOn 가용성 그룹 개요 &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md)  
  
  
