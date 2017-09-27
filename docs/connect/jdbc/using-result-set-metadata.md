---
title: "결과 사용 하 여 메타 데이터 설정 | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e37529a-30db-48c8-b90a-ae9657d0f6b0
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 98d595320ae164690712f1a5541ec304488e0ca0
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="using-result-set-metadata"></a>결과 집합 메타데이터 사용
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  결과 집합에 포함 된 열에 대 한 정보를 쿼리 하는 [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] 구현 하는 [SQLServerResultSetMetaData](../../connect/jdbc/reference/sqlserverresultsetmetadata-class.md) 클래스입니다. 이 클래스에는 단일 값 형태로 정보를 반환하는 다양한 메서드가 들어 있습니다.  
  
 SQLServerResultSetMetaData 개체를 만들려면 사용할 수 있습니다는 [getMetaData](../../connect/jdbc/reference/getmetadata-method-sqlserverresultset.md) 의 메서드는 [SQLServerResultSet](../../connect/jdbc/reference/sqlserverresultset-class.md) 클래스입니다.  
  
 다음 예에서는 열린 연결에에서는 [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)] 예제 데이터베이스는 함수에 전달 된, SQLServerResultSet 클래스의 getMetaData 메서드를 사용 하 여 SQLServerResultSetMetaData 개체와의 다음 다양 한 메서드를 반환 하는 SQLServerResultSetMetaData 개체는 결과 집합에 포함 된 열 이름 및 데이터 형식에 대 한 정보를 표시 하는 데 사용 됩니다.  
  
 [!code[JDBC#UsingResultSetMetaData1](../../connect/jdbc/codesnippet/Java/using-result-set-metadata_1.java)]  
  
## <a name="see-also"></a>관련 항목:  
 [JDBC 드라이버로 메타데이터 처리](../../connect/jdbc/handling-metadata-with-the-jdbc-driver.md)  
  
  