---
title: sp_delete_backup_file_snapshot (Transact SQL) | Microsoft Docs
ms.date: 08/09/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.custom: 
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: TSQL
ms.assetid: 5afe5530-a404-4fa5-af3c-bc7c3ca43ce6
caps.latest.revision: "9"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 4cf8bf8484e77c15c951ca548ce00baccfaf5b38
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="snapshot-backup---spdeletebackupfilesnapshot"></a>스냅숏 백업-sp_delete_backup_file_snapshot
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  지정된 된 데이터베이스에서 지정한 백업 스냅숏을 삭제합니다. 이 시스템 저장 프로시저와 함께에서 사용 하 여는 **sys.fn_db_backup_file_snapshots** 분리 된 백업 스냅숏 시스템 함수를 식별 하 고 삭제 합니다. 자세한 내용은 [Azure의 데이터베이스 파일에 대한 파일-스냅숏 백업](../../relational-databases/backup-restore/file-snapshot-backups-for-database-files-in-azure.md)을 참조하세요.  

  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sys.sp_delete_backup_file_snapshot  
    [ @db_name = ] N’<database_name>  
    , [ @snapshot_url = ] N’<snapshot_url>  
```  
  
## <a name="arguments"></a>인수  
 *[ @db_name =] database_name*  
 스냅숏 삭제, 유니코드 문자열로 지정 된 수를 포함 하는 데이터베이스의 이름입니다.  
  
 *[ @snapshot_url =] snapshot_url*  
 스냅숏 삭제, 유니코드 문자열 변수로 제공 될 URL입니다.  
  
## <a name="permissions"></a>Permissions  
 ALTER ANY DATABASE 권한이 필요합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [sys.fn_db_backup_file_snapshots&#40; Transact SQL &#41;](../../relational-databases/system-functions/sys-fn-db-backup-file-snapshots-transact-sql.md)   
 [sp_delete_backup&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/snapshot-backup-sp-delete-backup.md)  
  
  