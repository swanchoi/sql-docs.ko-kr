---
title: "사용 가능한 패키지를 프로그래밍 방식으로 열거 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- programmatically enumerate packages [SSIS]
- existence testing [Integration Services]
- enumerating packages [Integration Services]
ms.assetid: 254ec7ee-d3ff-4361-8995-46e9b9c4dc95
caps.latest.revision: 34
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 4ebdf52b9ec71be3845d0fcdf3053b2168467389
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="enumerating-available-packages-programmatically"></a>프로그래밍 방식으로 사용 가능 패키지 열거
  <a name="top"></a>프로그래밍 방식으로 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 패키지, 수도 있습니다를, 개별 패키지 또는 폴더가 있는지 확인 하거나 로드 및 실행할 수 있는 저장 된 패키지를 열거 합니다. <xref:Microsoft.SqlServer.Dts.Runtime.Application> 네임스페이스의 <xref:Microsoft.SqlServer.Dts.Runtime> 클래스는 이 요구 사항을 충족하기 위한 다양한 메서드를 제공합니다.    
    
##  <a name="exists"></a>패키지 또는 폴더가 있는지 여부 확인    
 저장된 패키지가 있는지 여부를 프로그래밍 방식으로 확인하려면 해당 패키지를 로드 및 실행하기 전에 다음 메서드 중 하나를 호출합니다.    
    
|저장소 위치|호출할 메서드|    
|----------------------|--------------------|    
|SSIS 패키지 저장소|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnDtsServer%2A>|    
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnSqlServer%2A>|    
    
 폴더가 있는지 여부를 프로그래밍 방식으로 확인하려면 해당 폴더에 저장된 패키지를 나열하기 전에 다음 메서드 중 하나를 호출합니다.    
    
|저장소 위치|호출할 메서드|    
|----------------------|--------------------|    
|SSIS 패키지 저장소|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnDtsServer%2A>|    
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnSqlServer%2A>|    
    
 [맨 위로 이동](#top)    
    
##  <a name="listing"></a>사용 가능한 패키지 열거    
 저장된 패키지 목록을 프로그래밍 방식으로 가져오려면 다음 메서드 중 하나를 호출합니다.    
    
|저장소 위치|호출할 메서드|    
|----------------------|--------------------|    
|SSIS 패키지 저장소|<xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A>|    
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A>|    
    
 다음 예제는 이러한 메서드의 사용 방법을 보여 주는 콘솔 응용 프로그램입니다.    
    
###  <a name="listing_store"></a>예 (SSIS 패키지 저장소)    
 <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A> 메서드를 사용하면 SSIS 패키지 저장소에 저장된 패키지를 나열할 수 있습니다. SSIS 패키지 저장소에서 관리하는 기본 저장소 위치는 파일 시스템과 MSDB입니다. 이러한 위치에 논리적 폴더를 추가로 만들 수 있습니다.    
    
```vb    
Imports Microsoft.SqlServer.Dts.Runtime    
    
Module Module1    
    
  Sub Main()    
    
    Dim sqlFolder As String    
    Dim sqlServer As String    
    
    Dim ssisApplication As Application    
    Dim sqlPackages As PackageInfos    
    Dim sqlPackage As PackageInfo    
    
    sqlServer = "."    
    
    ssisApplication = New Application()    
    
    ' Get packages stored in MSDB.    
    sqlFolder = "MSDB"    
    sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer)    
    If sqlPackages.Count > 0 Then    
      Console.WriteLine("Packages stored in MSDB:")    
      For Each sqlPackage In sqlPackages    
        Console.WriteLine(sqlPackage.Name)    
      Next    
      Console.WriteLine()    
    End If    
    
    ' Get packages stored in the File System.    
    sqlFolder = "File System"    
    sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer)    
    If sqlPackages.Count > 0 Then    
      Console.WriteLine("Packages stored in the File System:")    
      For Each sqlPackage In sqlPackages    
        Console.WriteLine(sqlPackage.Name)    
      Next    
    End If    
    
    Console.Read()    
    
  End Sub    
    
End Module    
```    
    
```csharp    
using System;    
using Microsoft.SqlServer.Dts.Runtime;    
    
namespace EnumeratePackagesSSIS_CS    
{    
  class Program    
  {    
    static void Main(string[] args)    
    {    
    
      string sqlFolder;    
      string sqlServer;    
    
      Application ssisApplication;    
      PackageInfos sqlPackages;    
    
      sqlServer = ".";    
    
      ssisApplication = new Application();    
    
      // Get packages stored in MSDB.    
      sqlFolder = "MSDB";    
      sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer);    
      if (sqlPackages.Count > 0)    
      {    
        Console.WriteLine("Packages stored in MSDB:");    
        foreach (PackageInfo sqlPackage in sqlPackages)    
        {    
          Console.WriteLine(sqlPackage.Name);    
        }    
        Console.WriteLine();    
      }    
    
      // Get packages stored in the File System.    
      sqlFolder = "File System";    
      sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer);    
      if (sqlPackages.Count > 0)    
      {    
        Console.WriteLine("Packages stored in the File System:");    
        foreach (PackageInfo sqlPackage in sqlPackages)    
        {    
          Console.WriteLine(sqlPackage.Name);    
        }    
      }    
    
      Console.Read();    
    
    }    
    
  }    
    
}    
```    
    
 [맨 위로 이동](#top)    
    
###  <a name="listing_sql"></a>예제 (SQL Server)    
 <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A> 메서드를 사용하면 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]의 인스턴스에 저장된 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 패키지를 나열할 수 있습니다.    
    
```vb    
Imports Microsoft.SqlServer.Dts.Runtime    
    
Module Module1    
    
  Sub Main()    
    
    Dim sqlFolder As String    
    Dim sqlServer As String    
    Dim sqlUser As String    
    Dim sqlPassword As String    
    
    Dim ssisApplication As Application    
    Dim sqlPackages As PackageInfos    
    Dim sqlPackage As PackageInfo    
    
    sqlFolder = String.Empty    
    sqlServer = "(local)"    
    sqlUser = String.Empty    
    sqlPassword = String.Empty    
    
    ssisApplication = New Application()    
    
    sqlPackages = ssisApplication.GetPackageInfos(sqlFolder, sqlServer, sqlUser, sqlPassword)    
    
    For Each sqlPackage In sqlPackages    
      Console.WriteLine(sqlPackage.Name)    
    Next    
    
    Console.Read()    
    
  End Sub    
    
End Module    
```    
    
```csharp    
using System;    
using Microsoft.SqlServer.Dts.Runtime;    
    
namespace EnumeratePackagesSql_CS    
{    
  class Program    
  {    
    static void Main(string[] args)    
    {    
    
      string sqlFolder;    
      string sqlServer;    
      string sqlUser;    
      string sqlPassword;    
    
      Application ssisApplication;    
      PackageInfos sqlPackages;    
    
      sqlFolder = String.Empty;    
      sqlServer = "(local)";    
      sqlUser = String.Empty;    
      sqlPassword = String.Empty;    
    
      ssisApplication = new Application();    
    
      sqlPackages = ssisApplication.GetPackageInfos(sqlFolder, sqlServer, sqlUser, sqlPassword);    
    
      foreach (PackageInfo sqlPackage in sqlPackages)    
      {    
        Console.WriteLine(sqlPackage.Name);    
      }    
    
      Console.Read();    
    
    }    
  }    
}    
```    
    
 [맨 위로 이동](#top)    
   
## <a name="see-also"></a>관련 항목:    
 [패키지 관리&#40;SSIS 서비스&#41;](../../integration-services/service/package-management-ssis-service.md)    
    
  