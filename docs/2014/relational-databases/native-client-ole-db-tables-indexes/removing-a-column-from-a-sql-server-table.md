---
title: SQL Server 테이블에서 열 제거 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- columns [OLE DB]
- removing columns
- DropColumn function
- SQL Server Native Client OLE DB provider, columns
ms.assetid: 210811b7-cbd6-421e-bc6e-df9482236768
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 919bd28a82171068349e4019bb1bd5c190d08cd0
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48108353"
---
# <a name="removing-a-column-from-a-sql-server-table"></a>SQL Server 테이블에서 열 제거
  합니다 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB 공급자가 노출 하는 **ITableDefinition::DropColumn** 함수입니다. 이 함수를 사용하여 소비자는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 테이블에서 열을 제거할 수 있습니다.  
  
 소비자는 *pTableID* 매개 변수에서 *uName* 공용 구조체의 *pwszName* 멤버에서 테이블 이름을 유니코드 문자열로 지정합니다. *pTableID*의 *eKind*멤버는 DBKIND_NAME이어야 합니다.  
  
 소비자의 열 이름을 나타냅니다 합니다 *pwszName*의 멤버는 *uName* 공용 구조체의 *pColumnID* 매개 변수입니다. 열 이름은 유니코드 문자열입니다. *pColumnID*의 *eKind*멤버는 DBKIND_NAME이어야 합니다.  
  
## <a name="example"></a>예제  
  
### <a name="code"></a>코드  
  
```  
DBID TableID;  
DBID ColumnID;  
HRESULT hr;  
  
TableID.eKind = DBKIND_NAME;  
TableID.uName.pwszName = L"MyTableName";  
  
ColumnID.eKind = DBKIND_NAME;  
ColumnID.uName.pwszName = L"MyColumnName";  
  
hr = m_pITableDefinition->DropColumn(&TableID, &ColumnID);  
```  
  
## <a name="see-also"></a>관련 항목  
 [테이블 및 인덱스](tables-and-indexes.md)  
  
  
