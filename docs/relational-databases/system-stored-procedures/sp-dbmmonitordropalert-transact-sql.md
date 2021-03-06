---
title: sp_dbmmonitordropalert (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_dbmmonitordropalert_TSQL
- sp_dbmmonitordropalert
dev_langs:
- TSQL
helpviewer_keywords:
- database mirroring [SQL Server], monitoring
- sp_dbmmonitordropalert
ms.assetid: fe4a134b-25bf-464e-a5c4-358de215b65a
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: d21b966df55cc796fb97c3994e37b87ba62501d2
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47708051"
---
# <a name="spdbmmonitordropalert-transact-sql"></a>sp_dbmmonitordropalert(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  임계값을 NULL로 설정하여 지정한 성능 메트릭에 대한 경고를 삭제합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_dbmmonitordropalert database_name   
    [ , alert_id ]   
```  
  
## <a name="arguments"></a>인수  
 *database_name*  
 지정한 경고 임계값을 삭제할 데이터베이스를 지정합니다.  
  
 *alert_id*  
 삭제될 경고를 식별하는 정수 값입니다. 이 인수를 생략하면 데이터베이스의 모든 경고가 삭제됩니다. 특정 성능 메트릭에 대한 경고를 삭제하려면 다음 값 중 하나를 지정합니다.  
  
|값|성능 메트릭|경고 임계값|  
|-----------|------------------------|-----------------------|  
|1|보내지 않은 가장 오래된 트랜잭션|주 서버 인스턴스에서 경고가 생성되기까지 Send Queue에 누적될 수 있는 트랜잭션에 해당하는 시간(분)을 지정합니다. 이 경고는 시간을 기준으로 발생 가능한 데이터 손실을 측정하는 데 도움이 되며 특히 성능 우선 모드와 관련이 있습니다. 그러나 파트너의 연결이 끊어져 미러링이 일시 중지되거나 일시 중단되면 이 경고는 보호 우선 모드와도 관련이 있습니다.|  
|2|보내지 않은 로그|주 서버 인스턴스에서 경고를 생성하는 보내지 않은 로그 크기(KB)를 지정합니다. 이 경고는 KB를 기준으로 발생 가능한 데이터 손실을 측정하는 데 도움이 되며 특히 성능 우선 모드와 관련이 있습니다. 그러나 파트너의 연결이 끊어져 미러링이 일시 중지되거나 일시 중단되면 이 경고는 보호 우선 모드와도 관련이 있습니다.|  
|3|복원되지 않은 로그|미러 서버 인스턴스에서 경고를 생성하는 복원되지 않은 로그 크기(KB)를 지정합니다. 이 경고는 장애 조치(Failover) 시간을 측정하는 데 도움이 됩니다. *장애 조치 시간* 은 주로 이전 미러 서버에서 Redo Queue에 남아 있는 로그를 롤포워드해야 하는 시간과 짧은 추가 시간으로 구성됩니다.|  
|4|미러 커밋 오버헤드|주 서버에서 경고가 생성되기까지 허용되는 트랜잭션당 평균 지연 시간(밀리초)을 지정합니다. 이 지연 시간은 주 서버 인스턴스에서 미리 서버 인스턴스가 트랜잭션 로그 레코드를 Redo Queue에 쓸 때까지 대기하는 동안 발생한 오버헤드 양입니다. 이 값은 보호 우선 모드에만 해당됩니다.|  
|5|보존 기간|데이터베이스 미러링 상태 테이블의 행이 유지되는 기간을 제어하는 메타데이터입니다.|  
  
> [!NOTE]  
>  이 절차를 사용 하 여 지정 된 여부에 관계 없이 경고 임계값을 삭제 **sp_dbmmonitorchangealert** 또는 데이터베이스 미러링 모니터입니다.  
  
 경고에 해당 하는 이벤트 Id에 대 한 정보를 참조 하세요 [사용 하 여 경고 임계값 및 경고 미러링 성능 메트릭에 대 한 &#40;SQL Server&#41;](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)합니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 없음  
  
## <a name="result-sets"></a>결과 집합  
 없음  
  
## <a name="permissions"></a>사용 권한  
 **sysadmin** 고정 서버 역할의 멤버 자격이 필요합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] 데이터베이스의 보존 기간 설정을 삭제합니다.  
  
```  
EXEC sp_dbmmonitordropalert AdventureWorks2012, 5;  
```  
  
 다음 예에서는 [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] 데이터베이스의 보존 기간과 모든 경고 임계값을 삭제합니다.  
  
```  
EXEC sp_dbmmonitordropalert AdventureWorks2012 ;  
```  
  
## <a name="see-also"></a>관련 항목  
 [데이터베이스 미러링 모니터링&#40;SQL Server&#41;](../../database-engine/database-mirroring/monitoring-database-mirroring-sql-server.md)   
 [sp_dbmmonitorchangealert&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dbmmonitorchangealert-transact-sql.md)  
  
  
