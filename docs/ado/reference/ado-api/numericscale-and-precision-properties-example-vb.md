---
title: NumericScale 및 Precision 속성 예제 (VB) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- NumericScale property [ADO], Visual Basic example
- Precision property [ADO], Visual Basic example
ms.assetid: 9c1e2322-c225-49d1-a120-a343f23cea73
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: fc8f2ee894416d8e290fe9e1a54b6123664b3c7c
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47612401"
---
# <a name="numericscale-and-precision-properties-example-vb"></a>NumericScale 및 Precision 속성 예제 (VB)
이 예에서는 [NumericScale](../../../ado/reference/ado-api/numericscale-property-ado.md) 및 [정밀도](../../../ado/reference/ado-api/precision-property-ado.md) 속성 필드의 전체 자릿수 및 소수 자릿수를 표시 하는 ***할인*** 목차는  ***Pubs*** 데이터베이스입니다.  
  
```  
'BeginNumericScaleVB  
  
    'To integrate this code  
    'replace the data source and initial catalog values  
    'in the connection string  
  
Public Sub NumericScaleX()  
  
    ' connection and recordset variables  
   Dim rstDiscounts As ADODB.Recordset  
   Dim Cnxn As ADODB.Connection  
   Dim fldTemp As ADODB.Field  
   Dim strCnxn As String  
   Dim strSQLDiscounts As String  
  
   ' Open connection  
   Set Cnxn = New ADODB.Connection  
   strCnxn = "Provider='sqloledb';Data Source='MySqlServer';Initial Catalog='Pubs';Integrated Security='SSPI';"  
  
   Cnxn.Open strCnxn  
  
   ' Open recordset  
   Set rstDiscounts = New ADODB.Recordset  
   strSQLDiscounts = "Discounts"  
   rstDiscounts.Open strSQLDiscounts, Cnxn, adOpenStatic, adLockReadOnly, adCmdTable  
  
   ' Display numeric scale and precision of  
   ' numeric and small integer fields  
   For Each fldTemp In rstDiscounts.Fields  
      If fldTemp.Type = adNumeric Or fldTemp.Type = adSmallInt Then  
         MsgBox "Field: " & fldTemp.Name & vbCr & _  
            "Numeric scale: " & _  
               fldTemp.NumericScale & vbCr & _  
            "Precision: " & fldTemp.Precision  
      End If  
   Next fldTemp  
  
    ' clean up  
   rstDiscounts.Close  
   Cnxn.Close  
   Set rstDiscounts = Nothing  
   Set Cnxn = Nothing  
  
End Sub  
'EndNumericScaleVB  
```  
  
## <a name="see-also"></a>관련 항목  
 [Field 개체](../../../ado/reference/ado-api/field-object.md)   
 [NumericScale 속성 (ADO)](../../../ado/reference/ado-api/numericscale-property-ado.md)   
 [매개 변수 개체](../../../ado/reference/ado-api/parameter-object.md)   
 [Precision 속성(ADO)](../../../ado/reference/ado-api/precision-property-ado.md)
