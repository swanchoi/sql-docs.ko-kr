---
title: 'Pdostatement:: Fetch | Microsoft Docs'
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4368e362-5bda-4da1-8462-33714683c39f
caps.latest.revision: 19
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 787f84791c12ceada7e3e4598b3fae387e51430b
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="pdostatementfetch"></a>PDOStatement::fetch
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

결과 집합에서 행을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
mixed PDOStatement::fetch ([ $fetch_style[, $cursor_orientation[, $cursor_offset]]] );  
```  
  
#### <a name="parameters"></a>매개 변수  
$*fetch_style*: 행 데이터의 형식을 지정 하는 선택적 (정수) 기호입니다. $에 대 한 가능한 값의 목록에 대 한 설명 섹션을 참조 하십시오.*fetch_style*합니다. 기본값은 PDO::FETCH_BOTH입니다. $*fetch_style* 페치에서 재정의 합니다 $*fetch_style* pdo:: query 메서드에서 지정 합니다.  
  
$*cursor_orientation*: prepare 문이 지정 하는 경우 검색할 행을 나타내는 선택적 (정수) 기호 `PDO::ATTR_CURSOR => PDO::CURSOR_SCROLL`합니다. $에 대 한 가능한 값의 목록에 대 한 설명 섹션을 참조 하십시오.*cursor_orientation*합니다. 스크롤 가능 커서를 사용하는 샘플은 [PDO::prepare](../../connect/php/pdo-prepare.md) 를 참조하세요.  
  
$*cursor_offset*: 경우 페치할 행을 지정 하는 선택적 (정수) 기호 $*cursor_orientation* 인 또는 FETCH_ORI_REL 및 pdo:: ATTR_CURSOR가 pdo:: CURSOR_SCROLL 합니다.  
  
## <a name="return-value"></a>반환 값  
행 또는 false를 반환하는 혼합 값입니다.  
  
## <a name="remarks"></a>주의  
페치가 호출되면 커서가 자동으로 이동합니다. 다음 표에서 가능한 $ 목록이*fetch_style* 값입니다.  
  
|$*fetch_style*|Description|  
|-------------------|---------------|  
|PDO::FETCH_ASSOC|열 이름으로 인덱싱된 배열을 지정합니다.|  
|PDO::FETCH_BOTH|열 이름 및 0부터 시작하는 순서에 따라 인덱싱된 배열을 지정합니다. 기본값입니다.|  
|PDO::FETCH_BOUND|True를 반환하고 [PDOStatement::bindColumn](../../connect/php/pdostatement-bindcolumn.md)에서 지정한 대로 값을 할당합니다.|  
|PDO::FETCH_CLASS|인스턴스를 만들고 열을 명명된 속성에 매핑합니다.<br /><br />페치를 호출하기 전에 [PDOStatement::setFetchMode](../../connect/php/pdostatement-setfetchmode.md) 를 호출합니다.|  
|PDO::FETCH_INTO|요청된 클래스의 인스턴스를 새로 고칩니다.<br /><br />페치를 호출하기 전에 [PDOStatement::setFetchMode](../../connect/php/pdostatement-setfetchmode.md) 를 호출합니다.|  
|PDO::FETCH_LAZY|액세스 중 변수 이름을 만들고 명명되지 않은 개체를 만듭니다.|  
|PDO::FETCH_NUM|0부터 시작하는 열 순서로 인덱싱된 배열을 지정합니다.|  
|PDO::FETCH_OBJ|명명되지 않은 개체를 열 이름에 매핑되는 속성 이름으로 지정합니다.|  
  
커서가 결과 집합 끝에 있고(마지막 행이 검색되고 커서가 결과 집합의 경계를 지나 이동) 커서가 정방향 전용인 경우(PDO::ATTR_CURSOR = PDO::CURSOR_FWDONLY) 후속 페치 호출이 실패합니다.  
  
커서가 스크롤 가능한 경우(PDO::ATTR_CURSOR = PDO::CURSOR_SCROLL) 페치는 결과 집합 경계 내에서 커서를 이동합니다. 다음 표에서 가능한 $ 목록이*cursor_orientation* 값입니다.  
  
|$*cursor_orientation*|Description|  
|--------------------------|---------------|  
|PDO::FETCH_ORI_NEXT|다음 행을 검색합니다. 기본값입니다.|  
|PDO::FETCH_ORI_PRIOR|이전 행을 검색합니다.|  
|PDO::FETCH_ORI_FIRST|첫 번째 행을 검색합니다.|  
|PDO::FETCH_ORI_LAST|마지막 행을 검색합니다.|  
|인, *num*|$에서 요청 된 행을 검색*cursor_offset* 행 번호입니다.|  
|Fetch_ori_rel, *num*|$에서 요청 된 행을 검색*cursor_offset* 현재 위치의 상대 위치로 합니다.|  
  
$ 지정 된 값*cursor_offset* 또는 $*cursor_orientation* 결과 집합 경계를 벗어난 위치에 결과 페치가 실패 합니다.  
  
PDO 지원이 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]의 버전 2.0에 추가되었습니다.  
  
## <a name="example"></a>예제  
  
```  
<?php  
   $server = "(local)";  
   $database = "AdventureWorks";  
   $conn = new PDO( "sqlsrv:server=$server ; Database = $database", "", "");  
  
   print( "\n---------- PDO::FETCH_CLASS -------------\n" );  
   $stmt = $conn->query( "select * from HumanResources.Department order by GroupName" );  
  
   class cc {  
      function __construct( $arg ) {  
         echo "$arg";  
      }  
  
      function __toString() {  
         return $this->DepartmentID . "; " . $this->Name . "; " . $this->GroupName;  
      }  
   }  
  
   $stmt->setFetchMode(PDO::FETCH_CLASS, 'cc', array( "arg1 " ));  
   while ( $row = $stmt->fetch(PDO::FETCH_CLASS)) {   
      print($row . "\n");   
   }  
  
   print( "\n---------- PDO::FETCH_INTO -------------\n" );  
   $stmt = $conn->query( "select * from HumanResources.Department order by GroupName" );  
   $c_obj = new cc( '' );  
  
   $stmt->setFetchMode(PDO::FETCH_INTO, $c_obj);  
   while ( $row = $stmt->fetch(PDO::FETCH_INTO)) {   
      echo "$c_obj\n";  
   }  
  
   print( "\n---------- PDO::FETCH_ASSOC -------------\n" );  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $result = $stmt->fetch( PDO::FETCH_ASSOC );  
   print_r( $result );  
  
   print( "\n---------- PDO::FETCH_NUM -------------\n" );  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $result = $stmt->fetch( PDO::FETCH_NUM );  
   print_r ($result );  
  
   print( "\n---------- PDO::FETCH_BOTH -------------\n" );  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $result = $stmt->fetch( PDO::FETCH_BOTH );  
   print_r( $result );  
  
   print( "\n---------- PDO::FETCH_LAZY -------------\n" );  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $result = $stmt->fetch( PDO::FETCH_LAZY );  
   print_r( $result );  
  
   print( "\n---------- PDO::FETCH_OBJ -------------\n" );  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $result = $stmt->fetch( PDO::FETCH_OBJ );  
   print $result->Name;  
   print( "\n \n" );  
  
   print( "\n---------- PDO::FETCH_BOUND -------------\n" );  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $stmt->bindColumn('Name', $name);  
   $result = $stmt->fetch( PDO::FETCH_BOUND );  
   print $name;  
   print( "\n \n" );  
?>  
```  
  
## <a name="see-also"></a>참고 항목  
[PDOStatement 클래스](../../connect/php/pdostatement-class.md)  
[PDO](http://go.microsoft.com/fwlink/?LinkID=187441)  
  
