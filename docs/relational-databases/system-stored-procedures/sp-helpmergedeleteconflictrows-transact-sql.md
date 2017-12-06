---
title: sp_helpmergedeleteconflictrows (Transact SQL) | Microsoft Docs
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
- sp_helpmergedeleteconflictrows
- sp_helpmergedeleteconflictrows_TSQL
helpviewer_keywords: sp_helpmergedeleteconflictrows
ms.assetid: 222be651-5690-4341-9dfb-f9ec1d80c970
caps.latest.revision: "17"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: af2e83f26bfe8f94dd0befcc71259c4d04ed148a
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="sphelpmergedeleteconflictrows-transact-sql"></a>sp_helpmergedeleteconflictrows(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  삭제 충돌이 손실되는 데이터 행에 대한 정보를 반환합니다 이 저장 프로시저는 게시 데이터베이스의 게시자 또는 구독 데이터베이스의 구독자에서 분산 충돌 로깅을 사용할 때 실행됩니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_helpmergedeleteconflictrows [ [ @publication = ] 'publication']  
    [ , [ @source_object = ] 'source_object']  
    [ , [ @publisher = ] 'publisher'  
    [ , [ @publisher_db = ] 'publsher_db'  
```  
  
## <a name="arguments"></a>인수  
 [  **@publication=**] **'***게시***'**  
 게시의 이름입니다. *게시* 은 **sysname**, 기본값은  **%** 합니다. 게시가 지정된 경우에는 해당 게시에 대한 모든 충돌이 반환됩니다.  
  
 [  **@source_object=**] **'***source_object***'**  
 원본 개체의 이름입니다. *source_object* 은 **nvarchar (386)**, 기본값은 NULL입니다.  
  
 [  **@publisher=**] **'***게시자***'**  
 게시자의 이름이입니다. *게시자* 은 **sysname**, 기본값은 NULL입니다.  
  
 [  **@publisher_db=**] **'***publisher_db***'**  
 게시자 데이터베이스의 이름이입니다. *publisher_db* 은 **sysname**, 기본값은 NULL입니다.  
  
## <a name="result-sets"></a>결과 집합  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**source_object**|**nvarchar (386)**|삭제 충돌의 원본 개체입니다.|  
|**rowguid**|**uniqueidentifier**|삭제 충돌에 대한 행 식별자입니다.|  
|**conflict_type**|**int**|충돌 유형을 표시하는 코드입니다.<br /><br /> **1** UpdateConflict =: 충돌이 행 수준에서 검색 됩니다.<br /><br /> **2** ColumnUpdateConflict =: 충돌이 열 수준에서 검색 합니다.<br /><br /> **3** UpdateDeleteWinsConflict =: 삭제가 충돌에서 승리 합니다.<br /><br /> **4** UpdateWinsDeleteConflict =: 충돌에서 패한 삭제 된 rowguid가이 테이블에 기록 됩니다.<br /><br /> **5** UploadInsertFailed =: 게시자에 구독자에서 삽입을 적용할 수 없습니다.<br /><br /> **6** DownloadInsertFailed =: 구독자에서 게시자에서의 삽입을 적용할 수 없습니다.<br /><br /> **7** UploadDeleteFailed =: 구독자에서의 삭제를 게시자로 업로드할 수 없습니다.<br /><br /> **8** DownloadDeleteFailed =: 게시자에서의 삭제를 구독자로 다운로드할 수 없습니다.<br /><br /> **9** UploadUpdateFailed =: 게시자에 구독자에서 업데이트를 적용할 수 없습니다.<br /><br /> **10** 수행 된 업데이트가: 구독자에 게시자에서 업데이트를 적용할 수 없습니다.|  
|**reason_code**|**Int**|상황에 맞는 오류 코드입니다.|  
|**reason_text**|**varchar(720)**|상황에 맞는 오류 설명입니다.|  
|**origin_datasource**|**varchar (255)**|충돌의 시작입니다.|  
|**pubid**|**uniqueidentifier**|게시 식별자입니다.|  
|**MSrepl_create_time**|**datetime**|충돌 정보가 추가된 시간입니다.|  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="remarks"></a>주의  
 **sp_helpmergedeleteconflictrows** 병합 복제에 사용 됩니다.  
  
## <a name="permissions"></a>Permissions  
 구성원만는 **sysadmin** 고정된 서버 역할 및 **db_owner** 고정된 데이터베이스 역할을 실행할 수 있는 **sp_helpmergedeleteconflictrows**합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  