---
title: NativeError 속성 (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Error::GetNativeError
- Error::get_NativeError
- Error::NativeError
helpviewer_keywords:
- NativeError property [ADO]
ms.assetid: b9b47e57-18a4-4186-aef5-5bd18d7b1d74
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 2f6ee8724454a8871f6642f5d812584ccffd9385
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47735051"
---
# <a name="nativeerror-property-ado"></a>NativeError 속성(ADO)
에 대 한 공급자 관련 오류 코드를 나타냅니다.는 주어진 [오류](../../../ado/reference/ado-api/error-object.md) 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 된 **긴** 오류 코드를 나타내는 값입니다.  
  
## <a name="remarks"></a>Remarks  
 사용 된 **NativeError** 특정 데이터베이스 관련 오류 정보를 검색할 속성 **오류** 개체입니다. 예를 들어, Microsoft SQL Server 데이터베이스를 사용 하 여 OLE DB에 대 한 Microsoft ODBC 공급자를 사용 하는 경우 SQL Server에서 발생 하는 원시 오류 코드 통과 ODBC 및 ODBC 공급자는 ADO **NativeError** 속성입니다.  
  
## <a name="applies-to"></a>적용 대상  
 [Error 개체](../../../ado/reference/ado-api/error-object.md)  
  
## <a name="see-also"></a>관련 항목  
 [설명, HelpContext, HelpFile, NativeError, 번호, 원본 및 SQLState 속성 예제 (VB)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vb.md)   
 [설명, HelpContext, HelpFile, NativeError, 번호, 원본 및 SQLState 속성 예제 (VC + +)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vc.md)   
