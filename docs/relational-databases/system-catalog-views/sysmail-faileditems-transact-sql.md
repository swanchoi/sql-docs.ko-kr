---
title: sysmail_faileditems (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sysmail_faileditems
- sysmail_faileditems_TSQL
dev_langs: TSQL
helpviewer_keywords: sysmail_faileditems database mail view
ms.assetid: a31562c5-358e-4cfc-a72d-b3faccc53851
caps.latest.revision: "18"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 9872591d38bfedcd0b6c4e0f28a7922ace26b849
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="sysmailfaileditems-transact-sql"></a>sysmail_faileditems(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  각 데이터베이스 메일 메시지에 대해 하나의 행을 포함는 **실패** 상태입니다. 이 뷰를 사용하여 성공적으로 보내지 못한 메시지를 확인할 수 있습니다.  
  
 데이터베이스 메일이 처리 하는 모든 메시지를 보려면 사용 [sysmail_allitems &#40; Transact SQL &#41; ](../../relational-databases/system-catalog-views/sysmail-allitems-transact-sql.md). 보내지 않은 메시지만 보려면를 사용 하 여 [sysmail_unsentitems &#40; Transact SQL &#41; ](../../relational-databases/system-catalog-views/sysmail-unsentitems-transact-sql.md). 보낸 메시지를 보려면 사용 [sysmail_sentitems &#40; Transact SQL &#41; ](../../relational-databases/system-catalog-views/sysmail-sentitems-transact-sql.md). 전자 메일 첨부 파일을 보려면 사용 하 여 [sysmail_mailattachments &#40; Transact SQL &#41; ](../../relational-databases/system-catalog-views/sysmail-mailattachments-transact-sql.md).  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**mailitem_id**|**int**|메일 큐의 메일 항목 식별자입니다.|  
|**profile_id**|**int**|메시지 전송에 사용된 프로필의 식별자입니다.|  
|**받는 사람**|**varchar(max)**|메시지를 받는 사람의 전자 메일 주소입니다.|  
|**copy_recipients**|**varchar(max)**|메시지 복사본을 받는 사람의 전자 메일 주소입니다.|  
|**blind_copy_recipients**|**varchar(max)**|메시지 복사본을 받지만 메시지 머리글에 이름이 표시되지 않는 사람의 전자 메일 주소입니다.|  
|**제목**|**nvarchar(510)**|메시지의 제목 줄입니다.|  
|**본문**|**varchar(max)**|메시지의 본문입니다.|  
|**body_format**|**varchar (20)**|메시지 본문의 형식입니다. 가능한 값은 TEXT 및 HTML입니다.|  
|**중요도**|**varchar(6)**|**중요도** 메시지의 매개 변수입니다.|  
|**민감도**|**varchar(12)**|**민감도** 메시지의 매개 변수입니다.|  
|**file_attachments**|**varchar(max)**|전자 메일 메시지에 첨부되는 파일 이름 목록으로 각 파일 이름은 세미콜론으로 구분되어 있습니다.|  
|**Attachment_encoding**|**varchar (20)**|메일 첨부 파일의 유형입니다.|  
|**쿼리**|**varchar(max)**|메일 프로그램이 실행하는 쿼리입니다.|  
|**execute_query_database**|**sysname**|메일 프로그램이 쿼리를 실행한 데이터베이스 컨텍스트입니다.|  
|**attach_query_result_as_file**|**bit**|값이 0이면 쿼리 결과가 전자 메일 메시지 본문의 내용 뒤에 포함됩니다. 값이 1이면 결과가 첨부 파일로 반환됩니다.|  
|**query_result_header**|**bit**|값이 1이면 쿼리 결과에 열 머리글이 포함됩니다. 값이 0이면 쿼리 결과에 열 머리글이 포함되지 않습니다.|  
|**query_result_width**|**int**|**query_result_width** 메시지의 매개 변수입니다.|  
|**query_result_separator**|**char(1)**|쿼리 출력에서 열을 구분하는 데 사용되는 문자입니다.|  
|**exclude_query_output**|**bit**|**exclude_query_output** 메시지의 매개 변수입니다. 자세한 내용은 참조 [sp_send_dbmail &#40; Transact SQL &#41; ](../../relational-databases/system-stored-procedures/sp-send-dbmail-transact-sql.md).|  
|**append_query_error**|**bit**|**append_query_error** 메시지의 매개 변수입니다. 0은 쿼리에 오류가 있을 때 데이터베이스 메일이 전자 메일 메시지를 보내지 않음을 나타냅니다.|  
|**send_request_date**|**datetime**|메시지가 메일 큐에 추가된 날짜와 시간입니다.|  
|**send_request_user**|**sysname**|메시지를 보낸 사용자입니다. 메시지의 보낸 사람: 필드가 아니라 데이터베이스 메일 프로시저의 사용자 컨텍스트입니다.|  
|**sent_account_id**|**int**|메시지를 보내는 데 사용되는 데이터베이스 메일 계정의 식별자입니다. 이 뷰의 경우 항상 NULL입니다.|  
|**sent_status**|**varchar(8)**|메일의 상태입니다. 항상 **실패** 이 보기에 대 한 합니다.|  
|**sent_date**|**datetime**|메시지가 메일 큐에서 제거된 추가된 날짜와 시간입니다.|  
|**last_mod_date**|**datetime**|행을 마지막으로 수정한 날짜와 시간입니다.|  
|**last_mod_user**|**sysname**|행을 마지막으로 수정한 사용자입니다.|  
  
## <a name="remarks"></a>주의  
 사용 하 여는 **sysmail_faileditems** 을 데이터베이스 메일에서 보내지 않은 메시지를 보려면 보기. 데이터베이스 메일 문제를 해결할 때 이 뷰를 통해 보내지 못한 메시지의 속성을 보면 문제의 근원을 확인하는 데 도움이 될 수 있습니다. 실패 한 이유를 보려면 실패 한 메시지에 대 한 항목을 참조는 [sysmail_event_log &#40; Transact SQL &#41; ](../../relational-databases/system-catalog-views/sysmail-event-log-transact-sql.md) 보기.  
  
## <a name="permissions"></a>Permissions  
 에 부여 된 **sysadmin** 고정된 서버 역할 및 **databasemailuserrole** 데이터베이스 역할입니다. 멤버에 의해 실행 된 **sysadmin** 고정 서버 역할,이 보기 실패 한 모든 메시지를 표시 합니다. 다른 모든 사용자는 자신이 제출한 메시지 중 실패한 메시지만 볼 수 있습니다.  
  
  