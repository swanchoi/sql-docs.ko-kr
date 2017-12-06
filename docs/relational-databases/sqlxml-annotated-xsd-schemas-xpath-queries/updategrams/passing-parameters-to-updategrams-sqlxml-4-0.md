---
title: "(SQLXML 4.0) Updategram에 매개 변수가 전달 | Microsoft Docs"
ms.custom: 
ms.date: 03/17/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: sqlxml
ms.reviewer: 
ms.suite: sql
ms.technology: dbe-xml
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- nullvalue attribute
- passing parameters [SQLXML]
- parameters [SQLXML]
- updategrams [SQLXML], passing parameters
- null values [SQLXML]
ms.assetid: 2354e6e7-1860-471f-8711-4e374c5a4ed2
caps.latest.revision: "30"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: b2de34ce8d8babc2232c3e82fdf88d164dbbff8e
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="passing-parameters-to-updategrams-sqlxml-40"></a>Updategram에 매개 변수 전달(SQLXML 4.0)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]Updategram은 템플릿이; 따라서 매개 변수 하 것을 전달할 수 있습니다. 템플릿에 매개 변수 전달에 대 한 자세한 내용은 참조 하십시오. [Updategram 보안 고려 사항 &#40; SQLXML 4.0 &#41; ](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/security/updategram-security-considerations-sqlxml-4-0.md).  
  
 Updategram을 사용하면 NULL을 매개 변수 값으로 전달할 수 있습니다. NULL 매개 변수 값을 전달 하려면 지정 된 **nullvalue** 특성입니다. 에 할당 된 값은 **nullvalue** 특성은 그런 다음 매개 변수 값으로 제공 됩니다. Updategram은 이 값을 NULL로 처리합니다.  
  
> [!NOTE]  
>  **\<sql:header >** 및  **\<updg:header >**를 지정 해야는 **nullvalue** 를 unqualified로 반면,  **\<updg:sync >**, 지정 된 **nullvalue** 를 qualified로 (예를 들어 **updg: nullvalue**).  
  
## <a name="examples"></a>예  
 다음 예에서는 사용 하 여 작업 예제를 만들려면에 지정 된 요구 사항을 충족 해야 [SQLXML 예 실행에 대 한 요구 사항](../../../relational-databases/sqlxml/requirements-for-running-sqlxml-examples.md)합니다.  
  
 Updategram 예를 사용하기 전에 다음 사항을 확인하십시오.  
  
-   이 예에서는 기본 매핑을 사용합니다. 즉, Updategram에 매핑 스키마가 지정되지 않습니다. 매핑 스키마를 사용 하는 updategram의 더 많은 예제를 참조 하세요. [Updategram &#40;에 주석이 추가 된 매핑 스키마 지정 SQLXML 4.0 &#41; ](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).  
  
### <a name="a-passing-parameters-to-an-updategram"></a>1. Updategram에 매개 변수 전달  
 이 예에서 Updategram은 HumanResources.Shift 테이블에 있는 직원의 성을 변경합니다. Updategram에 두 개의 매개 변수: ShiftID 근무조를 식별 하 고 이름을 고유 하 게 하는 데 사용 됩니다.  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header>  
  <updg:param name="ShiftID"/>  
  <updg:param name="Name" />  
</updg:header>  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="$ShiftID" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="$Name" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a>Updategram을 테스트하려면  
  
1.  위의 Updategram을 메모장에 복사하고 UpdategramWithParameters.xml로 파일에 저장합니다.  
  
2.  SQLXML 4.0 테스트 스크립트 (Sqlxml4test.vbs)를 준비 [SQLXML 4.0 쿼리 실행을 사용 하 여 ADO](../../../relational-databases/sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) 후 다음 줄을 추가 하 여 updategram을 실행 하는 `cmd.Properties("Output Stream").Value = outStream`:  
  
    ```  
    cmd.NamedParameters = True  
    ' CreateParameter arguments: Name, Type, Direction, Size, Value  
    cmd.Parameters.Append cmd.CreateParameter("@ShiftID",  2, 1,  0, 1)  
    cmd.Parameters.Append cmd.CreateParameter("@Name",   200, 1, 50, "New Name")  
    ```  
  
### <a name="b-passing-null-as-a-parameter-value-to-an-updategram"></a>2. NULL을 매개 변수 값으로 Updategram에 전달  
 Updategram을 실행하면 NULL로 설정할 매개 변수에 "isnull" 값이 할당됩니다. Updategram은 "isnulll" 매개 변수 값을 NULL로 변환하고 적절하게 처리합니다.  
  
 다음 Updategram에서는 직원 직함을 NULL로 설정합니다.  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header nullvalue="isnull" >  
  <updg:param name="EmployeeID"/>  
  <updg:param name="ManagerID" />  
</updg:header>  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Employee EmployeeID="$EmployeeID" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Employee ManagerID="$ManagerID" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a>Updategram을 테스트하려면  
  
1.  위의 Updategram을 메모장에 복사하고 UpdategramPassingNullvalues.xml로 파일에 저장합니다.  
  
2.  SQLXML 4.0 테스트 스크립트 (Sqlxml4test.vbs)를 준비 [SQLXML 4.0 쿼리 실행을 사용 하 여 ADO](../../../relational-databases/sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) 후 다음 줄을 추가 하 여 updategram을 실행 하는 `cmd.Properties("Output Stream").Value = outStream`:  
  
    ```  
    cmd.NamedParameters = True  
    ' CreateParameter arguments: Name, Type, Direction, Size, Value   
    cmd.Parameters.Append cmd.CreateParameter("@EmployeeID", 3, 1, 0, 1)  
    cmd.Parameters.Append cmd.CreateParameter("@ManagerID",  3, 1, 0, Null)  
    ```  
  
## <a name="see-also"></a>관련 항목:  
 [Updategram 보안 고려 사항 &#40; SQLXML 4.0 &#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/security/updategram-security-considerations-sqlxml-4-0.md)  
  
  