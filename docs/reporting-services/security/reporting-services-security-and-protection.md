---
title: Reporting Services 보안 및 보호 | Microsoft Docs
ms.date: 08/26/2016
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- security [Reporting Services]
- Reporting Services, security
ms.assetid: 270075c5-bf12-4467-a775-abbda3d954a5
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 22904f062ec460fce229835a6657610639419350
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47850333"
---
# <a name="reporting-services-security-and-protection"></a>Reporting Services 보안 및 보호
  이 섹션에서는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]의 보안 기능에 대해 설명합니다. [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]에서 지원되는 권한 부여 모델 및 인증 공급자에 대해서도 설명합니다.  
  
## <a name="extended-protection-for-authentication"></a>인증에 대한 확장된 보호  
 [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]부터는 인증에 대한 확장된 보호가 지원됩니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 기능은 채널 바인딩 및 서비스 바인딩을 사용해 인증 보호를 향상시킬 수 있도록 지원합니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 기능은 확장된 보호를 지원하는 운영 체제에서 사용해야 합니다. 자세한 내용은 [Extended Protection for Authentication with Reporting Services](../../reporting-services/security/extended-protection-for-authentication-with-reporting-services.md)을(를) 참조하세요.  
  
## <a name="authentication-and-authorization"></a>인증 및 권한 부여  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 는 보고서 서버에 대해 사용자 및 클라이언트 응용 프로그램에 부여할 다양한 인증 유형을 제공합니다. 보고서 서버에 맞는 인증 유형을 사용하면 조직에서 요구되는 적합한 수준의 보안을 확보할 수 있습니다. 자세한 내용은 [Authentication with the Report Server](../../reporting-services/security/authentication-with-the-report-server.md)을(를) 참조하세요.  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 는 또한 역할 및 권한을 이용하여 보고서 서버 카탈로그 내용에 대한 사용자 액세스 권한을 제어합니다. 즉, 누가 어떤 내용에 액세스할 수 있는지, 액세스하는 방법 등을 제어합니다. 자세한 내용은 [역할 및 사용 권한&#40;Reporting Services&#41;](../../reporting-services/security/roles-and-permissions-reporting-services.md)을 참조하세요.  
  
## <a name="related-tasks"></a>관련 작업  
  
|태스크 설명|링크|  
|-----------------------|-----------|  
|SSL(Secure Socket Layer)를 구성하여 클라이언트와 보고서 서버의 연결에 보안을 설정합니다.|[기본 모드 보고서 서버에서 SSL 연결 구성](../../reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server.md)|  
  
  
