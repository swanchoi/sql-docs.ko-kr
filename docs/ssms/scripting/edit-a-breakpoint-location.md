---
title: 중단점 위치 편집 | Microsoft 문서
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: scripting
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint location
ms.assetid: 5c28e411-0377-4210-a7ce-2a5c13dcdf74
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 0e1525b5210d94f4a1a9f219a757daa893731f5d
ms.sourcegitcommit: 40c3b86793d91531a919f598dd312f7e572171ec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/13/2018
ms.locfileid: "53328353"
---
# <a name="edit-a-breakpoint-location"></a>중단점 위치 편집
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
  중단점 위치는 [!INCLUDE[tsql](../../includes/tsql-md.md)] 스크립트 파일에서 중단점이 나오는 줄과 문자를 지정합니다. 중단점 위치를 편집하여 중단점을 스크립트의 다른 위치나 다른 스크립트로 이동할 수 있습니다.  
  
## <a name="editing-a-location"></a>위치 편집  
 중단점 위치를 편집하면 적중 횟수 또는 조건과 같은 모든 기존 속성과 함께 중단점이 새 위치로 이동됩니다.  
  
#### <a name="to-edit-a-breakpoint-location"></a>중단점 위치를 편집하려면  
  
1.  편집기 창에서 중단점 문자 모양을 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **위치** 를 클릭합니다.  
  
     -또는-  
  
     **중단점** 창에서 중단점 문자 모양을 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **위치** 를 클릭합니다.  
  
2.  **파일 중단점** 대화 상자에서 **파일** 을 편집하여 새 파일을 지정하거나 **줄** 을 편집하여 새 줄을 지정하거나 **문자** 를 편집하여 줄 내의 새 위치를 지정합니다. 지정한 새 파일이 쿼리 편집기 창에 이미 열려 있으면 중단점이 해당 편집기 창으로 이동됩니다. 파일이 열려 있지 않으면 새 편집기 창이 열리고 파일이 로드된 후 중단점이 새 위치로 이동됩니다.  
  
     **을 디버깅할 때는** 소스 코드가 원래 버전과 일치하지 않아도 됨 [!INCLUDE[tsql](../../includes/tsql-md.md)]옵션을 설정해도 아무 효과가 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [적중 횟수 지정](../../relational-databases/scripting/specify-a-hit-count.md)   
 [중단점 동작 지정](../../relational-databases/scripting/specify-a-breakpoint-action.md)   
 [중단점 조건 지정](../../relational-databases/scripting/specify-a-breakpoint-condition.md)   
 [중단점 필터 지정](../../relational-databases/scripting/specify-a-breakpoint-filter.md)  
