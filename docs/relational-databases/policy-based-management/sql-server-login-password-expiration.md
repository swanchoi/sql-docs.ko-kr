---
title: SQL Server 로그인 암호 만료 | Microsoft 문서
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 7e3bf9da-a436-433d-847a-47c30428cad3
author: VanMSFT
ms.author: vanto
manager: craigg
ms.openlocfilehash: a6bbe425ade7e616de9976a07a874539be50b65c
ms.sourcegitcommit: ef6e3ec273b0521e7c79d5c2a4cb4dcba1744e67
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51512418"
---
# <a name="sql-server-login-password-expiration"></a>SQL Server 로그인 암호 만료
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  이 규칙은 각 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 로그인의 "암호 만료"가 설정되었는지 검사합니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인증이 설정되었고 운영 체제가 [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)]이전 버전인 경우 공격자는 알려진 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 로그인 암호를 반복적으로 악용할 수 있습니다.  
  
## <a name="best-practices-recommendations"></a>최선의 구현 방법 권장 사항  
 운영 체제를 [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)]으로 업그레이드하는 것이 좋습니다.  
  
 현재 환경에 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인증이 필요하지 않은 경우 Windows 인증을 사용합니다. 자세한 내용은 [인증 모드 선택](../../relational-databases/security/choose-an-authentication-mode.md)을 참조하세요.  
  
 모든 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 로그인에 대해 "암호 만료"를 설정합니다. [ALTER LOGIN](../../t-sql/statements/alter-login-transact-sql.md) 을 사용하여 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 로그인에 대한 암호 정책을 구성합니다.  
  
## <a name="for-more-information"></a>참조 항목  
 [암호 정책](../../relational-databases/security/password-policy.md)  
  
## <a name="see-also"></a>참고 항목  
 [정책 기반 관리를 사용하여 최선의 방법 모니터링 및 적용](../../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
