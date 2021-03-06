---
title: SQLServerXAConnection 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 5ecb4bf1-b8d1-47cf-9cb1-7a18acc11ce2
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 1f2cc7956f36ee6fad113efd1cfe5afd5f58baff
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47782991"
---
# <a name="sqlserverxaconnection-class"></a>SQLServerXAConnection 클래스
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  분산(XA) 트랜잭션에 참여할 수 있는 JDBC 연결을 나타냅니다.  
  
 **패키지:** com.microsoft.sqlserver.jdbc  
  
 **확장:** [SQLServerPooledConnection](../../../connect/jdbc/reference/sqlserverpooledconnection-class.md)  
  
 **구현:** javax.sql.XAConnection  
  
## <a name="syntax"></a>구문  
  
```  
  
public class SQLServerXAConnection  
```  
  
## <a name="remarks"></a>Remarks  
 [SQLServerXAResource](../../../connect/jdbc/reference/sqlserverxaresource-class.md) 개체를 사용하여 SQLServerXAConnection 개체를 분산 트랜잭션에 참여시킬 수 있습니다. 트랜잭션 관리자를 중간 계층 서버를 일반적으로 일부 SQLServerXAResource 개체를 통해 SQLServerXAConnection 개체를 관리합니다.  
  
> [!NOTE]  
>  응용 프로그램 프로그래머는 일반적으로 이 인터페이스를 직접 사용하지 않습니다. 이 인터페이스는 중간 계층 서버에서 작업하는 트랜잭션 관리자가 주로 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerXAConnection 메서드](../../../connect/jdbc/reference/sqlserverxaconnection-members.md)   
 [JDBC 드라이버 API 참조](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
