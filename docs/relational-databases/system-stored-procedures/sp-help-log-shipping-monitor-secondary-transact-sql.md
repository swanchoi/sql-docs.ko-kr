---
title: sp_help_log_shipping_monitor_secondary (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 08/02/2016
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
- sp_help_log_shipping_monitor_secondary
- sp_help_log_shipping_monitor_secondary_TSQL
dev_langs: TSQL
helpviewer_keywords: sp_help_log_shipping_monitor_secondary
ms.assetid: 3ac091ea-c9a8-4c05-a0b6-1ccf4e001339
caps.latest.revision: "22"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 612571cd299a0474b1d405d8d9885487eba70a16
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="sphelplogshippingmonitorsecondary-transact-sql"></a>sp_help_log_shipping_monitor_secondary(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  모니터 테이블에서 보조 데이터베이스에 대한 정보를 반환합니다.  
  
 
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_help_log_shipping_monitor_secondary  
[ @secondary_server = ] 'secondary_server',  
[ @secondary_database = ] 'secondary_database'  
```  
  
## <a name="arguments"></a>인수  
 [  **@secondary_server =** ] '*secondary_server*'  
 보조 서버의 이름입니다. *secondary_server* 은 **sysname**, 기본값은 없습니다.  
  
 [  **@secondary_database =** ] '*secondary_database*'  
 보조 데이터베이스의 이름입니다. *secondary_database* 은 **sysname**, 기본값은 없습니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 1(실패)  
  
## <a name="result-sets"></a>결과 집합  
  
|열|Description|  
|------------|-----------------|  
|**secondary_server**|보조 인스턴스의 이름에서 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] 로그 전달 구성의 합니다.|  
|**secondary_database**|로그 전달 구성의 보조 데이터베이스의 이름입니다.|  
|**secondary_id**|로그 전달 구성의 보조 서버의 ID입니다.|  
|**primary_server**|로그 전달 구성의 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]에 대한 주 인스턴스 이름입니다.|  
|**primary_database**|로그 전달 구성의 주 데이터베이스의 이름입니다.|  
|**restore_threshold**|복원 작업 간 허용되는 시간(분)입니다. 이 시간이 지나면 경고가 발생합니다.|  
|**threshold_alert**|복원 임계값을 초과할 경우 발생하는 경고입니다.|  
|**threshold_alert_enabled**|복원 임계값 경고를 설정할지 여부를 결정합니다.<br /><br /> 1 = 사용.<br /><br /> 0 = 사용 안 함.|  
|**last_copied_file**|보조 서버로 복사된 마지막 백업 파일의 파일 이름입니다.|  
|**last_copied_date**|보조 서버에 수행된 마지막 복사 작업의 시간과 날짜입니다.|  
|**last_copied_date_utc**|보조 서버에 수행된 마지막 복사 작업의 시간과 날짜(UTC)입니다.|  
|**last_restored_file**|보조 데이터베이스에 복원된 마지막 백업 파일의 이름입니다.|  
|**last_restored_date**|보조 데이터베이스에 수행된 마지막 복원 작업의 시간과 날짜입니다.|  
|**last_restored_date_utc**|보조 데이터베이스에 수행된 마지막 복원 작업의 시간과 날짜(UTC)입니다.|  
|**history_retention_period**|지정된 보조 데이터베이스에서 로그 전달 기록 레코드가 삭제되기까지 보관되는 기간(분)입니다.|  
  
## <a name="remarks"></a>주의  
 **sp_help_log_shipping_monitor_secondary** 에서 실행 되어야 합니다는 **마스터** 모니터 서버에는 데이터베이스입니다.  
  
## <a name="permissions"></a>Permissions  
 구성원만는 **sysadmin** 고정된 서버 역할에서이 프로시저를 실행할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [로그 전달 정보&#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  