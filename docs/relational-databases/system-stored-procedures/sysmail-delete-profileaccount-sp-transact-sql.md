---
title: sysmail_delete_profileaccount_sp (TRANSACT-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sysmail_delete_profileaccount_sp
- sysmail_delete_profileaccount_sp_TSQL
dev_langs: TSQL
helpviewer_keywords: sysmail_delete_profileaccount_sp
ms.assetid: b58d06f2-d6c9-4c8e-95bd-027c50f4621a
caps.latest.revision: "45"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 67c1f60356209a9f39d0ac902fea41b5f6ec2f2a
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="sysmaildeleteprofileaccountsp-transact-sql"></a>sysmail_delete_profileaccount_sp(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  데이터베이스 메일 프로필에서 계정을 제거합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sysmail_delete_profileaccount_sp  {   [ @profile_id = ] profile_id | [ @profile_name = ] 'profile_name' } ,  
    {   [ @account_id = ] account_id | [ @account_name = ] 'account_name' }  
```  
  
## <a name="arguments"></a>인수  
 [  **@profile_id**  =] *profile_id*  
 삭제할 프로필의 ID입니다. *profile_id* 은 **int**, 기본값은 NULL입니다. 중 하나는 *profile_id* 또는 *profile_name* 지정할 수 있습니다.  
  
 [  **@profile_name**  =] **'***profile_name***'**  
 삭제할 프로필의 이름입니다. *profile_name* 은 **sysname**, 기본값은 NULL입니다. 중 하나는 *profile_id* 또는 *profile_name* 지정할 수 있습니다.  
  
 [  **@account_id**  =] *account_id*  
 삭제할 계정 ID입니다. *account_id* 은 **int**, 기본값은 NULL입니다. 중 하나는 *account_id* 또는 *account_name* 지정할 수 있습니다.  
  
 [  **@account_name**  =] **'***account_name***'**  
 삭제할 계정의 이름입니다. *account_name* 은 **sysname**, 기본값은 NULL입니다. 중 하나는 *account_id* 또는 *account_name* 지정할 수 있습니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="result-sets"></a>결과 집합  
 없음  
  
## <a name="remarks"></a>주의  
 지정된 계정과 프로필이 연관되어 있지 않으면 오류를 반환합니다.  
  
 계정은 지정되었으나 프로필이 지정되지 않은 경우 이 저장 프로시저는 모든 프로필에서 지정된 계정을 제거합니다. 예를 들어 기존 SMTP 서버를 종료하려는 경우 각 프로필에서 계정을 제거하는 대신 모든 프로필에서 SMTP 서버를 사용하는 해당 계정을 제거합니다.  
  
 프로필은 지정되었으나 계정이 지정되지 않은 경우 이 저장 프로시저는 지정된 프로필에서 모든 계정을 제거합니다. 예를 들어 프로필에서 사용하는  SMTP 서버를 변경하려는 경우 프로필에서 모든 계정을 제거한 후 필요한 만큼 새 계정을 추가하는 것이 편리할 수 있습니다.  
  
 저장된 프로시저 **sysmail_delete_profileaccount_sp** 에 **msdb** 데이터베이스에 있으며가 소유 하 고는 **dbo** 스키마입니다. 현재 데이터베이스 없는 경우 세 부분으로 이루어진 이름으로 프로시저를 실행 해야 **msdb**합니다.  
  
## <a name="permissions"></a>Permissions  
 실행의 구성원에 게이 프로시저 기본값에 대 한 권한을 **sysadmin** 고정된 서버 역할입니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 `Audit Account` 프로필에서 `AdventureWorks Administrator` 계정을 제거합니다.  
  
```  
EXECUTE msdb.dbo.sysmail_delete_profileaccount_sp  
    @profile_name = 'AdventureWorks Administrator',  
    @account_name = 'Audit Account' ;  
```  
  
## <a name="see-also"></a>관련 항목:  
 [데이터베이스 메일](../../relational-databases/database-mail/database-mail.md)   
 [데이터베이스 메일 계정 만들기](../../relational-databases/database-mail/create-a-database-mail-account.md)   
 [데이터베이스 메일 구성 개체](../../relational-databases/database-mail/database-mail-configuration-objects.md)   
 [데이터베이스 메일 저장 프로시저 &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/database-mail-stored-procedures-transact-sql.md)  
  
  