---
title: setCharacterStream 메서드(int, java.io.Reader, long) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: cb6ac7f5-81ae-4cb7-87c8-cbee40d278c5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 4ce5694d1f594c69e6f7f72cc7abb497e65bf250
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47732641"
---
# <a name="setcharacterstream-method-int-javaioreader-long"></a>setCharacterStream 메서드(int, java.io.Reader, long)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  지정된 매개 변수를 지정된 문자 길이의 java.io.Reader 개체로 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public final void setCharacterStream(int parameterIndex,  
                                    java.io.Reader reader,  
                                    long length)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *된*  
  
 매개 변수 번호를 나타내는 **int**입니다.  
  
 *reader*  
  
 유니코드 데이터가 들어 있는 java.io.Reader 개체입니다.  
  
 *length*  
  
 스트림의 문자 수를 나타내는 **long**입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 이 setCharacterStream 메서드는 java.sql.PreparedStatement 인터페이스의 setCharacterStream 메서드에 의해 지정 됩니다.  
  
 스트림의 길이가 *length* 매개 변수에 지정된 길이와 다르면 행이 업데이트되거나 삽입될 때 JDBC 드라이버에서 예외가 발생합니다.  
  
 스트림의 길이를 알 수 없으면 *length* 매개 변수는 드라이버에서 스트림의 길이에 상관없이 스트림을 허용해야 함을 나타내는 -1로 설정될 수 있습니다. sqljdbc4.jar을 사용하면 응용 프로그램에서 길이를 알 수 없는 스트림에서 열을 업데이트하려고 할 때 JDBC 4.0 메서드 [setCharacterStream 메서드 &#40;int, java.io.Reader&#41;](../../../connect/jdbc/reference/setcharacterstream-method-int-java-io-reader.md)를 사용하는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목  
 [setCharacterStream 메서드&#40;SQLServerPreparedStatement&#41;](../../../connect/jdbc/reference/setcharacterstream-method-sqlserverpreparedstatement.md)   
 [SQLServerPreparedStatement 멤버](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)  
  
  
