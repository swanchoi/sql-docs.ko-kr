---
title: setHoldability 메서드 (SQLServerConnection) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerConnection.setHoldability
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 552eebd0-4c38-43f0-961f-35244f99109b
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 37181dfc2a2fa7b3e166d00e83130c2758e28533
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47638651"
---
# <a name="setholdability-method-sqlserverconnection"></a>setHoldability 메서드(SQLServerConnection)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 [SQLServerSavepoint](../../../connect/jdbc/reference/sqlserversavepoint-class.md) 개체를 사용하여 만든 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 개체의 유지 기능을 변경합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public void setHoldability(int nNewHold)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *nNewHold*  
  
 다음 유지 기능 수준 중 하나가 들어 있는 **int** 값입니다.  
  
 HOLD_CURSORS_OVER_COMMIT  
  
 CLOSE_CURSORS_AT_COMMIT  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 이 setHoldability 메서드는 java.sql.Connection 인터페이스의 setHoldability 메서드에 의해 지정 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerConnection 멤버](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection 클래스](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
