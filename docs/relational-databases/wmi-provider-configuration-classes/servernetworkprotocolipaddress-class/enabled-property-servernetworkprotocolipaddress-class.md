---
title: "Enabled 속성 (ServerNetworkProtocolIpAddress 클래스) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: wmi
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: reference
apiname: Enabled Property (ServerNetworkProtocolIpAddress Class)
apilocation: sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords: Enabled property
ms.assetid: 870fd4d0-6c77-462a-b480-d42eb044b2e7
caps.latest.revision: "14"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 755178e6e89d380bc1ad6d38b755a9d6194cbfe5
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="enabled-property-servernetworkprotocolipaddress-class"></a>Enabled 속성(ServerNetworkProtocolIpAddress 클래스)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]IP 주소를 사용할 수 있는지 여부를 지정 하는 부울 속성을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object.Enabled [= value]  
```  
  
## <a name="parts"></a>부분  
 *개체*  
 A [ServerNetworkProtocolIPAdress 클래스](../../../relational-databases/wmi-provider-configuration-classes/servernetworkprotocolipaddress-class/servernetworkprotocolipaddress-class.md) 인스턴스의 네트워크 프로토콜에 대 한 IP 주소를 나타내는 개체 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]합니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 IP 주소를 사용할 수 있는지 여부를 지정 하는 부울 값: **true** IP 주소를 사용 하는 경우 또는 **false** IP 주소를 사용 하지 않도록 설정 합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [서버 네트워크 프로토콜 및 네트워크 라이브러리 구성](http://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)  
  
  