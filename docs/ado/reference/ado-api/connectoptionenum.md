---
title: ConnectOptionEnum | Microsoft Docs
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- ConnectOptionEnum
helpviewer_keywords:
- ConnectOptionEnum enumeration [ADO]
ms.assetid: bff07eeb-dee3-4e4e-9b2d-d56061ea744d
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 582f85d3ce45071cd283f05f5d595e10b5d1614c
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="connectoptionenum"></a>ConnectOptionEnum
지정 여부는 [열려](../../../ado/reference/ado-api/open-method-ado-connection.md) 의 메서드는 [연결](../../../ado/reference/ado-api/connection-object-ado.md) 연결 (동기) 또는 하기 전에 개체를 반환 해야 (비동기).  
  
|상수|값|Description|  
|--------------|-----------|-----------------|  
|**adAsyncConnect**|16|비동기적으로 연결을 엽니다. [ConnectComplete](../../../ado/reference/ado-api/connectcomplete-and-disconnect-events-ado.md) 이벤트는 연결을 사용할 수를 결정 하는 데 사용 수 있습니다.|  
|**adConnectUnspecified**|-1|기본. 동기적으로 연결을 엽니다.|  
  
## <a name="adowfc-equivalent"></a>해당 하는 ADO/WFC  
 패키지에 대 한 **com.ms.wfc.data**  
  
|상수|  
|--------------|  
|AdoEnums.ConnectOption.ASYNCCONNECT|  
|AdoEnums.ConnectOption.CONNECTUNSPECIFIED|  
  
## <a name="applies-to"></a>적용 대상  
 [Open 메서드(ADO 연결)](../../../ado/reference/ado-api/open-method-ado-connection.md)