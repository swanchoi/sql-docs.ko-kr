---
title: SQL 쿼리 실행 (SQLXML 관리 되는 클래스) | Microsoft 문서
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML], SQLXML Managed Classes
- SQLXML Managed Classes, executing SQL queries
- Managed Classes [SQLXML], executing SQL queries
- ExecuteToStream method
- SQL queries [SQLXML]
ms.assetid: a561ae83-a8b6-4b9b-a819-9b86839546b4
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 3d08831c8699acb7ef938e8d977801109704943d
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2019
ms.locfileid: "56014095"
---
# <a name="executing-sql-queries-sqlxml-managed-classes"></a>SQL 쿼리 실행(SQLXML 관리되는 클래스)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  이 예에서는 다음 작업을 수행하는 방법을 보여 줍니다.  
  
-   매개 변수 (SqlXmlParameter 개체)를 만듭니다.  
  
-   SqlXmlParameter 개체의 속성 이름 및 값에 값을 지정 합니다.  
  
 이 예에서는 간단한 SQL 쿼리를 실행하여 성이 매개 변수로 전달된 직원의 이름, 성 및 생년월일을 검색합니다. 매개 변수를 지정 (*성*), Value 속성만 설정 됩니다. 이 쿼리 매개 변수는 위치 때문에 이름이 필요 합니다. Name 속성이 설정 되지 않았습니다.  
  
 기본적으로 SqlXmlCommand 개체의 CommandType 속성은 **Sql**. 명시적으로 설정되지 않았습니다.  
  
> [!NOTE]  
>  코드에서 연결 문자열에 Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 인스턴스의 이름을 지정해야 합니다.  
  
 다음은 C# 코드입니다.  
  
```  
using System;  
  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         Stream strm;  
         SqlXmlParameter p;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);        
         cmd.CommandText = "SELECT FirstName, LastName FROM Person.Contact WHERE LastName=? For XML Auto";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         string strResult;  
         try   
         {  
            strm = cmd.ExecuteStream();  
            strm.Position = 0;  
            using(StreamReader sr = new StreamReader(strm))  
            {  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         catch (SqlXmlException e)  
         {  
            //in case of an error, this prints error returned.  
            e.ErrorStream.Position=0;  
            strResult=new StreamReader(e.ErrorStream).ReadToEnd();  
            System.Console.WriteLine(strResult);  
         }  
  
         return 0;  
   }  
public static int Main(String[] args)  
{  
    testParams();  
    return 0;  
}  
}  
```  
  
### <a name="to-test-the-application"></a>애플리케이션을 테스트하려면  
  
1.  이 항목에 나오는 C# 코드(DocSample.cs)를 폴더에 저장합니다.  
  
2.  코드를 컴파일합니다. 다음을 사용하여 명령 프롬프트에서 코드를 컴파일합니다.  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     이렇게 하면 실행 파일(DocSample.exe)이 만들어집니다.  
  
3.  명령 프롬프트에서 DocSample.exe를 실행합니다.  
  
 이 예를 테스트하려면 컴퓨터에 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework가 설치되어 있어야 합니다.  
  
 SQL 쿼리를 명령 텍스트로 지정하는 대신 다음 코드 조각에 표시된 것처럼 updategram 템플릿을 실행하는 템플릿을 지정하여 고객 레코드를 삽입할 수 있습니다. 파일에서 템플릿과 updategram을 지정한 후 파일을 실행합니다. 자세한 내용은 [CommandText 속성을 사용 하 여 템플릿 파일 실행](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-template-files-by-using-the-commandtext-property.md).  
  
```  
SqlXmlCommand cmd = new SqlXmlCommand("Provider=SQLOLEDB;Data Source=SqlServerName;Initial Catalog=Database; Integrated Security=SSPI;");  
Stream stm;  
cmd.CommandType = SqlXmlCommandType.UpdateGram;  
cmd.CommandText = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql' xmlns:updg='urn:schemas-microsoft-com:xml-updategram'>" +  
      "<updg:sync>" +  
       "<updg:before/>" +  
       "<updg:after>" +  
         "<Customer CustomerID='aaaaa' CustomerName='Some Name' CustomerTitle='SomeTitle' />" +  
       "</updg:after>" +  
       "</updg:sync>" +  
       "</ROOT>";  
  
stm = cmd.ExecuteStream();  
stm = null;  
cmd = null;  
```  
  
## <a name="using-executetostream"></a>ExecuteToStream 사용  
 기존의 스트림에 Stream 개체를 생성 하 고 Execute 메서드를 사용 하는 대신 ExecuteToStream 메서드를 사용할 수 있습니다. 이전 예제에서 코드는 ExecuteToStream 메서드를 사용 하 여 여기 개정 되어:  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=SqlServerName;database=AdventureWorks;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      SqlXmlParameter p;  
      MemoryStream ms = new MemoryStream();  
      StreamReader sr = new StreamReader(ms);  
      ms.Position = 0;  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.CommandText = "select FirstName, LastName from Person.Contact where LastName = ? For XML Auto";  
      p = cmd.CreateParameter();  
      p.Value = "Achong";  
      cmd.ExecuteToStream(ms);  
      ms.Position = 0;  
      Console.WriteLine(sr.ReadToEnd());  
      return 0;        
   }  
   public static int Main(String[] args)  
   {  
      testParams();     
      return 0;  
   }  
}  
```  
  
> [!NOTE]  
>  XmlReader 개체를 반환 하는 ExecuteXMLReadermethod를 사용할 수 있습니다. 자세한 내용은 [ExecuteXMLReader 메서드를 사용 하 여 SQL 쿼리 실행](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-sql-queries-by-using-the-executexmlreader-method.md).  
  
  
