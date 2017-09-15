---
title: "getReference 메서드 (SQLServerDataSource) | Microsoft Docs"
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
- SQLServerDataSource.getReference
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: b3fb1a97-86ee-4977-adca-c35ae199dbb3
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 035149aed809ffd295ab53b4acf0f7fc41c59f7a
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="getreference-method-sqlserverdatasource"></a>getReference 메서드(SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이에 대 한 참조를 반환 [SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md) 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public javax.naming.Reference getReference()  
```  
  
## <a name="return-value"></a>반환 값  
 참조 개체입니다.  
  
## <a name="remarks"></a>주의  
 이 getReference 메서드는 javax.naming.Referenceable 인터페이스의 getReference 메서드에 의해 지정 됩니다.  
  
 이전에 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] JDBC 드라이버 3.0에서는 SQLServerDataSource 개체에 SQLServerDataSource.setTrustStorePassword가 호출 하는 경우 암호에에서 제공 됩니다 하는 데 사용할 개체 SQLServerDataSource.getReference에서 반환 되는 개체 추가 연결을 확인 합니다. JDBC 드라이버 3.0에서는 SQLServerDataSource.getReference에서 반환되는 개체에 암호를 설정해야 이 개체를 사용하여 연결을 만들 수 있습니다.  
  
 또한 데이터 원본 속성을 바인딩하기 전에 SQLServerDataSource.setTrustStorePassword를 설정할 경우, 연결을 가져오기 전에 SQLServerDataSource.setTrustStorePassword를 호출해야 합니다. 예:  
  
```  
ctx = new InitialContext(System.getProperties());  
  
SQLServerDataSource ds1 = (SQLServerDataSource) ctx.lookup(jndiName);  
  
ds1.setTrustStorePassword("XXXXX");  
Connection con = ds1.getConnection("user", "XXXXXX");  
  
ctx.rebind(jndiName, ds1);  
SQLServerDataSource ds2 = (SQLServerDataSource) ctx.lookup(jndiName);  
ds2.setTrustStorePassword("XXXXX");   // reset the truststore password  
con = ds2.getConnection("user", "XXXXXX");   // provide userid and password again  
```  
  
## <a name="see-also"></a>관련 항목:  
 [SQLServerDataSource 멤버](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource 클래스](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  