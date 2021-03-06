---
title: managed_backup.fn_is_master_switch_on (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- fn_is_master_switch_on
- fn_is_master_switch_on_TSQL
- smart_admin.fn_is_master_switch_on
- smart_admin.fn_is_master_switch_on_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- smart_admin.fn_is_master_switch_on
- fn_is_master_switch_on
ms.assetid: e8c2108d-b104-46cb-9645-a15f46112c86
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 60485350a3958eb74b5647293c7a4bbc6525ff19
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47812871"
---
# <a name="managedbackupfnismasterswitchon-transact-sql"></a>managed_backup.fn_is_master_switch_on (Transact SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  SQL Server 인스턴스에서 [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] 작업의 상태를 반환합니다.  
  
 이 함수를 사용하면 [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]의 현재 상태를 가져올 수 있습니다.  
  
 
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```sql  
managed_backup.fn_is_master_switch_on ()  
```  
  
##  <a name="Arguments"></a> 인수  
 없음  
  
## <a name="return-type"></a>반환 형식  
 **BIT**  
  
 1 = [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]이 활성 상태임, 0 = [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]이 일시 중지됨  
  
## <a name="security"></a>보안  
  
### <a name="permissions"></a>사용 권한  
 함수에 대해 SELECT 권한이 필요합니다.  
  
## <a name="see-also"></a>관련 항목  
 [Microsoft Azure에 대한 SQL Server Managed Backup](../../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md)  
  
  
