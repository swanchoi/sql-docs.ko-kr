---
title: "사용자, 역할 및 로그인 관리 | Microsoft Docs"
ms.custom: 
ms.date: 08/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: smo
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- logins [SMO]
- roles [SMO]
- users [SMO]
ms.assetid: 74e411fa-74ed-49ec-ab58-68c250f2280e
caps.latest.revision: "45"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: eeda3dc5a30031545b7a6e500c378d6d4c190a6c
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="managing-users-roles-and-logins"></a>사용자, 역할 및 로그인 관리
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]SMO에서 로그인으로 표시 됩니다는 <xref:Microsoft.SqlServer.Management.Smo.Login> 개체입니다. [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]에 로그온이 있으면 서버 역할에 추가할 수 있습니다. 서버 역할으로 표시 됩니다는 <xref:Microsoft.SqlServer.Management.Smo.ServerRole> 개체입니다. 데이터베이스 역할은 <xref:Microsoft.SqlServer.Management.Smo.DatabaseRole> 개체로 표시되고 응용 프로그램 역할은 <xref:Microsoft.SqlServer.Management.Smo.ApplicationRole> 개체로 표시됩니다.  
  
 연결 된 서버 수준 권한을의 속성으로 표시 되는 <xref:Microsoft.SqlServer.Management.Smo.ServerPermission> 개체입니다. 개별 로그온 계정에 대해 서버 수준 권한을 부여, 거부 또는 취소할 수 있습니다.  
  
 모든 <xref:Microsoft.SqlServer.Management.Smo.Database> 개체에는 <xref:Microsoft.SqlServer.Management.Smo.UserCollection> 데이터베이스의 모든 사용자를 지정 하는 개체입니다. 각 사용자는 로그온과 연관되어 있습니다. 하나의 로그온은 둘 이상의 데이터베이스의 사용자들과 연관될 수 있습니다. <xref:Microsoft.SqlServer.Management.Smo.Login> 개체의 <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> 메서드를 사용 하는 로그온과 연관 된 모든 데이터베이스의 모든 사용자를 나열할 수 있습니다. 또는 <xref:Microsoft.SqlServer.Management.Smo.User> 개체의 <xref:Microsoft.SqlServer.Management.Smo.Login> 속성이 사용자와 연관되어 있는 로그온을 지정합니다.  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]데이터베이스에는 특정 작업을 수행 하는 사용자 수 있는 데이터베이스 수준 권한 집합을 지정 하는 역할도 포함 합니다. 서버 역할과 달리 데이터베이스 역할은 고정되지 않아서 생성, 수정 및 제거할 수 있습니다. 대량 관리를 위해 데이터베이스 역할에 권한 및 사용자를 할당할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제를 사용하려면 응용 프로그램을 만들 프로그래밍 환경, 프로그래밍 템플릿 및 프로그래밍 언어를 선택해야 합니다. 자세한 내용은 참조 [만들기 Visual C &#35; Visual Studio.NET에서에서 SMO 프로젝트](../../../relational-databases/server-management-objects-smo/how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md)합니다.  
  
## <a name="enumerating-logins-and-associated-users-in-visual-c"></a>Visual C#에서 로그인 및 연관된 사용자 열거  
 데이터베이스의 모든 사용자는 로그온과 연관되어 있습니다. 로그온은 둘 이상의 데이터베이스의 사용자들과 연관될 수 있습니다. 코드 예제는 <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> 개체의 <xref:Microsoft.SqlServer.Management.Smo.Login> 메서드를 호출하여 로그온과 연관된 데이터베이스 사용자를 모두 나열하는 방법을 보여 줍니다. 이 예에서는 만듭니다 로그온과 사용자에는 [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] 열거할 매핑 정보가 있는지 확인 하기 위해 데이터베이스.  
  
```csharp  
{   
Server srv = new Server();   
//Iterate through each database and display.   
  
foreach ( Database db in srv.Databases) {   
   Console.WriteLine("========");   
   Console.WriteLine("Login Mappings for the database: " + db.Name);   
   Console.WriteLine(" ");   
   //Run the EnumLoginMappings method and return details of database user-login mappings to a DataTable object variable.   
   DataTable d;  
   d = db.EnumLoginMappings();   
   //Display the mapping information.   
   foreach (DataRow r in d.Rows) {   
      foreach (DataColumn c in r.Table.Columns) {   
         Console.WriteLine(c.ColumnName + " = " + r[c]);   
      }   
      Console.WriteLine(" ");   
   }   
}   
}  
```  
  
## <a name="enumerating-logins-and-associated-users-in-powershell"></a>PowerShell에서 로그인 및 연관된 사용자 열거  
 데이터베이스의 모든 사용자는 로그온과 연관되어 있습니다. 로그온은 둘 이상의 데이터베이스의 사용자들과 연관될 수 있습니다. 코드 예제는 <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> 개체의 <xref:Microsoft.SqlServer.Management.Smo.Login> 메서드를 호출하여 로그온과 연관된 데이터베이스 사용자를 모두 나열하는 방법을 보여 줍니다. 이 예에서는 만듭니다 로그온과 사용자에는 [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] 열거할 매핑 정보가 있는지 확인 하기 위해 데이터베이스.  
  
```powershell  
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\Default\Databases  
  
#Iterate through all databases  
 foreach ($db in Get-ChildItem)  
 {  
 "====="  
 "Login Mappings for the database: "+ $db.Name  
  
 #get the datatable containing the mapping from the smo database oject  
 $dt = $db.EnumLoginMappings()  
  
 #display the results  
 foreach($row in $dt.Rows)  
     {  
        foreach($col in $row.Table.Columns)  
      {  
        $col.ColumnName + "=" + $row[$col]  
       }  
  
     }  
 }  
```  
  
## <a name="managing-roles-and-users"></a>역할 및 사용자 관리  
 이 예제에서는 역할 및 사용자를 관리하는 방법을 보여 줍니다. 이 샘플을 실행 하려면 다음 어셈블리를 참조 해야 합니다.  
  
-   Microsoft.SqlServer.Smo.dll  
  
-   Microsoft.SqlServer.Management.Sdk.Sfc.dll  
  
-   Microsoft.SqlServer.ConnectionInfo.dll  
  
-   Microsoft.SqlServer.SqlEnum.dll  
  
```csharp  
using Microsoft.SqlServer.Management.Smo;  
using System;  
  
public class A {  
   public static void Main() {  
      Server svr = new Server();  
      Database db = new Database(svr, "TESTDB");  
      db.Create();  
  
      // Creating Logins  
      Login login = new Login(svr, "Login1");  
      login.LoginType = LoginType.SqlLogin;  
      login.Create("password@1");  
  
      Login login2 = new Login(svr, "Login2");  
      login2.LoginType = LoginType.SqlLogin;  
      login2.Create("password@1");  
  
      // Creating Users in the database for the logins created  
      User user1 = new User(db, "User1");  
      user1.Login = "Login1";  
      user1.Create();  
  
      User user2 = new User(db, "User2");  
      user2.Login = "Login2";  
      user2.Create();  
  
      // Creating database permission Sets  
      DatabasePermissionSet dbPermSet = new DatabasePermissionSet(DatabasePermission.AlterAnySchema);  
      dbPermSet.Add(DatabasePermission.AlterAnyUser);  
  
      DatabasePermissionSet dbPermSet2 = new DatabasePermissionSet(DatabasePermission.CreateType);  
      dbPermSet2.Add(DatabasePermission.CreateSchema);  
      dbPermSet2.Add(DatabasePermission.CreateTable);  
  
      // Creating Database roles  
      DatabaseRole role1 = new DatabaseRole(db, "Role1");  
      role1.Create();  
  
      DatabaseRole role2 = new DatabaseRole(db, "Role2");  
      role2.Create();  
  
      // Granting Database Permission Sets to Roles  
      db.Grant(dbPermSet, role1.Name);  
      db.Grant(dbPermSet2, role2.Name);  
  
      // Adding members (Users / Roles) to Role  
      role1.AddMember("User1");  
  
      role2.AddMember("User2");  
  
      // Role1 becomes a member of Role2  
      role2.AddMember("Role1");  
  
      // Enumerating through explicit permissions granted to Role1  
      // enumerates all database permissions for the Grantee  
      DatabasePermissionInfo[] dbPermsRole1 = db.EnumDatabasePermissions("Role1");     
      foreach (DatabasePermissionInfo dbp in dbPermsRole1) {  
         Console.WriteLine(dbp.Grantee + " has " + dbp.PermissionType.ToString() + " permission.");  
      }  
      Console.WriteLine(" ");  
   }  
}  
```
  
  