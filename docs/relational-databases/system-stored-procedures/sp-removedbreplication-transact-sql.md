---
title: sp_removedbreplication (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_removedbreplication
- sp_removedbreplication_TSQL
helpviewer_keywords:
- sp_removedbreplication
ms.assetid: cb98d571-d1eb-467b-91f7-a6e091009672
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 4b9f9c6c8c39355ec2c381c7fa4efa340da3addf
ms.sourcegitcommit: c44014af4d3f821e5d7923c69e8b9fb27aeb1afd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58528665"
---
# <a name="spremovedbreplication-transact-sql"></a>sp_removedbreplication (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  이 저장 프로시저는 SQL Server의 게시자 인스턴스에서 게시 데이터베이스 또는 SQL Server의 구독자 인스턴스에서 구독 데이터베이스의 모든 복제 개체를 제거합니다. 적절한 데이터베이스에서 실행하고 같은 인스턴스 상에 다른 데이터베이스의 컨텍스트에서 실행을 하는 경우 복제 개체를 제거해야 할 데이터베이스를 지정합니다. 이 프로시저는 배포 데이터베이스와 같은 다른 데이터베이스에서 개체를 제거하지 않습니다.  
  
> [!NOTE]  
>  이 프로시저는 다른 방법으로 복제 개체를 제거하는 데 실패한 경우에만 사용해야 합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_removedbreplication [ [ @dbname = ] 'dbname' ]  
    [ , [ @type = ] type ]   
```  
  
## <a name="arguments"></a>인수  
`[ @dbname = ] 'dbname'` 데이터베이스의 이름이입니다. *dbname* 은 기본값은 NULL을 가진 **sysname**입니다. NULL인 경우 현재 데이터베이스를 사용합니다.  
  
`[ @type = ] type` 개체 제거 되는 데이터베이스에 대 한 복제의 유형이입니다. *형식* 됩니다 **nvarchar(5)** 이며 다음 값 중 하나일 수 있습니다.  
  
|||  
|-|-|  
|**tran**|트랜잭션 복제 게시 개체를 제거합니다.|  
|**merge**|병합 복제 게시 개체를 제거합니다.|  
|**둘 다** (기본값)|모든 복제 게시 개체를 제거합니다.|  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="remarks"></a>Remarks  
 **sp_removedbreplication** 모든 유형의 복제에 사용 됩니다.  
  
 **sp_removedbreplication** 복원할 필요가 없는 복제 개체를 가진 복제 된 데이터베이스를 복원 하는 경우에 유용 합니다.  
  
 **sp_removedbreplication** 읽기 전용으로 표시 되는 데이터베이스에 대해 사용할 수 없습니다.  
  
## <a name="example"></a>예제  
 [!code-sql[HowTo#sp_removedbreplication](../../relational-databases/replication/codesnippet/tsql/sp-removedbreplication-t_1.sql)]  
  
## <a name="permissions"></a>사용 권한  
 멤버는 **sysadmin** 고정된 서버 역할을 실행할 수 있습니다 **sp_removedbreplication**합니다.  
  
## <a name="example"></a>예제  
  
```  
-- Remove replication objects from the subscription database on MYSUB.  
DECLARE @subscriptionDB AS sysname  
SET @subscriptionDB = N'AdventureWorksReplica'  
  
-- Remove replication objects from a subscription database (if necessary).  
USE master  
EXEC sp_removedbreplication @subscriptionDB  
GO  
  
```  
  
## <a name="see-also"></a>관련 항목  
 [게시 및 배포 해제](../../relational-databases/replication/disable-publishing-and-distribution.md)   
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
