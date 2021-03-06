---
title: 옵션 (쿼리 결과-SQL Server-다중-Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqleditors.multiserverresultssettings
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLMultiServerResults
ms.assetid: d6768bd8-9cb5-4606-a726-a33a1df9e1bb
author: craigg-msft
ms.author: craigg
manager: craigg
ms.openlocfilehash: 99b9192f2bf2b6e1fe00e1b0e367ff254219539c
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48172199"
---
# <a name="options-query-results-sql-server-multi-server"></a>옵션(쿼리 결과-SQL Server-다중 서버)
  여러 서버를 동시에 쿼리할 때 이 페이지를 사용하여 결과 집합 표시 옵션을 지정할 수 있습니다. 결과를 병합하면 모든 서버의 결과 집합이 단일 결과 집합으로 결합됩니다. 결과를 병합할 때 응답할 첫 번째 서버가 결과 집합에 대한 스키마를 설정합니다. 결과 집합을 병합하려면 쿼리가 각 서버에서 같은 열 이름을 사용하는 동일한 수의 열을 반환해야 합니다. 결과를 병합할 때는 결과를 반환할 첫 번째 서버에서 반환된 스키마(열 개수 및 열 이름)와 일치하지 않는 각 서버에 대해 메시지가 표시됩니다.  
  
 결과를 병합하지 않을 때는 각 서버의 결과 집합이 자체 스키마와 함께 자체 표에 표시됩니다.  
  
## <a name="uielement-list"></a>UIElement 목록  
 **결과 병합**  
 여러 서버의 결과 집합을 같은 표로 결합하려면 이 확인란을 선택합니다.  
  
 **결과에 서버 이름 추가**  
 각 행을 생성한 서버의 이름을 제공하는 추가 열을 포함하려면 이 확인란을 선택합니다.  
  
 **결과에 로그인 이름 추가**  
 각 행을 제공한 서버에 연결하는 데 사용된 로그인을 제공하는 추가 열을 포함하려면 이 확인란을 선택합니다.  
  
## <a name="see-also"></a>관련 항목  
 [중앙 관리 서버 및 서버 그룹 만들기 &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md)   
 [여러 서버에 대해 동시에 문 실행&#40;SQL Server Management Studio&#41;](../ssms/register-servers/execute-statements-against-multiple-servers-simultaneously.md)  
  
  
