---
title: "XML 스키마를 사용 하 여 | Microsoft Docs"
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
helpviewer_keywords: XML [SMO]
ms.assetid: 9d04de01-efeb-4b2d-8c28-3234bc7ff2f3
caps.latest.revision: "41"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c80fad3483460d6b0cbb6472c86549bf83219c39
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="using-xml-schemas"></a>XML 스키마 사용
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]SMO에서 XML 프로그래밍은 XML 데이터 형식, XML 네임 스페이스 및 XML 데이터 형식 열의 단순 인덱스를 제공 하 제한 됩니다.  
  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] XML 문서 인스턴스에 대 한 기본 저장소를 제공 합니다. XML 스키마를 사용하여 데이터 무결성 보장을 위해 XML 문서의 유효성 검사에 사용할 수 있는 복잡한 XML 데이터 형식을 정의할 수 있습니다. XML 스키마는 <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> 개체에 정의됩니다.  
  
## <a name="example"></a>예제  
 제공된 코드 예제를 사용하려면 응용 프로그램을 만들 프로그래밍 환경, 프로그래밍 템플릿 및 프로그래밍 언어를 선택해야 합니다. 자세한 내용은 참조 [만들기 Visual C &#35; Visual Studio.NET에서에서 SMO 프로젝트](../../../relational-databases/server-management-objects-smo/how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md)합니다.  
  
## <a name="creating-an-xml-schema-in-visual-basic"></a>Visual Basic에서 XML 스키마 만들기  
 이 코드 예제는 <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> 개체를 사용하여 XML 스키마를 만드는 방법을 보여 줍니다. XML 스키마 컬렉션을 정의하는 <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> 속성은 여러 개의 큰따옴표를 포함하고 이들은 `chr(34)` 문자열로 바뀝니다.  
  
```VBNET
'Connect to the local, default instance of SQL Server.
Dim srv As Server
srv = New Server()
'Reference the AdventureWorks2012 2008R2 database.
Dim db As Database
db = srv.Databases("AdventureWorks2012")
'Define an XmlSchemaCollection object by supplying the parent database and name arguments in the constructor.
Dim xsc As XmlSchemaCollection
xsc = New XmlSchemaCollection(db, "MySampleCollection")
xsc.Text = "\<schema xmlns=" + Chr(34) + "http://www.w3.org/2001/XMLSchema" + Chr(34) + "  xmlns:ns=" + Chr(34) + "http://ns" + Chr(34) + ">\<element name=" + Chr(34) + "e" + Chr(34) + " type=" + Chr(34) + "dateTime" + Chr(34) + "/></schema>"
'Create the XML schema collection on the instance of SQL Server.
xsc.Create()
```
  
## <a name="creating-an-xml-schema-in-visual-c"></a>Visual C#에서 XML 스키마 만들기  
 이 코드 예제는 <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> 개체를 사용하여 XML 스키마를 만드는 방법을 보여 줍니다. XML 스키마 컬렉션을 정의하는 <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> 속성은 여러 개의 큰따옴표를 포함하고 이들은 `chr(34)` 문자열로 바뀝니다.  
  
```csharp  
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = default(Server);  
            srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db = default(Database);  
            db = srv.Databases["AdventureWorks2012"];  
            //Define an XmlSchemaCollection object by supplying the parent  
            // database and name arguments in the constructor.   
            XmlSchemaCollection xsc = default(XmlSchemaCollection);  
            xsc = new XmlSchemaCollection(db, "MySampleCollection");  
            xsc.Text = "\<schema xmlns=" + Strings.Chr(34) + "http://www.w3.org/2001/XMLSchema" + Strings.Chr(34) + " xmlns:ns=" + Strings.Chr(34) + "http://ns" + Strings.Chr(34) + ">\<element name=" + Strings.Chr(34) + "e" + Strings.Chr(34) + " type=" + Strings.Chr(34) + "dateTime" + Strings.Chr(34) + "/></schema>";  
            //Create the XML schema collection on the instance of SQL Server.   
            xsc.Create();  
        }  
```  
  
## <a name="creating-an-xml-schema-in-powershell"></a>PowerShell에서 XML 스키마 만들기  
 이 코드 예제는 <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> 개체를 사용하여 XML 스키마를 만드는 방법을 보여 줍니다. XML 스키마 컬렉션을 정의하는 <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> 속성은 여러 개의 큰따옴표를 포함하고 이들은 `chr(34)` 문자열로 바뀝니다.  
  
```powershell   
#Get a server object which corresponds to the default instance replace LocalMachine with the physical server  
cd \sql\LocalHost  
$srv = get-item default  
  
#Reference the AdventureWorks database.  
$db = $srv.Databases["AdventureWorks2012"]  
  
#Create a new schema collection  
$xsc = New-Object -TypeName Microsoft.SqlServer.Management.SMO.XmlSchemaCollection `  
-argumentlist $db,"MySampleCollection"  
  
#Add the xml  
$dq = '"' # the double quote character  
$xsc.Text = "<schema xmlns=" + $dq + "http://www.w3.org/2001/XMLSchema" + $dq + `  
"  xmlns:ns=" + $dq + "http://ns" + $dq + "><element name=" + $dq + "e" + $dq +`  
 " type=" + $dq + "dateTime" + $dq + "/></schema>"  
  
#Create the XML schema collection on the instance of SQL Server.  
$xsc.Create()  
```  
  
  