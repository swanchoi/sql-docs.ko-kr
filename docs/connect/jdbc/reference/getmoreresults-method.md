---
title: getMoreResults 메서드 () | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerStatement.getMoreResults ()
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: df89db50-0b2f-4094-820a-30be25ad72fe
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: f2a0b2994bf377610574efbd5c3ff78b0d55035d
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47718371"
---
# <a name="getmoreresults-method-"></a>getMoreResults 메서드()
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 [SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md) 개체의 다음 결과로 이동합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public final boolean getMoreResults()  
```  
  
## <a name="return-value"></a>반환 값  
 반환된 결과가 결과 집합이면 **true**이고, 그렇지 않으면 **false**입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 이 getMoreResults 메서드는 java.sql.Statement 인터페이스의 getMoreResults 메서드에 의해 지정 됩니다.  
  
 getMoreResults 메서드를 호출하면 [getResultSet](../../../connect/jdbc/reference/getresultset-method-sqlserverstatement.md) 메서드를 사용하여 가져온 현재 열려 있는 결과 집합 개체가 암시적으로 닫힙니다.  
  
## <a name="see-also"></a>참고 항목  
 [getMoreResults 메서드(SQLServerStatement)](../../../connect/jdbc/reference/getmoreresults-method-sqlserverstatement.md)   
 [SQLServerStatement 멤버](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement 클래스](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
