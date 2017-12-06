---
title: sp_add_maintenance_plan_job (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
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
- sp_add_maintenance_plan_job_TSQL
- sp_add_maintenance_plan_job
dev_langs: TSQL
helpviewer_keywords: sp_add_maintenance_plan_job
ms.assetid: 7205855c-964f-4f55-bf75-39a55f6fe7bd
caps.latest.revision: "32"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 89b05f5e2a9f4fb2d2e60938d24c191412b28d67
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2017
---
# <a name="spaddmaintenanceplanjob-transact-sql"></a>sp_add_maintenance_plan_job(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  유지 관리 계획과 기존 작업을 연결합니다.  
  
> [!NOTE]  
>  이 저장 프로시저는 데이터베이스 유지 관리 계획에 사용됩니다. 이 기능은 이러한 저장 프로시저를 사용하지 않는 유지 관리 계획으로 바뀌었습니다. 이 프로시저를 사용하여 이전 버전의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 업그레이드된 설치에 대한 데이터베이스 유지 관리 계획을 유지할 수 있습니다.  
  
 [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_add_maintenance_plan_job [ @plan_id = ] 'plan_id' , [ @job_id = ] 'job_id'  
```  
  
## <a name="arguments"></a>인수  
 [  **@plan_id =**] **'***plan_id***'**  
 유지 관리 계획의 ID를 지정합니다. *plan_id* 은 **uniqueidentifier**, 이며 유효한 ID 여야 합니다  
  
 [  **@job_id =**] **'***job_id***'**  
 유지 관리 계획과 연관된 작업의 ID를 지정합니다. *job_id* 은 **uniqueidentifier**, 이며 유효한 ID 여야 합니다 실행 작업 또는 작업을 만들려면 **sp_add_job**, 하거나 SQL Server Management Studio를 사용 합니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 1(실패)  
  
## <a name="remarks"></a>주의  
 **sp_add_maintenance_plan_job** 에서 실행 되어야 합니다는 **msdb** 데이터베이스입니다.  
  
## <a name="permissions"></a>Permissions  
 구성원만는 **sysadmin** 고정된 서버 역할을 실행할 수 있는 **sp_add_maintenance_plan_job**합니다.  
  
## <a name="examples"></a>예  
 이 예제에서는 "B8FCECB1-E22C-11D2-AA64-00C04F688EAE" 작업을 사용 하 여 만든 유지 관리 계획에 추가 **sp_add_maintenance_plan_job**합니다.  
  
```  
EXECUTE   sp_add_maintenance_plan_job N'FAD6F2AB-3571-11D3-9D4A-00C04FB925FC', N'B8FCECB1-E22C-11D2-AA64-00C04F688EAE';  
```  
  
## <a name="see-also"></a>관련 항목:  
 [유지 관리 계획](../../relational-databases/maintenance-plans/maintenance-plans.md)   
 [데이터베이스 유지 관리 계획 저장 프로시저 &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/database-maintenance-plan-stored-procedures-transact-sql.md)  
  
  