---
title: sp_changesubscriptiondtsinfo (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/04/2017
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
- sp_changesubscriptiondtsinfo
- sp_changesubscriptiondtsinfo_TSQL
helpviewer_keywords: sp_changesubscriptiondtsinfo
ms.assetid: 64fc085f-f81b-493b-b59a-ee6192d9736d
caps.latest.revision: "16"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 6b551a265d30632f7ee96c86b78191388099c7d0
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="spchangesubscriptiondtsinfo-transact-sql"></a>sp_changesubscriptiondtsinfo(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  구독의 DTS(데이터 변환 서비스) 패키지 속성을 변경합니다. 이 저장 프로시저는 구독 데이터베이스의 구독자에서 실행됩니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_changesubscriptiondtsinfo [ [ @job_id = ] job_id ]  
    [ , [ @dts_package_name= ] 'dts_package_name' ]  
    [ , [ @dts_package_password= ] 'dts_package_password' ]  
    [ , [ @dts_package_location= ] 'dts_package_location' ]  
```  
  
## <a name="arguments"></a>인수  
 [  **@job_id=**] *job_id*  
 밀어넣기 구독에 대한 배포 에이전트의 작업 ID입니다. *job_id* 은 **varbinary (16)**, 기본값은 없습니다. 배포 작업 ID를 확인 하려면 실행 **sp_helpsubscription** 또는 **sp_helppullsubscription**합니다.  
  
 [  **@dts_package_name** =] **'***dts_package_name***'**  
 DTS 패키지의 이름을 지정합니다. *dts_package_name* 는 **sysname**, 기본값은 NULL입니다. 예를 들어 라는 패키지를 지정 하려면 **DTSPub_Package**를 지정 하는 경우 `@dts_package_name = N'DTSPub_Package'`합니다.  
  
 [  **@dts_package_password** =] **'***dts_package_password***'**  
 패키지 암호를 지정합니다. *dts_package_password* 은 **sysname** 기본값은 NULL 이며 암호 속성이 남아 있을 것 이라는 것을 지정 하는 변경 되지 않습니다.  
  
> [!NOTE]  
>  DTS 패키지에는 암호가 있어야 합니다.  
  
 [  **@dts_package_location** =] **'***dts_package_location***'**  
 패키지 위치를 지정합니다. *dts_package_location* 는 **nvarchar (12)**, 기본값은 NULL이 고 지정 하는 패키지 위치 남겨둘 변경 되지 않습니다. 패키지의 위치를 변경할 수 있습니다 **배포자** 또는 **구독자**합니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="remarks"></a>주의  
 **sp_changesubscriptiondtsinfo** 스냅숏 복제 및 트랜잭션 복제는 밀어넣기 구독에만 사용 됩니다.  
  
## <a name="permissions"></a>Permissions  
 구성원만는 **sysadmin** 고정 서버 역할, **db_owner** 고정된 데이터베이스 역할 또는 구독의 작성자 실행할 수 **sp_changesubscriptiondtsinfo**합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  