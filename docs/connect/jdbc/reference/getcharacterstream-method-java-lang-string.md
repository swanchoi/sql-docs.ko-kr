---
title: getCharacterStream 메서드 (java.lang.String) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.getCharacterStream (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: cdddc572-05c1-480d-b3e5-28270001575c
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 3f7bb4fd480eef5351a5727ac712a9a65d60c236
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47701921"
---
# <a name="getcharacterstream-method-javalangstring"></a>getCharacterStream 메서드(java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 개체의 현재 행에서 지정된 열 이름의 값을 java.io.Reader 개체로 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public java.io.Reader getCharacterStream(java.lang.String columnName)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *columnName*  
  
 열 이름이 포함된 **문자열**입니다.  
  
## <a name="return-value"></a>반환 값  
 판독기 개체입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 이 getCharacterStream 메서드는 java.sql.ResultSet 인터페이스의 getCharacterStream 메서드에 의해 지정 됩니다.  
  
 이 메서드는 nchar, nvarchar, nvarchar(max) 및 ntext와 같은 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 유니코드 문자 데이터 형식만 읽습니다. ASCII 문자 형식을 비롯한 다른 모든 데이터 형식에서는 예외가 발생합니다. ASCII 데이터 형식을 읽으려면 [getAsciiStream](../../../connect/jdbc/reference/getasciistream-method-sqlserverresultset.md) 메서드를 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [getCharacterStream 메서드&#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/getcharacterstream-method-sqlserverresultset.md)   
 [SQLServerResultSet 멤버](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 클래스](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
