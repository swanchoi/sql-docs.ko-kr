---
title: SQL Server 데이터베이스 단위 테스트 문제 해결 | Microsoft Docs
ms.custom:
- SSDT
ms.date: 02/09/2017
ms.prod: sql
ms.technology: ssdt
ms.reviewer: ''
ms.topic: conceptual
ms.assetid: cf4c9cd1-7e73-4c3b-922a-68b9247e7b33
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 45e9264284a690dee4a2938f56afb1fa9d9afed2
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47626331"
---
# <a name="troubleshooting-sql-server-database-unit-testing-issues"></a>SQL Server 데이터베이스 단위 테스트 문제 해결
데이터베이스에 대한 SQL Server 단위 테스트 작업을 수행할 때 이 항목에 포함되어 있는 문제가 발생할 수 있습니다.  
  
-   [단위 테스트를 실행할 때 단위 테스트 및 App.Config 변경 내용이 무시됨](#UnitTestingAndAppConfigChanges)  
  
-   [단위 테스트를 실행할 때 예기치 않은 대상으로 데이터베이스가 배포됨](#DatabaseDeploymentInUnitTests)  
  
-   [데이터베이스 단위 테스트를 실행할 때 제한 시간이 있음](#TimeoutsDuringUnitTests)  
  
## <a name="UnitTestingAndAppConfigChanges"></a>단위 테스트를 실행할 때 단위 테스트 및 App.Config 변경 내용이 무시됨  
테스트 프로젝트에서 App.Config 파일을 수정하는 경우 테스트 프로젝트를 다시 빌드해야만 해당 변경 내용이 적용됩니다. 이러한 변경 내용에는 **SQL Server 테스트 구성** 대화 상자를 사용하여 App.Config에 대해 변경한 내용이 포함됩니다. 테스트 프로젝트를 다시 빌드하지 않으면 단위 테스트를 실행할 때 변경 내용이 적용되지 않습니다.  
  
## <a name="DatabaseDeploymentInUnitTests"></a>단위 테스트를 실행할 때 예기치 않은 대상으로 데이터베이스가 배포됨  
단위 테스트를 실행할 때 데이터베이스 프로젝트의 데이터베이스를 배포하는 경우 데이터베이스는 단위 테스트 구성에 지정된 연결 문자열 정보를 사용하여 배포됩니다. 데이터베이스 프로젝트 디버그 속성에 지정된 연결 정보는 이 작업에 사용되지 않으므로 동일한 데이터베이스의 다른 인스턴스에 대해 SQL Server 단위 테스트를 실행할 수 있습니다.  
  
## <a name="TimeoutsDuringUnitTests"></a>데이터베이스 단위 테스트를 실행할 때 제한 시간이 있음  
제한 시간 때문에 데이터베이스 단위 테스트가 실패하는 경우 테스트 프로젝트에서 app.config 파일을 업데이트하여 제한 시간을 늘릴 수 있습니다. 연결 문자열에 정의된 연결 제한 시간은 단위 테스트가 서버에 연결할 때 기다리는 시간을 지정합니다. app.config 파일에 직접 정의해야 하는 명령 제한 시간은 단위 테스트가 Transact\-SQL 스크립트를 실행할 때 기다리는 시간을 지정합니다. 단위 테스트 실행 시간이 길어서 문제가 있는 경우에는 적절한 컨텍스트 요소에서 명령 제한 시간 값을 늘려 보십시오. 예를 들어 **PrivilegedContext** 요소에 대해 명령 제한 시간을 120초로 지정하려면 app.config를 다음과 같이 업데이트합니다.  
  
```  
<SqlUnitTesting_VS2010>  
    <DatabaseDeployment DatabaseProjectFileName="..\..\..\..\..\..\Visual Studio 2010\Projects\Database10\Database10\AdventureWorks.sqlproj"  
        Configuration="Debug" />  
    <DataGeneration ClearDatabase="true" />  
    <ExecutionContext Provider="System.Data.SqlClient" ConnectionString="Data Source=(LocalDB)\Projects;Initial Catalog=AdventureWorks_Test;Integrated Security=True;Pooling=False"  
        CommandTimeout="30" />  
    <PrivilegedContext Provider="System.Data.SqlClient" ConnectionString="Data Source=(LocalDB)\Projects;Initial Catalog=AdventureWorks_Test;Integrated Security=True;Pooling=False"  
        CommandTimeout="120" />  
</SqlUnitTesting_VS2010>  
```  
  
## <a name="see-also"></a>참고 항목  
[방법: 함수, 트리거 및 저장 프로시저에 대한 SQL Server 단위 테스트 만들기](../ssdt/how-to-create-unit-tests-for-functions-triggers-stored-procedures.md)  
[방법: SQL Server 단위 테스트 실행 구성](../ssdt/how-to-configure-sql-server-unit-test-execution.md)  
  
