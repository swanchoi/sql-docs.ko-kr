---
title: sp_helpreplicationoption (Transact SQL) | Microsoft Docs
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
- sp_helpreplicationoption
- sp_helpreplicationoption_TSQL
helpviewer_keywords: sp_helpreplicationoption
ms.assetid: ef988dbc-dd0b-4132-80ab-81eebec1cffe
caps.latest.revision: "25"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 378a931a86932be4535906f34432d2a4ea2356e9
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="sphelpreplicationoption-transact-sql"></a>sp_helpreplicationoption(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  서버에 대해 사용할 수 있는 복제 옵션 유형을 표시합니다. 이 저장 프로시저는 모든 데이터베이스의 모든 서버에서 실행됩니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_helpreplicationoption [ [ @optname =] 'option_name' ]  
```  
  
## <a name="arguments"></a>인수  
 [  **@optname =**] **'***option_name***'**  
 쿼리할 복제 옵션의 이름입니다. *option_name* 은 **sysname**, 기본값은 NULL입니다.  
  
|값|Description|  
|-----------|-----------------|  
|**트랜잭션**|트랜잭션 복제를 사용하는 경우 반환되는 결과 집합입니다.|  
|**병합**|병합 복제를 사용하는 경우 반환되는 결과 집합입니다.|  
|NULL(기본값)|결합 집합이 반환되지 않습니다.|  
  
## <a name="result-sets"></a>결과 집합  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**optname**|**sysname**|복제 옵션의 이름이며 다음 중 하나입니다.<br /><br /> **트랜잭션**<br /><br /> **병합**|  
|**값**|**bit**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**major_version**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**minor_version**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**수정 버전**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**install_failures**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="remarks"></a>주의  
 **sp_helpreplicationoption** 복제 옵션을 특정 서버에서 사용 하는 방법에 대 한 정보를 가져오는 데 사용 됩니다. 특정 데이터베이스에 대 한 정보를 가져오려면 **sp_helpreplicationdboption**합니다.  
  
## <a name="permissions"></a>Permissions  
 실행 권한은 기본적으로 **public** 역할로 설정됩니다.  
  
## <a name="see-also"></a>관련 항목:  
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  