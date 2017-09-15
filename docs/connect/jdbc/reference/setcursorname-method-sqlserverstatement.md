---
title: "setCursorName 메서드 (SQLServerStatement) | Microsoft Docs"
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
- SQLServerStatement.setCursorName
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 3f3ec4f2-103a-4e16-9206-c5bd8639f946
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 501440dec2f47c4f3f272ebde7f6cbd01642e377
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="setcursorname-method-sqlserverstatement"></a>setCursorName 메서드(SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  SQL 커서 이름을 이후 실행 메서드에 사용될 지정된 문자열로 설정합니다.  
  
> [!NOTE]  
>  이 메서드는 현재 지원 되지 않습니다는 [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]합니다. 이 메서드를 호출해도 아무 작업도 수행되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public final void setCursorName(java.lang.String name)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *name*  
  
 A **문자열** 커서 이름이 들어 있는입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>주의  
 이 setCursorName 메서드는 java.sql.Statement 인터페이스의 setCursorName 메서드에 의해 지정 됩니다.  
  
## <a name="see-also"></a>관련 항목:  
 [SQLServerStatement 멤버](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement 클래스](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  