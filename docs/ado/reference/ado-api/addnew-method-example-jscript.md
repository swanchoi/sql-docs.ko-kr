---
title: "AddNew 메서드 예제 (JScript) | Microsoft Docs"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JScript
helpviewer_keywords:
- AddNew method [ADO], JScript example
ms.assetid: eabdd278-6576-4be7-9315-fb79cb8ef678
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 756b72a0012eb05e999d18030ade12e3ef924620
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="addnew-method-example-jscript"></a>AddNew 메서드 예제 (JScript)
사용 하 여이 예제는 [AddNew](../../../ado/reference/ado-api/addnew-method-ado.md) 메서드를 지정 된 이름의 새 레코드를 만듭니다. 메모장 이나 다른 텍스트 편집기에 다음 코드를 잘라내어 하십시오로 저장 **붙여 넣고 AddNewJS.asp**합니다.  
  
```  
<!-- BeginAddNewJS -->  
<%@LANGUAGE="JScript" %>  
<!-- Include file for JScript ADO Constants -->  
<%// use this meta tag instead of adojavas.inc%>  
<!--METADATA TYPE="typelib" uuid="00000205-0000-0010-8000-00AA006D2EA4" -->  
  
<html>  
  
<head>  
    <title>Add New Method Example (JScript)</title>  
<style>  
<!--  
body {  
   font-family: 'Verdana','Arial','Helvetica',sans-serif;  
   BACKGROUND-COLOR:white;  
   COLOR:black;  
    }  
-->  
</style>  
</head>  
  
<body>  
<h1>AddNew Method Example (JScript)</h1>  
  
<%  
    if (Request.Form("Addit") == "AddNew")  
    {  
        // connection and recordset variables  
        var Cnxn = Server.CreateObject("ADODB.Connection")  
        var strCnxn = "Provider='sqloledb';Data Source=" + Request.ServerVariables("SERVER_NAME") + ";" +  
            "Initial Catalog='Northwind';Integrated Security='SSPI';";  
        var rsEmployee = Server.CreateObject("ADODB.Recordset");  
        //record variables  
        var FName = String(Request.Form("FirstName"));  
        var LName = String(Request.Form("LastName"));  
  
        try  
        {  
            // open connection  
            Cnxn.Open(strCnxn)  
  
            // open Employee recordset using client-side cursor  
            rsEmployee.CursorLocation = adUseClient;  
            rsEmployee.Open("Employees", strCnxn, adOpenKeyset, adLockOptimistic, adCmdTable);  
  
            rsEmployee.AddNew();  
            rsEmployee("FirstName") = FName;  
            rsEmployee("LastName") = LName;  
            rsEmployee.Update;  
  
            // of course, you would normally do error handling here  
            Response.Write("New record added.")  
        }  
        catch (e)  
        {  
            Response.Write(e.message);  
        }  
        finally  
        {  
            // clean up  
            if (rsEmployee.State == adStateOpen)  
                rsEmployee.Close;  
            if (Cnxn.State == adStateOpen)  
                Cnxn.Close;  
            rsEmployee = null;  
            Cnxn = null;  
        }  
    }  
%>  
  
<form method="post" action="AddNewJS.asp" id=form1 name=form1>  
<table>  
<tr>  
    <td colspan="2">  
    <h4>Please enter the record to add:</h4>  
    </td>  
</tr>  
<tr>  
    <td>  
        First Name:  
    </td>  
    <td>  
        <input name="FirstName" maxLength=20>  
    </td>  
</tr>  
<tr>  
    <td>  
        Last Name:  
    </td>  
    <td>  
        <input name="LastName" size="30" maxLength=30>  
    </td>  
</tr>  
<tr>  
    <td align="right">  
        <input type="submit" value="Submit" name="Submit">  
    </td>  
    <TD align="left">  
        <INPUT type="reset" value="Reset" name="Reset">  
    </TD>  
</tr>  
</table>  
<INPUT type="hidden" value="AddNew" name="Addit">  
</form>  
</body>  
</HTML>  
<!-- EndAddNewJS -->  
```  
  
## <a name="see-also"></a>관련 항목:  
 [AddNew 메서드 (ADO)](../../../ado/reference/ado-api/addnew-method-ado.md)   
 [레코드 집합 개체(ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)