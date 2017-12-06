---
title: "원격 테이블 복사본 (SQL Server PDW)에 대 한 SQL Server PDW 구성"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.prod: sql-non-specified
ms.prod_service: mpp-data-warehouse
ms.service: 
ms.component: analytics-platform-system
ms.technology: mpp-data-warehouse
ms.custom: 
ms.date: 01/13/2017
ms.reviewer: na
ms.suite: sql
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 496b4214-5891-404c-8237-c2a1e09db6d5
caps.latest.revision: "11"
ms.openlocfilehash: 5daa546ed4cf0eeed1c51713fd9e55aa88515380
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="configure-sql-server-pdw-for-remote-table-copies"></a>원격 테이블 복사본에 대 한 SQL Server PDW 구성
비 어플라이언스 서버의 SMP SQL Server 데이터베이스에 테이블을 복사 하려면 원격 테이블 복사 기능을 사용 하려면 SQL Server PDW 구성 하는 방법에 설명 합니다.  
  
이 항목에서는 원격 테이블 복사본을 구성 하기 위한 구성 단계 중 하나. 목록이 모든 구성 단계에 대 한 참조 [원격 테이블 복사](remote-table-copy.md)합니다.  
  
## <a name="before-you-begin"></a>시작하기 전에  
원격 테이블 복사본을 사용 하도록 SQL Server PDW를 구성 하려면 다음을 수행 해야 합니다.  
  
-   분석 플랫폼 시스템 관리자 계정이에 직접 로그인 할 수는  ***appliance_domain*-AD01** 및  ***appliance_domain*-AD02** 노드.  
  
-   호스트 이름 또는 대상 서버의 IP 이름을 알아야 합니다.  
  
## <a name="HowToPDW"></a>원격 테이블 복사본에 대 한 SQL Server PDW 구성: DNS에 호스트 이름을 업데이트  
**CREATE REMOTE TABLE** 문, 원격 테이블 복사본에 사용 되는 IP 주소 또는 SMP Windows 시스템의 IP 이름 중 하나를 사용 하 여 대상 서버를 지정 합니다. IP 이름을 사용 하려면 DNS 서버에 성공적인 이름 확인에 대 한 항목을 추가 해야 합니다.  
  
다음 단계에는 DNS 서버를 업데이트 하는 방법을 간략하게 설명 합니다.  
  
1.  활성 AD 노드에 로그온 (일반적으로  ***appliance_domain*-AD01**).  
  
2.  DNS 관리자를 엽니다. 아래 **관리 도구** 에 **시작** 메뉴.  
  
3.  DNS 관리자를 사용 하 여 IP 이름을 추가 합니다.  
  
## <a name="see-also"></a>관련 항목:  
<!-- MISSING LINKS 
[Common Metadata Query Examples &#40;SQL Server PDW&#41;](../sqlpdw/common-metadata-query-examples-sql-server-pdw.md)  
-->
[비 어플라이언스 DNS 이름을 확인 하기 위해 DNS 전달자를 사용 합니다.](use-a-dns-forwarder-to-resolve-non-appliance-dns-names.md)  
<!-- MISSING LINKS 
[Security - Configure Domain Trusts &#40;SQL Server PDW&#41;](../sqlpdw/security-configure-domain-trusts-sql-server-pdw.md)  
-->
  