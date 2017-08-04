---
title: "마스터 데이터 관리자 웹 서비스 프록시 클래스를 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 03/17/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
ms.assetid: 8bdab026-a0c0-41f3-9d36-f3919c23247f
caps.latest.revision: 8
author: sabotta
ms.author: carlasab
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: a45cd15ced90aef95feb03f8fbaafd5aa70cb746
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="create-master-data-manager-web-service-proxy-classes"></a>마스터 데이터 관리자 웹 서비스에 대한 프록시 클래스 만들기
  [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] 웹 서비스를 사용하면 사용자의 [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] 웹 사이트에 액세스할 수 있는 모든 컴퓨터에서 [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)]의 기능을 프로그래밍 방식으로 사용할 수 있습니다. 웹 서비스에 액세스하기 위한 코드를 작성하려면 먼저 프록시 클래스를 생성해야 합니다. 웹 서비스 작업을 수행하는 데 사용되는 주요 프록시 클래스는 <xref:Microsoft.MasterDataServices.ServiceClient> 인터페이스를 구현하는 <xref:Microsoft.MasterDataServices.IService> 클래스입니다.  
  
## <a name="enable-web-service-metadata-publishing"></a>웹 서비스 메타데이터 게시 활성화  
 프록시 클래스를 생성하려면 먼저 웹 서비스 메타데이터 게시를 활성화해야 합니다. 이렇게 하려면 다음 단계를 수행하십시오.  
  
1.  열기는 [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] 텍스트 편집기에서 Web.config 파일입니다. 이 파일은 [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] 설치 경로의 WebApplication 폴더에 있습니다.  
  
2.  찾을 **mdsWsHttpBehavior** 섹션 아래  **\<serviceBehaviors >**합니다. 에 대 한는  **\<serviceMetadata >** 요소인 설정 **httpGetEnabled** 를 **true**합니다.  
  
    > [!NOTE]  
    >  웹 서비스를 통해 SSL Secure Sockets Layer ()를 사용 하려면 설정 **httpsGetEnabled** 를 **true** 에 **mdsWsHttpBehavior** web.config 파일의 섹션입니다. 변경 해야 **mdsWsHTTPBinding** 도 SSL 및 SSL 이외의 섹션 주석에 대해 구성 됩니다.  
  
3.  파일의 변경 내용을 저장합니다.  
  
4.  예를 들어 서비스 URL로 이동 하 여 메타 데이터 게시를 테스트: `http://yourserver/MDS/service/service.svc`합니다. 메타데이터 게시가 활성화된 경우 "서비스를 만들었습니다."로   
    시작하는 페이지가 표시됩니다.  
  
## <a name="creating-proxy-classes-by-using-visual-studio"></a>Visual Studio를 사용하여 프록시 클래스 만들기  
 프록시 클래스를 생성 하는 가장 간단한 방법은 추가 하는 Visual Studio 2010이 설치 되어 있는 경우는 **서비스 참조** 프로젝트에 있습니다. [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] 웹 응용 프로그램의 URL에 /service/service.svc를 추가하면 서비스 참조의 주소가 됩니다. 예를 들면 `http://yourserver/MDS/service/service.svc`과 같습니다. 자세한 내용은 참조 [하는 방법: 추가, 업데이트 또는 서비스 참조를 제거](http://go.microsoft.com/fwlink/?LinkId=221167)합니다.  
  
## <a name="creating-proxy-classes-by-using-svcutilexe"></a>Svcutil.exe를 사용하여 프록시 클래스 만들기  
 있어야 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 또는 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Svcutil.exe 컴퓨터에 설치 하려면 Windows SDK를 설치 합니다. [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]를 사용하는 경우에는 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 명령 프롬프트를 사용하여 명령을 실행해야 합니다. 자세한 내용은 참조 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](http://go.microsoft.com/fwlink/?LinkId=165027) 및 [서비스 메타 데이터에서 WCF 클라이언트 생성](http://go.microsoft.com/fwlink/?LinkId=164821)합니다.  
  
 Svcutil.exe를 사용하여 C# 프록시 클래스 집합을 만들려면 다음과 같은 명령을 사용하십시오.  
  
```  
svcutil.exe http://<server_name:port>/<virtual_path>/Service/Service.svc   
/out:<proxy_name>.cs /messageContract /tcv:Version35   
/noconfig /ct:System.Collections.ObjectModel.Collection`1   
/namespace:*,Microsoft.MasterDataServices  
```  
  
 각 항목이 나타내는 의미는 다음과 같습니다.  
  
-   *servername*:*포트* 컴퓨터 이름 및 포트 번호를 호스팅하는 컴퓨터의 [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)]합니다.  
  
-   *virtual_path* 의 가상 경로 [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] 인터넷 정보 서비스 (IIS).  
  
-   *proxy_name* 생성된 된 프록시 파일에 대 한 이름입니다.  
  
## <a name="see-also"></a>참고 항목  
 [범주별로 분류 한 웹 서비스 작업 &#40; Master Data services&#41;](../../master-data-services/develop/categorized-web-service-operations-master-data-services.md)  
  
  