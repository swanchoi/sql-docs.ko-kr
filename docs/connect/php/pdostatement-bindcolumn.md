---
title: 'Pdostatement:: Bindcolumn | Microsoft Docs'
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbdcea53-d23d-4769-89a0-95c7cf4d5390
caps.latest.revision: 14
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 5099dc820bd3772b2cbd4148d03bc84fb1b757e5
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="pdostatementbindcolumn"></a>PDOStatement::bindColumn
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

결과 집합의 열에 변수를 바인딩합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
bool PDOStatement::bindColumn($column, &$param[, $type[, $maxLen[, $driverdata ]]] );  
```  
  
#### <a name="parameters"></a>매개 변수  
$*열*: 열 (인덱스 1부터 시작) 또는 결과 집합의 열 이름입니다 (혼합된) 수입니다.  
  
&$*param*: PHP 변수는 열이 바인딩될 (혼합된) 이름입니다.  
  
$*형식*: pdo:: PARAM_ * 상수로 표현 된 매개 변수의 선택적 데이터 형식입니다.  
  
$*maxLen*: Microsoft Drivers for PHP for SQL Server에서 사용되지 않는 선택적 정수입니다.  
  
$*driverdata*: 선택적 혼합 매개 변수는 드라이버에 대 한 합니다. 예를 들어 PDO::SQLSRV_ENCODING_UTF8을 지정하여 UTF-8로 인코드된 문자열로 변수에 열을 바인딩할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
성공하면 TRUE이고, 그렇지 않으면 FALSE입니다.  
  
## <a name="remarks"></a>주의  
PDO 지원이 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]의 버전 2.0에 추가되었습니다.  
  
## <a name="example"></a>예제  
이 예제에서는 변수를 결과 집합의 열에 바인딩하는 방법을 보여 줍니다.  
  
```  
<?php  
$database = "AdventureWorks";  
$server = "(local)";  
$conn = new PDO( "sqlsrv:server=$server ; Database = $database", "", "");  
  
$query = "SELECT Title, FirstName, EmailAddress FROM Person.Contact where LastName = 'Estes'";  
$stmt = $conn->prepare($query);  
$stmt->execute();  
  
$stmt->bindColumn('EmailAddress', $email);  
while ( $row = $stmt->fetch( PDO::FETCH_BOUND ) ){  
   echo "$email\n";  
}  
?>  
```  
  
## <a name="see-also"></a>참고 항목  
[PDOStatement 클래스](../../connect/php/pdostatement-class.md)  
[PDO](http://go.microsoft.com/fwlink/?LinkID=187441)  
  
