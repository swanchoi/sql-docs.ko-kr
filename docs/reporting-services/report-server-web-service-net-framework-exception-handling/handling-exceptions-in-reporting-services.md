---
title: Reporting Services의 예외 처리 | Microsoft Docs
ms.date: 03/14/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-server-web-service-net-framework-exception-handling
ms.topic: reference
helpviewer_keywords:
- SOAP [Reporting Services], exceptions
- .NET Framework [Reporting Services]
- exceptions [Reporting Services], about exception handling
- SoapException object
ms.assetid: 1a443432-2db5-48c5-bc29-433b4688082f
author: markingmyname
ms.author: maghan
ms.openlocfilehash: b743287ad9056d32c55a7d83189cd7c98fcf9920
ms.sourcegitcommit: bfa10c54e871700de285d7f819095d51ef70d997
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2019
ms.locfileid: "54257018"
---
# <a name="handling-exceptions-in-reporting-services"></a>Reporting Services의 예외 처리
  Reporting Services SOAP API 클라이언트 요청을 완료할 수 없는 경우 보고서 서버에서는 호출에 대해 예상된 결과가 아니라 오류를 반환합니다. 호출을 완료할 수 없는 경우 보고서 서버 웹 서비스에 대한 오류가 SOAP **Fault** XML 요소로 반환됩니다. 오류의 주요 설명 요소는 보고서 서버에서 제공하는 모든 오류 정보와 추가 웹 서비스 오류 정보를 포함하는 **detail** 요소입니다. **detail** 요소의 주요 정보는 보고서 서버 오류 코드입니다. 메시지 및 오류 코드를 기준으로 응용 프로그램에서 수행할 적절한 다음 동작을 결정할 수 있습니다. SOAP 오류에 대한 자세한 내용은 W3C(World Wide Web 컨소시엄) 웹 사이트 http://www.w3.org/TR/SOAP을 참조하십시오.  
  
## <a name="soap-faults-and-the-net-framework"></a>SOAP 오류 및 .NET Framework  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]에서 웹 서비스에 대한 클라이언트 요청에 오류가 발생할 경우 보고서 서버에서 **SoapException** 개체를 throw하여 웹 서비스를 호출하는 클라이언트 코드에 오류를 전달합니다. **SoapException**은 SOAP 오류에 포함된 정보를 래핑합니다. **SoapException**의 **Detail** 속성은 SOAP 오류의 **detail** 요소에 매핑됩니다. 애플리케이션에서는 try/catch 블록으로 **SoapException** 개체를 catch하고 **SoapException**의 **Detail** 속성을 사용하여 올바른 조치를 취해야 합니다. **SoapException** 클래스 및 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]의 **Detail** 속성에 대한 자세한 내용은 [Reporting Services SoapException 클래스](../../reporting-services/report-server-web-service-net-framework-exception-handling/soapexception-class/reporting-services-soapexception-class.md)를 참조하세요. **SoapException** 클래스에 대한 자세한 내용은 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK 설명서를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Detail 속성](../../reporting-services/report-server-web-service-net-framework-exception-handling/soapexception-class/detail-property.md)   
 [Reporting Services의 예외 처리 소개](../../reporting-services/report-server-web-service-net-framework-exception-handling/introducing-exception-handling-in-reporting-services.md)   
 [Reporting Services SoapException 클래스](../../reporting-services/report-server-web-service-net-framework-exception-handling/soapexception-class/reporting-services-soapexception-class.md)  
  
  
