---
title: "executeQuery 메서드 () | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- SQLServerPreparedStatement.executeQuery ()
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 1d90407f-16df-4ba2-b4a5-47d5751e1d7c
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: c6d924934ae94acc07fe3cce71a58204cd16ab0c
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="executequery-method-"></a>executeQuery 메서드()
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 SQL 쿼리를 실행 [SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) 개체를 반환 된 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 쿼리에 의해 생성 되는 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public java.sql.ResultSet executeQuery()  
```  
  
## <a name="return-value"></a>반환 값  
 
          SQLServerResultSet 개체입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>주의  
 이 executeQuery 메서드는 java.sql.PreparedStatement 인터페이스의 executeQuery 메서드에 의해 지정 됩니다.  
  
## <a name="see-also"></a>관련 항목:  
 [executeQuery 메서드 &#40; SQLServerPreparedStatement &#41;](../../../connect/jdbc/reference/executequery-method-sqlserverpreparedstatement.md)   
 [SQLServerPreparedStatement 멤버](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)   
 [SQLServerPreparedStatement 클래스](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md)  
  
  