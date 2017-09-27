---
title: "사용자 지정 파일 UserList 섹션 | Microsoft Docs"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UserList section in rds [ADO]
- customization file in RDS [ADO]
ms.assetid: 42e8ec20-eaac-4a95-8cb8-4bba93a75bcb
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 5521648ed1c4d125168d3f9afb7a4c884854d9b4
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="customization-file-userlist-section"></a>사용자 지정 파일 UserList 섹션
**userlist** 관련 섹션의 **연결** 의 동일한 영역 *식별자* 매개 변수입니다.  
  
 이 섹션에 포함 될 수 있습니다는 *사용자 액세스 항목*, 재정의 및 지정된 된 사용자에 대 한 대 한 액세스를 지정 하는 *기본* *액세스 항목* 일치 에서**연결** 섹션.  
  
> [!IMPORTANT]
>  Windows 8 및 Windows Server 2012 부터는 RDS 서버 구성 요소가 더 이상에 포함 Windows 운영 체제 (Windows 8 참조 및 [Windows Server 2012 호환성 설명서](https://www.microsoft.com/en-us/download/details.aspx?id=27416) 자세한 세부 정보에 대 한). RDS 클라이언트 구성 요소는 나중 버전의 Windows에서 제거 됩니다. 새 개발 작업에서는 이 기능을 사용하지 않도록 하고, 현재 이 기능을 사용하는 응용 프로그램은 수정하세요. RDS를 사용 하는 응용 프로그램을 마이그레이션해야 합니다. [WCF 데이터 서비스](http://go.microsoft.com/fwlink/?LinkId=199565)합니다.  
  
## <a name="syntax"></a>구문  
 사용자 액세스 항목 형식입니다.  
  
 *사용자 이름***=**   
 ***accessRights***  
  
|부분|Description|  
|----------|-----------------|  
|*사용자 이름*|*사용자 이름* 이 연결을 사용 하는 사람의 합니다. 유효한 사용자 이름은 IIS에서 설정 됩니다 **Service Manager** 대화 상자.|  
|***accessRights***|다음 액세스 권한 중 하나입니다.<br /><br /> -   **액세스 권한 없음** -사용자 데이터 원본에 액세스할 수 없습니다.<br />-   **읽기 전용** -사용자는 데이터 소스를 읽을 수 있습니다.<br />-   **ReadWrite** -사용자 읽기 또는 데이터 원본에 쓸 수 있습니다.|  
  
## <a name="see-also"></a>관련 항목:  
 [사용자 지정 파일 연결 섹션](../../../ado/guide/remote-data-service/customization-file-connect-section.md)   
 [사용자 지정 파일 로그 섹션](../../../ado/guide/remote-data-service/customization-file-logs-section.md)   
 [사용자 지정 파일 SQL 섹션](../../../ado/guide/remote-data-service/customization-file-sql-section.md)   
 [DataFactory 사용자 지정](../../../ado/guide/remote-data-service/datafactory-customization.md)   
 [필요한 클라이언트 설정](../../../ado/guide/remote-data-service/required-client-settings.md)   
 [사용자 지정 파일 이해](../../../ado/guide/remote-data-service/understanding-the-customization-file.md)   
 [고유한 사용자 지정된 처리기 작성](../../../ado/guide/remote-data-service/writing-your-own-customized-handler.md)


