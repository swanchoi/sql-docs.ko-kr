---
title: "getPrecision 메서드 (SQLServerParameterMetaData) | Microsoft Docs"
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
- SQLServerParameterMetaData.getPrecision
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 8bd79484-bab6-423b-978f-d7ec7132ebeb
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 8c80beecc510fb5f2d4190839e8bc4ca1c95602c
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="getprecision-method-sqlserverparametermetadata"></a>getPrecision 메서드(SQLServerParameterMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  지정된 매개 변수의 자릿수를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public int getPrecision(int param)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *param*  
  
 **int** 매개 변수 인덱스를 나타내는입니다.  
  
## <a name="return-value"></a>반환 값  
 **int** 지정된 된 매개 변수의 전체 자릿수를 나타내는입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>주의  
 이 getPrecision 메서드는 java.sql.ParameterMetaData 인터페이스의 getPrecision 메서드에 의해 지정 됩니다.  
  
 숫자 형식의 경우 이 메서드는 자릿수를 가져옵니다. 문자 형식의 경우에는 최대 길이(문자 수)를 가져옵니다. 이진 형식의 경우에는 최대 길이(바이트)를 가져옵니다. 자릿수를 알 수 없으면 이 메서드는 "0"을 반환합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [SQLServerParameterMetaData 메서드](../../../connect/jdbc/reference/sqlserverparametermetadata-methods.md)   
 [SQLServerParameterMetaData 멤버](../../../connect/jdbc/reference/sqlserverparametermetadata-members.md)   
 [SQLServerParameterMetaData 클래스](../../../connect/jdbc/reference/sqlserverparametermetadata-class.md)  
  
  