---
title: "커서 (Transact SQL) | Microsoft Docs"
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- statements [SQL Server], cursors
- functions [SQL Server], cursors
- cursors [SQL Server], statements
ms.assetid: 63000023-54fc-4efc-a30f-fb4d4db73aae
caps.latest.revision: 15
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 990b1bc3c44605e2b7debed67b88e5cd65770ed5
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="cursors-transact-sql"></a>커서(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 문은 완전 한 결과 집합을 만들지만 결과가 가장 좋은 시간은 한 번에 하나의 행을 처리 합니다. 결과 집합에서 커서를 열면 결과 집합을 한 번에 한 행씩 처리할 수 있습니다. 커서 변수 또는 매개 변수를 할당할 수 있습니다는 **커서** 데이터 형식입니다.  
  
 커서 작업은 다음과 같은 문에서 지원됩니다.  
  
 [닫기](../../t-sql/language-elements/close-transact-sql.md)  
  
 [CREATE PROCEDURE](../../t-sql/statements/create-procedure-transact-sql.md)  
  
 [할당 취소](../../t-sql/language-elements/deallocate-transact-sql.md)  
  
 [커서 선언](../../t-sql/language-elements/declare-cursor-transact-sql.md)  
  
 [DECLARE @local_variable](../../t-sql/language-elements/declare-local-variable-transact-sql.md)  
  
 [DELETE](../../t-sql/statements/delete-transact-sql.md)  
  
 [FETCH](../../t-sql/language-elements/fetch-transact-sql.md)  
  
 [열기](../../t-sql/language-elements/open-transact-sql.md)  
  
 [UPDATE](../../t-sql/queries/update-transact-sql.md)  
  
 [설정](../../t-sql/statements/set-statements-transact-sql.md)  
  
 다음 시스템 함수 및 시스템 저장 프로시저 또한 커서를 지원합니다.  
  
 [@@CURSOR_ROWS](../../t-sql/functions/cursor-rows-transact-sql.md)  
  
 [CURSOR_STATUS](../../t-sql/functions/cursor-status-transact-sql.md)  
  
 [@@FETCH_STATUS](../../t-sql/functions/fetch-status-transact-sql.md)  
  
 [sp_cursor_list](../../relational-databases/system-stored-procedures/sp-cursor-list-transact-sql.md)  
  
 [sp_describe_cursor](../../relational-databases/system-stored-procedures/sp-describe-cursor-transact-sql.md)  
  
 [sp_describe_cursor_columns](../../relational-databases/system-stored-procedures/sp-describe-cursor-columns-transact-sql.md)  
  
 [sp_describe_cursor_tables](../../relational-databases/system-stored-procedures/sp-describe-cursor-tables-transact-sql.md)  
  
## <a name="see-also"></a>관련 항목:  
 [커서](../../relational-databases/cursors.md)  
  
  