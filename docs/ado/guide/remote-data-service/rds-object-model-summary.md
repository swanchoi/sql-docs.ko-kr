---
title: "RDS 개체 모델 요약 | Microsoft Docs"
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
- RDS objects [ADO], object model summary
- RDS object model [ADO]
ms.assetid: 909f9af7-31db-4eec-ad52-650ce74dac2f
caps.latest.revision: 15
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 1c89ea8ccd9875368ea0d279c54a1153bc0cfd3d
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="rds-object-model-summary"></a>RDS 개체 모델 요약
> [!IMPORTANT]
>  Windows 8 및 Windows Server 2012 부터는 RDS 서버 구성 요소가 더 이상에 포함 Windows 운영 체제 (Windows 8 참조 및 [Windows Server 2012 호환성 설명서](https://www.microsoft.com/en-us/download/details.aspx?id=27416) 자세한 세부 정보에 대 한). RDS 클라이언트 구성 요소는 나중 버전의 Windows에서 제거 됩니다. 새 개발 작업에서는 이 기능을 사용하지 않도록 하고, 현재 이 기능을 사용하는 응용 프로그램은 수정하세요. RDS를 사용 하는 응용 프로그램을 마이그레이션해야 합니다. [WCF 데이터 서비스](http://go.microsoft.com/fwlink/?LinkId=199565)합니다.  
  
|개체|Description|  
|------------|-----------------|  
|[.RDS 데이터 공간](../../../ado/reference/rds-api/dataspace-object-rds.md)|이 개체는 서버 프록시를 가져오는 메서드를 포함 합니다. 프록시는 기본 또는 사용자 지정 서버 프로그램 (비즈니스 개체) 일 수 있습니다. 서버 프로그램 인터넷, 인트라넷, 로컬 영역 네트워크에서 호출할 수 또는 로컬 동적 연결 라이브러리 여야 합니다.<br /><br /> **DataSpace** 개체는 스크립팅 작업에 안전 합니다.|  
|[업데이트할](../../../ado/reference/rds-api/datafactory-object-rdsserver.md)|이 개체의 기본 서버 프로그램을 나타냅니다. 기본 RDS 데이터 검색 및 업데이트 동작을 실행합니다.<br /><br /> **DataFactory** 개체가 스크립팅 작업에 안전 합니다.|  
|[.RDS DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md)|이 개체에 자동으로 실행할 수는 **.rds입니다 DataSpace** 및 **업데이트할** 개체입니다.<br /><br /> 이 개체를 사용 하 여 기본 RDS 데이터 검색 또는 업데이트 동작을 호출 합니다.<br /><br /> 이 개체는 반환 된 액세스 하려면 시각적 컨트롤이 수단을 제공 **레코드 집합** 개체입니다.<br /><br /> **DataControl** 개체는 스크립팅 작업에 안전 합니다.|  
  
## <a name="see-also"></a>관련 항목:  
 [RDS 기본 사항](../../../ado/guide/remote-data-service/rds-fundamentals.md)   
 [RDS 시나리오](../../../ado/guide/remote-data-service/rds-scenario.md)   
 [RDS 자습서](../../../ado/guide/remote-data-service/rds-tutorial.md)   
 [RDS 사용량 및 보안](../../../ado/guide/remote-data-service/rds-usage-and-security.md)


