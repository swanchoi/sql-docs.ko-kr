---
title: sqlsrv_has_rows | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- API Reference, sqlsrv_has_rows
- sqlsrv_has_rows
ms.assetid: 4da7f640-cf12-409f-9e00-95b30a8d5e17
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 9cc449b6aa47024d9d38af1870dfa370f8a59896
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47772771"
---
# <a name="sqlsrvhasrows"></a>sqlsrv_has_rows
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

결과 집합에 하나 이상의 행이 있는지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
sqlsrv_has_rows( resource $stmt )  
```  
  
#### <a name="parameters"></a>매개 변수  
*$stmt*: 실행된 문입니다.  
  
## <a name="return-value"></a>반환 값  
결과 집합에 행이 있는 경우 반환 값은 **true**입니다. 행이 없거나 함수 호출이 실패하는 경우 반환 값은 **false**입니다.  
  
## <a name="example"></a>예제  
  
```  
<?php  
   $server = "server_name";  
   $conn = sqlsrv_connect( $server, array( 'Database' => 'Northwind' ) );  
  
   $stmt = sqlsrv_query( $conn, "select * from orders where CustomerID = 'VINET'" , array());  
  
   if ($stmt !== NULL) {  
      $rows = sqlsrv_has_rows( $stmt );  
  
      if ($rows === true)  
         echo "\nthere are rows\n";  
      else   
         echo "\nno rows\n";  
   }  
?>  
```  
  
## <a name="see-also"></a>참고 항목  
[SQLSRV 드라이버 API 참조](../../connect/php/sqlsrv-driver-api-reference.md)  
  
