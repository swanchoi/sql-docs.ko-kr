---
title: Transact-SQL 코드 조각 삽입 | Microsoft 문서
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: scripting
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [SQL Server], snippets
- Transact-SQL snippets, code
- snippets [Transact-SQL], how to insert
ms.assetid: d66c96f4-2e84-4d79-9bfd-3635fdd98425
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: fb7521f04626cd0aae6a67035b186edf50bc5165
ms.sourcegitcommit: 0638b228980998de9056b177c83ed14494b9ad74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2018
ms.locfileid: "51643564"
---
# <a name="insert-transact-sql-snippets"></a>Transact-SQL 코드 조각 삽입
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
  [!INCLUDE[tsql](../../includes/tsql-md.md)] 코드 조각은 [!INCLUDE[tsql](../../includes/tsql-md.md)] 쿼리 편집기에서 새 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 문을 작성할 때 시작 지점으로 사용할 수 있는 템플릿입니다.  
  
## <a name="inserting-snippets"></a>조각 삽입  
 **조각 삽입** 메뉴를 사용하여 범주별로 분류된 조각 목록을 열고 이 목록에서 조각을 선택할 수 있습니다.  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] 조각에는 해당 지점과 관련된 구문을 제안하는 텍스트인 대체 지점이 포함되어 있습니다. 예를 들어 CREATE TABLE 조각에는 테이블 이름, 열 이름, 열 데이터 형식 등의 요소에 대한 대체 지점이 있습니다. 코드 조각을 삽입한 후에는 올바른 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문이 되도록 대체 텍스트를 변경해야 합니다. 자세한 내용은 [Transact-SQL 코드 조각 완성](../../relational-databases/scripting/complete-transact-sql-snippets.md)을 참조하세요.  
  
#### <a name="inserting-a-snippet-by-using-the-insert-snippet-menu"></a>조각 삽입 메뉴를 사용하여 조각 삽입  
  
1.  [!INCLUDE[ssDE](../../includes/ssde-md.md)] 쿼리 편집기 창에서 [!INCLUDE[tsql](../../includes/tsql-md.md)] 조각을 삽입할 위치에 커서를 놓습니다.  
  
2.  다음 세 가지 방법 중 하나로 조각 선택 도구 설명을 시작합니다.  
  
    -   Ctrl+K, Ctrl+X를 누릅니다.  
  
    -   **편집** 메뉴에서 **IntelliSense**를 가리킨 다음 **조각 삽입**을 클릭합니다.  
  
    -   마우스 오른쪽 단추를 클릭한 다음 바로 가기 메뉴에서 **조각 삽입** 을 선택합니다.  
  
3.  조각을 두 번 클릭하거나 조각 선택에서 조각을 선택하고 Tab 키 또는 Enter 키를 누릅니다.  
  
## <a name="see-also"></a>참고 항목  
 [코드 감싸기 Transact-SQL 조각 삽입](../../relational-databases/scripting/insert-surround-with-transact-sql-snippets.md)  
  
  
