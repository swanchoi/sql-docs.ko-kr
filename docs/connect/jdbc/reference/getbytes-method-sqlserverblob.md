---
title: getBytes 메서드 (SQLServerBlob) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerBlob.getBytes
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: bea1b810-b5c1-466d-bdc4-561468214632
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 098937df965d9573701657ef6c2ec580de09daf3
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47729741"
---
# <a name="getbytes-method-sqlserverblob"></a>getBytes 메서드(SQLServerBlob)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  BLOB 데이터를 바이트 배열로 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public byte[] getBytes(long pos,  
                       int length)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *pos*  
  
 시작 위치로, 0이 아니라 1부터 시작합니다.  
  
 *length*  
  
 가져올 데이터의 길이입니다.  
  
## <a name="return-value"></a>반환 값  
 요청된 데이터가 들어 있는 **byte** 배열입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 이 getBytes 메서드는 java.sql.Blob 인터페이스의 getBytes 메서드에 의해 지정됩니다.  
  
 null 또는 길이가 0인 BLOB이 있는 경우 위치 1에서 정확히 0바이트를 가져오려고 하면 빈 **byte** 배열(길이가 0인 바이트 배열)이 반환됩니다.  
  
 null 또는 길이가 0인 BLOB이 있는 경우 위치 1이 아닌 다른 위치에서 임의 길이의 바이트를 가져오려고 하면 위치 예외가 발생합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerBlob 메서드](../../../connect/jdbc/reference/sqlserverblob-methods.md)   
 [SQLServerBlob 멤버](../../../connect/jdbc/reference/sqlserverblob-members.md)   
 [SQLServerBlob 클래스](../../../connect/jdbc/reference/sqlserverblob-class.md)  
  
  
