---
title: updateDate 메서드(java.lang.String, java.sql.Date) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.updateDate (java.lang.String, java.sql.Date)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 4fbe9123-7365-4a8f-bbd5-dc2b16f1b231
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: f38e59a9724838b3ceaab8e09a843ec1cedc6fe4
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47833821"
---
# <a name="updatedate-method-javalangstring-javasqldate"></a>updateDate 메서드(java.lang.String, java.sql.Date)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  열 이름이 지정된 경우 지정된 열을 날짜 값으로 업데이트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public void updateDate(java.lang.String columnName,  
                       java.sql.Date x)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *columnName*  
  
 열 이름이 포함된 **문자열**입니다.  
  
 *x*  
  
 날짜 값입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 이 updateDate 메서드는 java.sql.ResultSet 인터페이스의 updateDate 메서드에 의해 지정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [updateDate 메서드 &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/updatedate-method-sqlserverresultset.md)   
 [SQLServerResultSet 멤버](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 클래스](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
