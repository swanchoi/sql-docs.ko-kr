---
title: setClob 메서드(java.lang.String, java.io.Reader, long) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: bc9fddea-134e-4440-ba54-a1f74bb40c46
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 18452e922be67e0656ef52b0117552dad0c661c7
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47654949"
---
# <a name="setclob-method-javalangstring-javaioreader-long"></a>setClob 메서드(java.lang.String, java.io.Reader, long)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  지정된 매개 변수를 지정된 문자 길이의 지정된 Reader 개체로 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public final void setClob(java.lang.String parameterName,  
            java.io.Reader value,  
            long length)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *parameterName*  
  
 매개 변수 이름이 들어 있는 **문자열**입니다.  
  
 *value*  
  
 판독기 개체입니다.  
  
 *length*  
  
 스트림의 문자 수를 나타내는 **long**입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 이 setClob 메서드는 java.sql.CallableStatement 인터페이스의 setClob 메서드에 의해 지정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [setClob 메서드(SQLServerCallableStatement)](../../../connect/jdbc/reference/setclob-method-sqlservercallablestatement.md)   
 [SQLServerCallableStatement 멤버](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)  
  
  
