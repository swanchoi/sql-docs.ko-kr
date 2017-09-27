---
title: "position 메서드 (java.sql.Blob, long) | Microsoft Docs"
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
- SQLServerBlob.position (java.sql.Blob.long)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: ebd005e5-f6c5-4789-87f9-d2fdacd35060
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: c7c3f740409e7a8d7a5cbc8989ae8aa074703305
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="position-method-javasqlblob-long"></a>position 메서드(java.sql.Blob, long)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  지정된 패턴과 시작 인덱스에 따라 BLOB에서 지정된 패턴이 있는 위치를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public long position(java.sql.Blob pattern,  
                     long start)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *패턴*  
  
 검색할 패턴입니다.  
  
 *시작*  
  
 검색할 시작 인덱스입니다.  
  
## <a name="return-value"></a>반환 값  
 A **긴** 위치 패턴이 발견 된 값 또는 찾을 수 없는 경우-1입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>주의  
 이 위치 메서드는 java.sql.Blob 인터페이스의 위치 메서드에 의해 지정 됩니다.  
  
## <a name="see-also"></a>관련 항목:  
 [방법 &#40; 배치 SQLServerBlob &#41;](../../../connect/jdbc/reference/position-method-sqlserverblob.md)   
 [SQLServerBlob 메서드](../../../connect/jdbc/reference/sqlserverblob-methods.md)   
 [SQLServerBlob 멤버](../../../connect/jdbc/reference/sqlserverblob-members.md)   
 [SQLServerBlob 클래스](../../../connect/jdbc/reference/sqlserverblob-class.md)  
  
  