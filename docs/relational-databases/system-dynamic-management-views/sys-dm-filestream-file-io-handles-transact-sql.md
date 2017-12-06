---
title: sys.dm_filestream_file_io_handles (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- dm_filestream_file_io_handles
- sys.dm_filestream_file_io_handles
- dm_filestream_file_io_handles_TSQL
- sys.dm_filestream_file_io_handles_TSQL
dev_langs: TSQL
helpviewer_keywords: sys.dm_filestream_file_io_handle catalog view
ms.assetid: e59632f4-3292-419f-9217-ca375749f1a5
caps.latest.revision: "10"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 46b8bd6e5696cf9a2e1b3d1f460e5f1885ed2009
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmfilestreamfileiohandles-transact-sql"></a>sys.dm_filestream_file_io_handles(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  NSO(네임스페이스 소유자)가 인식하는 파일 핸들을 표시합니다. 클라이언트를 사용 하 여 가져온 파일 스트림 핸들이 **OpenSqlFilestream** 이 보기에 표시 됩니다.  
  
|열|형식|Description|  
|------------|----------|-----------------|  
|**handle_context_address**|**varbinary (8)**|클라이언트의 핸들과 연결된 내부 NSO 구조의 주소를 표시합니다. Null을 허용합니다.|  
|**creation_request_id**|**int**|이 핸들을 만드는 데 사용된 REQ_PRE_CREATE I/O 요청의 필드를 표시합니다. Null을 허용하지 않습니다.|  
|**creation_irp_id**|**int**|이 핸들을 만드는 데 사용된 REQ_PRE_CREATE I/O 요청의 필드를 표시합니다. Null을 허용하지 않습니다.|  
|**handle_id**|**int**|드라이버가 할당한 이 핸들의 고유한 ID를 표시합니다. Null을 허용하지 않습니다.|  
|**creation_client_thread_id**|**varbinary (8)**|이 핸들을 만드는 데 사용된 REQ_PRE_CREATE I/O 요청의 필드를 표시합니다. Null을 허용합니다.|  
|**creation_client_process_id**|**varbinary (8)**|이 핸들을 만드는 데 사용된 REQ_PRE_CREATE I/O 요청의 필드를 표시합니다. Null을 허용합니다.|  
|**filestream_transaction_id**|**varbinary(128)**|지정된 핸들과 연결된 트랜잭션의 ID를 표시합니다. 이 반환한 값은 고 **get_filestream_transaction_context** 함수입니다. 이 필드를 사용 하 여를 조인 하는 **sys.dm_filestream_file_io_requests** 보기. Null을 허용합니다.|  
|**access_type**|**nvarchar (60)**|Null을 허용하지 않습니다.|  
|**logical_path를 수집**|**nvarchar(256)**|이 핸들이 연 파일의 논리적 경로 이름을 표시합니다. 반환 되는 동일한 경로 이름에서 **합니다. PathName** 방식의 **varbinary**(**max**) filestream 합니다. Null을 허용합니다.|  
|**physical_path를 수집**|**nvarchar(256)**|파일의 실제 NTFS 경로 이름을 표시합니다. 동일한 경로 이름에서 반환 되는 **합니다. PhysicalPathName** 의 메서드는 **varbinary**(**max**) filestream 합니다. 추적 플래그 5556에 의해 설정됩니다. Null을 허용합니다.|  
  
## <a name="permissions"></a>Permissions  
 을 실행하려면 서버에 대해 VIEW SERVER STATE 권한이 필요합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [Filestream 및 FileTable 동적 관리 뷰 &#40; Transact SQL &#41;](../../relational-databases/system-dynamic-management-views/filestream-and-filetable-dynamic-management-views-transact-sql.md)  
  
  