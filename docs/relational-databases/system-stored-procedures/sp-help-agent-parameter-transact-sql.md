---
title: sp_help_agent_parameter (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to: SQL Server
f1_keywords:
- sp_help_agent_parameter
- sp_help_agent_parameter_TSQL
helpviewer_keywords: sp_help_agent_parameter
ms.assetid: 8fb4a9c3-19af-4a34-8004-572729ba3d15
caps.latest.revision: "29"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 4c9e97d300b834c6f8182379cf2265d9fd5327d7
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="sphelpagentparameter-transact-sql"></a>sp_help_agent_parameter(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  프로필의 모든 매개 변수가 반환 된 [MSagent_parameters &#40; Transact SQL &#41; ](../../relational-databases/system-tables/msagent-parameters-transact-sql.md) 시스템 테이블입니다. 이 저장 프로시저는 에이전트가 실행되고 있는 모든 데이터베이스의 배포자에서 실행될 수 있습니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_help_agent_parameter [ [ @profile_id = ] profile_id ]  
```  
  
## <a name="arguments"></a>인수  
 [  **@profile_id=**] *profile_id*  
 프로필의 id는 [MSagent_parameters &#40; Transact SQL &#41; ](../../relational-databases/system-tables/msagent-parameters-transact-sql.md) 테이블입니다. *profile_id* 은 **int**, 기본값은 **-1**, 모든 매개 변수를 반환 하는 합니다.  
  
## <a name="result-sets"></a>결과 집합  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**profile_id**|**int**|에이전트 프로필의 ID입니다.|  
|**p a r a**|**sysname**|매개 변수의 이름입니다.|  
|**값**|**nvarchar(255)**|매개 변수의 값입니다.|  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="remarks"></a>주의  
 **sp_help_agent_parameter** 모든 유형의 복제에 사용 됩니다.  
  
## <a name="permissions"></a>Permissions  
 구성원만는 **sysadmin** 고정된 서버 역할 또는 **replmonitor** 고정된 데이터베이스 역할을 실행할 수 있는 **sp_help_agent_parameter**합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [복제 에이전트 프로필 작업](../../relational-databases/replication/agents/work-with-replication-agent-profiles.md)   
 [sp_add_agent_parameter &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-add-agent-parameter-transact-sql.md)   
 [sp_drop_agent_parameter &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-drop-agent-parameter-transact-sql.md)   
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  