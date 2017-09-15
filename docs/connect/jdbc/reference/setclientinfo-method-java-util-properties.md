---
title: "setClientInfo 메서드 (java.util.Properties) | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2a8ec0b-40a2-44d1-90d9-a810d4132e56
caps.latest.revision: 19
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: d3484e23a4f7e8997d1bfa21a34a4cdf6f6dee71
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="setclientinfo-method-javautilproperties"></a>setClientInfo 메서드(java.util.Properties)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  연결의 클라이언트 정보 속성에 대한 값을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public void setClientInfo (java.util.Properties properties)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *속성*  
  
 설정할 클라이언트 정보 속성의 목록을 포함 하는 속성 개체입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>주의  
 이 setClientInfo 메서드는 java.sql.Connection 인터페이스의 setClientInfo 메서드에 의해 지정 됩니다.  
  
 [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] 클라이언트 정보 속성을 지원 하지 않습니다. 이 메서드는 경우 경고를 생성 된 *속성* 입력된 매개 변수가 빈 속성 집합을 참조 하지 않습니다. 즉, 이 메서드는 응용 프로그램에서 설정하려고 하는 속성에 대한 경고를 생성합니다. 응용 프로그램 사용 해야 [getWarnings](../../../connect/jdbc/reference/getwarnings-method-sqlserverconnection.md) 의 메서드는 [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) 클래스 각 경고를 검색 합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [setClientInfo 메서드 &#40; SQLServerConnection &#41;](../../../connect/jdbc/reference/setclientinfo-method-sqlserverconnection.md)   
 [SQLServerConnection 멤버](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection 클래스](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  