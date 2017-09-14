---
title: GET CONVERSATION GROUP (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/26/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- GET
- CONVERSATION_GROUP_TSQL
- GET_TSQL
- GET_CONVERSATION_GROUP_TSQL
- GET CONVERSATION GROUP
- CONVERSATION GROUP
- GET CONVERSATION
- GET_CONVERSATION_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- GET CONVERSATION GROUP statement
- conversations [Service Broker], groups
ms.assetid: 4da8a855-33c0-43b2-a49d-527487cb3b5c
caps.latest.revision: 39
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 5cf1bd19e9ccc290c2c822ab59f00be75d447ba1
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="get-conversation-group-transact-sql"></a>GET CONVERSATION GROUP(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  다음에 받을 메시지에 대한 대화 그룹 식별자를 반환하고 해당 메시지를 포함하는 대화에 대한 대화 그룹을 잠급니다. 대화 그룹 식별자는 메시지 자체를 받기 전에 대화 상태 정보를 검색하는 데 사용할 수 있습니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
[ WAITFOR ( ]  
   GET CONVERSATION GROUP @conversation_group_id  
      FROM <queue>  
[ ) ] [ , TIMEOUT timeout ]  
[ ; ]  
  
<queue> ::=  
{  
    [ database_name . [ schema_name ] . | schema_name . ] queue_name  
}  
```  
  
## <a name="arguments"></a>인수  
 WAITFOR  
 현재 메시지가 없으면 메시지가 큐에 도착할 때까지 GET CONVERSATION GROUP 문이 대기하도록 지정합니다.  
  
 *@conversation_group_id*  
 GET CONVERSATION GROUP 문에서 반환한 대화 그룹 ID를 저장하는 데 사용되는 변수입니다. 변수 형식 이어야 합니다 **uniqueidentifier**합니다. 사용할 수 있는 대화 그룹이 없으면 변수가 NULL로 설정됩니다.  
  
 FROM  
 대화 그룹을 가져올 큐를 지정합니다.  
  
 *database_name*  
 대화 그룹을 가져올 큐를 포함하는 데이터베이스의 이름입니다. No *database_name* 제공 되는 현재 데이터베이스에 대 한 기본값입니다.  
  
 *schema_name*  
 대화 그룹을 가져올 큐를 소유하는 스키마의 이름입니다. No *schema_name* 제공 되는 현재 사용자의 기본 스키마는 기본값입니다.  
  
 *queue_name*  
 대화 그룹을 가져올 큐의 이름입니다.  
  
 제한 시간 *제한 시간*  
 메시지가 큐에 도착할 때까지 Service Broker에서 대기하는 시간(밀리초)을 지정합니다. 이 절은 WAITFOR 절에서만 사용할 수 있습니다. WAITFOR를 사용 하는 문이이 절이 포함 되지 않은 경우 또는 *제한 시간* -1 이면 대기 시간 제한 됩니다. 제한 시간이 만료 되 면 GET CONVERSATION GROUP 설정는  *@conversation_group_id*  변수를 NULL로 합니다.  
  
## <a name="remarks"></a>주의  
  
> [!IMPORTANT]  
>  위의 문은 세미콜론으로 종료 해야 GET CONVERSATION GROUP 문이 일괄 처리 또는 저장된 프로시저의 첫 번째 문이 아닌 경우 (**;**), [!INCLUDE[tsql](../../includes/tsql-md.md)] 문 종결자입니다.  
  
 GET CONVERSATION GROUP 문에 지정된 큐를 사용할 수 없으면 [!INCLUDE[tsql](../../includes/tsql-md.md)] 오류가 발생하여 문이 실패합니다.  
  
 이 문은 아래 조건이 모두 충족되는 경우 다음 대화 그룹을 반환합니다.  
  
-   대화 그룹을 성공적으로 잠글 수 있습니다.  
  
-   큐에 대화 그룹이 사용할 수 있는 메시지가 있습니다.  
  
-   대화 그룹이 앞서 나열한 조건을 충족하는 모든 대화 그룹 중에서 가장 높은 우선 순위를 가집니다. 대화 그룹의 우선 순위 수준이 그룹 멤버인 모든 대화에 할당된 우선 순위 중에서 가장 높으며 큐에 메시지가 있습니다.  
  
 같은 트랜잭션 내에서 GET CONVERSATION GROUP을 연속 호출하면 둘 이상의 대화 그룹이 잠길 수 있습니다. 사용 가능한 대화 그룹이 없으면 대화 그룹 식별자로 NULL이 반환됩니다.  
  
 WAITFOR 절을 지정하면 문은 지정된 제한 시간 동안 대기하거나 대화 그룹을 사용할 수 있을 때까지 대기합니다. 문이 대기하는 동안 큐가 삭제되면 즉시 오류가 반환됩니다.  
  
 GET CONVERSATION GROUP은 사용자 정의 함수에 유효하지 않습니다.  
  
## <a name="permissions"></a>Permissions  
 큐에서 대화 그룹 식별자를 가져오려면 현재 사용자가 큐에 대한 RECEIVE 권한을 가져야 합니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-getting-a-conversation-group-waiting-indefinitely"></a>1. 무한 대기하여 대화 그룹 가져오기  
 다음 예에서는 `@conversation_group_id`를 `ExpenseQueue`에 있는 사용 가능한 다음 메시지의 대화 그룹 식별자로 설정합니다. 명령은 메시지를 사용할 수 있게 될 때까지 대기합니다.  
  
```  
DECLARE @conversation_group_id UNIQUEIDENTIFIER ;  
  
WAITFOR (  
 GET CONVERSATION GROUP @conversation_group_id  
     FROM ExpenseQueue  
) ;  
```  
  
### <a name="b-getting-a-conversation-group-waiting-one-minute"></a>2. 1분간 대기하여 대화 그룹 가져오기  
 다음 예에서는 `@conversation_group_id`를 `ExpenseQueue`에 있는 사용 가능한 다음 메시지의 대화 그룹 식별자로 설정합니다. 1분 이내에 사용 가능한 메시지가 없으면 GET CONVERSATION GROUP이 `@conversation_group_id` 값을 그대로 반환합니다.  
  
```  
DECLARE @conversation_group_id UNIQUEIDENTIFIER  
  
WAITFOR (  
    GET CONVERSATION GROUP @conversation_group_id   
    FROM ExpenseQueue ),  
TIMEOUT 60000 ;  
```  
  
### <a name="c-getting-a-conversation-group-returning-immediately"></a>3. 즉시 실행하여 대화 그룹 가져오기  
 다음 예에서는 `@conversation_group_id`를 `ExpenseQueue`에 있는 사용 가능한 다음 메시지의 대화 그룹 식별자로 설정합니다. 사용 가능한 메시지가 없으면 `GET CONVERSATION GROUP`은 `@conversation_group_id`를 변경하지 않은 채 즉시 반환합니다.  
  
```  
DECLARE @conversation_group_id UNIQUEIDENTIFIER ;  
  
GET CONVERSATION GROUP @conversation_group_id  
FROM AdventureWorks.dbo.ExpenseQueue ;  
```  
  
## <a name="see-also"></a>관련 항목:  
 [BEGIN DIALOG conversation&#40; Transact SQL &#41;](../../t-sql/statements/begin-dialog-conversation-transact-sql.md)   
 [MOVE CONVERSATION &#40; Transact SQL &#41;](../../t-sql/statements/move-conversation-transact-sql.md)  
  
  
