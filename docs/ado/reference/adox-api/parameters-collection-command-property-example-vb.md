---
title: "Parameters 컬렉션, 명령 속성 예제 (VB) | Microsoft Docs"
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
- VB
helpviewer_keywords:
- Command property [ADOX], Visual Basic example
ms.assetid: 7df1089e-69b7-476e-9244-19947c087351
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: b927cf4ae288fce370f20d122c93ba72d79d454d
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="parameters-collection-command-property-example-vb"></a>Parameters 컬렉션, 명령 속성 예제 (VB)
다음 코드에서는 사용 하는 방법을 [명령](../../../ado/reference/adox-api/command-property-adox.md) 속성을는 [명령](../../../ado/reference/ado-api/command-object-ado.md) 프로시저에 대 한 매개 변수 정보를 검색할 개체입니다.  
  
```  
' BeginParametersVB  
Sub Main()  
    On Error GoTo ProcedureParametersError  
  
    Dim cnn As New ADODB.Connection  
    Dim cmd As ADODB.Command  
    Dim prm As ADODB.Parameter  
    Dim cat As New ADOX.Catalog  
  
    ' Open the Connection  
    cnn.Open _  
        "Provider='Microsoft.Jet.OLEDB.4.0';" & _  
        "Data Source='Northwind.mdb';"  
  
    ' Open the catalog  
    Set cat.ActiveConnection = cnn  
  
    ' Get the command object  
    Set cmd = cat.Procedures("CustomerById").Command  
  
    ' Retrieve Parameter information  
    cmd.Parameters.Refresh  
    For Each prm In cmd.Parameters  
        Debug.Print prm.Name & ":" & prm.Type  
    Next  
  
    'Clean up  
    cnn.Close  
    Set cat = Nothing  
    Set cmd = Nothing  
    Set cnn = Nothing  
    Exit Sub  
  
ProcedureParametersError:  
  
    Set cat = Nothing  
    Set cmd = Nothing  
  
    If Not cnn Is Nothing Then  
        If cnn.State = adStateOpen Then cnn.Close  
    End If  
    Set cnn = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
End Sub  
' EndParametersVB  
```  
  
## <a name="see-also"></a>관련 항목:  
 [ActiveConnection 속성 (ADOX)](../../../ado/reference/adox-api/activeconnection-property-adox.md)   
 [카탈로그 개체 (ADOX)](../../../ado/reference/adox-api/catalog-object-adox.md)   
 [Command 속성 (ADOX)](../../../ado/reference/adox-api/command-property-adox.md)   
 [프로시저 개체 (ADOX)](../../../ado/reference/adox-api/procedure-object-adox.md)   
 [Procedures 컬렉션(ADOX)](../../../ado/reference/adox-api/procedures-collection-adox.md)