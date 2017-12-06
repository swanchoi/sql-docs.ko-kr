---
title: sp_help_category (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 08/09/2016
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
- sp_help_category
- sp_help_category_TSQL
dev_langs: TSQL
helpviewer_keywords: sp_help_category
ms.assetid: 8cad1dcc-b43e-43bd-bea0-cb0055c84169
caps.latest.revision: "18"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: efec4c1ef04ef95e74ef13479b5f51cfe2d84bdb
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="sphelpcategory-transact-sql"></a>sp_help_category(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  지정된 클래스의 작업, 경고 또는 운영자에 관한 정보를 제공합니다.  
   
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_help_category [ [ @class = ] 'class' ]   
     [ , [ @type = ] 'type' ]   
     [ , [ @name = ] 'name' ]   
     [ , [ @suffix = ] suffix ]   
```  
  
## <a name="arguments"></a>인수  
 [  **@class=**] **'***클래스***'**  
 정보를 요청한 대상 클래스입니다. *클래스* 은 **varchar(8)**의 기본값은 **작업**합니다. *클래스* 다음이 값 중 하나일 수 있습니다.  
  
|값|Description|  
|-----------|-----------------|  
|**작업**|작업 범주에 관한 정보를 제공합니다.|  
|**경으십시오**|경고 범주에 관한 정보를 제공합니다.|  
|**연산자**|운영자 범주에 관한 정보를 제공합니다.|  
  
 [  **@type=** ] **'***형식***'**  
 정보를 요청한 대상 범주의 유형입니다. *형식* 은 **varchar(12)**, 기본값은 NULL 이며 다음이 값 중 하나일 수 있습니다.  
  
|값|Description|  
|-----------|-----------------|  
|**로컬**|로컬 작업 범주입니다.|  
|**다중-서버**|다중 서버 작업 범주입니다.|  
|**NONE**|이외의 다른 클래스에 대 한 범주 **작업**합니다.|  
  
 [  **@name=** ] **'***이름***'**  
 정보를 요청한 대상 범주의 이름입니다. *이름* 은 **sysname**, 기본값은 NULL입니다.  
  
 [  **@suffix=** ] *접미사*  
 지정 여부는 **category_type** 결과 집합의 열은 ID 또는 이름이 있습니다. *접미사* 은 **비트**, 기본값은 **0**합니다. **1** 표시는 **category_type** 를 이름으로 및 **0** ID로 표시 합니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="result-sets"></a>결과 집합  
 때  **@suffix**  은 **0**, **sp_help_category** 다음 결과 집합을 반환 합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**category_id**|**int**|범주 ID입니다.|  
|**category_type**|**tinyint**|범주의 유형입니다.<br /><br /> **1** = 로컬<br /><br /> **2** = 다중 서버<br /><br /> **3** = 없음|  
|**name**|**sysname**|범주의 이름입니다.|  
  
 때  **@suffix**  은 **1**, **sp_help_category** 다음 결과 집합을 반환 합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**category_id**|**int**|범주 ID입니다.|  
|**category_type**|**sysname**|범주의 유형입니다. 중 하나 **로컬**, **MULTI-SERVER**, 또는 **NONE**|  
|**name**|**sysname**|범주의 이름입니다.|  
  
## <a name="remarks"></a>주의  
 **sp_help_category** 에서 실행 되어야 합니다는 **msdb** 데이터베이스입니다.  
  
 매개 변수가 지정되지 않은 경우에는 결과 집합이 모든 작업 범주에 관한 정보를 제공합니다.  
  
## <a name="permissions"></a>Permissions  
 기본적으로 **sysadmin** 고정 서버 역할의 멤버는 이 저장 프로시저를 실행할 수 있습니다. 다른 사용자는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] msdb **데이터베이스의 다음** 에이전트 고정 데이터베이스 역할 중 하나를 부여 받아야 합니다.  
  
-   **SQLAgentUserRole**  
  
-   **SQLAgentReaderRole**  
  
-   **SQLAgentOperatorRole**  
  
 이러한 역할의 사용 권한에 대한 자세한 내용은 [SQL Server 에이전트 고정 데이터베이스 역할](http://msdn.microsoft.com/library/719ce56b-d6b2-414a-88a8-f43b725ebc79)을 참조하세요.  
  
## <a name="examples"></a>예  
  
### <a name="a-returning-local-job-information"></a>1. 로컬 작업 정보 반환  
 다음 예에서는 로컬로 관리되는 작업에 대한 정보를 반환합니다.  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_help_category  
    @type = N'LOCAL' ;  
GO  
```  
  
### <a name="b-returning-alert-information"></a>2. 경고 정보 반환  
 다음 예에서는 복제 경고 범주에 대한 정보를 반환합니다.  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_help_category  
    @class = N'ALERT',  
    @name = N'Replication' ;  
GO  
```  
  
## <a name="see-also"></a>관련 항목:  
 [sp_add_category &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-add-category-transact-sql.md)   
 [sp_delete_category &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-delete-category-transact-sql.md)   
 [sp_update_category &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-update-category-transact-sql.md)   
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  