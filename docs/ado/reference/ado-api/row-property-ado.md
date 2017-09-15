---
title: "속성 (ADO)를 행 | Microsoft Docs"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- ADORecordConstruction::PutRow
- ADORecordConstruction::GetRow
- ADORecordConstruction::get_Row
- ADORecordConstruction::Row
- ADORecordConstruction::put_Row
helpviewer_keywords:
- Row property [ADO]
ms.assetid: 21019d89-2dd1-4a26-ac6f-384b81d66949
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 19b935d43739d1a1ce19f414cae12b00c311b261
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="row-property-ado"></a>Row 속성 (ADO)
OLE DB를 가져오거나 설정 합니다. **행** 또는에서 개체는 [ADORecordConstruction 인터페이스](../../../ado/reference/ado-api/adorecordconstruction-interface.md) 개체입니다. 사용 하는 경우 **put_Row** 설정 하는 **행** 개체를 행 ADO로 변경 됩니다 **레코드** 개체입니다.  
  
## <a name="readwritesyntax"></a>읽기/쓰기입니다. 구문  
  
```  
HRESULT get_Row([out, retval] IUnknown** ppRow);  
HRESULT put_Row([in] IUnknown* pRow);  
```  
  
## <a name="parameters"></a>매개 변수  
 *ppRow*  
 OLE DB에 대 한 포인터 **행** 개체입니다.  
  
 *PRow*  
 OLE DB **행** 개체입니다.  
  
## <a name="return-values"></a>반환 값  
 이 속성 메서드는 S_OK와 E_FAIL을 포함 하는 표준 HRESULT 값을 반환 합니다.  
  
## <a name="applies-to"></a>적용 대상  
 [ADORecordConstruction 인터페이스](../../../ado/reference/ado-api/adorecordconstruction-interface.md)