---
title: SetEnable 메서드 (ServerNetworkProtocolIPAddress 클래스) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetEnable Method (ServerNetworkProtocolIPAddress Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEnable method
ms.assetid: baa86deb-95dd-416f-b2c7-cec1dfb91ab4
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: d4c542aa1491710d49ec4c24c027e69f2eef24a9
ms.sourcegitcommit: 334cae1925fa5ac6c140e0b2c38c844c477e3ffb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/13/2018
ms.locfileid: "53349174"
---
# <a name="setenable-method-servernetworkprotocolipaddress-class"></a>SetEnable 메서드(ServerNetworkProtocolIPAddress 클래스)
  IP 주소를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object  
.SetEnable()  
  
```  
  
## <a name="parts"></a>부분  
 *object*  
 A [ServerNetworkProtocolIPAdress 클래스](servernetworkprotocolipaddress-class.md) 인스턴스의 네트워크 프로토콜에 대 한 IP 주소를 나타내는 개체입니다 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]합니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 `uint32` 값으로, 0은 서비스가 수정되었음을 나타내고 1은 요청이 지원되지 않음을 나타내며 다른 모든 숫자는 오류를 나타냅니다.  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>관련 항목  
 [서버 네트워크 프로토콜 및 네트워크 라이브러리 구성](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)  
  
  
