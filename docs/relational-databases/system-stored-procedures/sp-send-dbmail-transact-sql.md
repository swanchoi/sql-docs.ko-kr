---
title: sp_send_dbmail (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 08/10/2016
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
- sendmail_sp_TSQL
- sendmail_sp
- SP_SEND_DBMAIL_TSQL
dev_langs: TSQL
helpviewer_keywords: sp_send_dbmail
ms.assetid: f1d7a795-a3fd-4043-ac4b-c781e76dab47
caps.latest.revision: "72"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Active
ms.openlocfilehash: 4001c0260cdd6f9f2f0b43db07445dcb77fb6c5d
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="spsenddbmail-transact-sql"></a>sp_send_dbmail(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  지정된 수신자에게 전자 메일 메시지를 보냅니다. 이 메시지에는 쿼리 결과 집합, 첨부 파일 등이 포함될 수 있습니다. 메일 데이터베이스 메일 큐에 성공적으로 배치 된 경우 **sp_send_dbmail** 반환는 **mailitem_id** 메시지입니다. 이 저장된 프로시저에는 **msdb** 데이터베이스입니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_send_dbmail [ [ @profile_name = ] 'profile_name' ]  
    [ , [ @recipients = ] 'recipients [ ; ...n ]' ]  
    [ , [ @copy_recipients = ] 'copy_recipient [ ; ...n ]' ]  
    [ , [ @blind_copy_recipients = ] 'blind_copy_recipient [ ; ...n ]' ]  
    [ , [ @from_address = ] 'from_address' ]  
    [ , [ @reply_to = ] 'reply_to' ]   
    [ , [ @subject = ] 'subject' ]   
    [ , [ @body = ] 'body' ]   
    [ , [ @body_format = ] 'body_format' ]  
    [ , [ @importance = ] 'importance' ]  
    [ , [ @sensitivity = ] 'sensitivity' ]  
    [ , [ @file_attachments = ] 'attachment [ ; ...n ]' ]  
    [ , [ @query = ] 'query' ]  
    [ , [ @execute_query_database = ] 'execute_query_database' ]  
    [ , [ @attach_query_result_as_file = ] attach_query_result_as_file ]  
    [ , [ @query_attachment_filename = ] query_attachment_filename ]  
    [ , [ @query_result_header = ] query_result_header ]  
    [ , [ @query_result_width = ] query_result_width ]  
    [ , [ @query_result_separator = ] 'query_result_separator' ]  
    [ , [ @exclude_query_output = ] exclude_query_output ]  
    [ , [ @append_query_error = ] append_query_error ]  
    [ , [ @query_no_truncate = ] query_no_truncate ]   
    [ , [ @query_result_no_padding = ] @query_result_no_padding ]   
    [ , [ @mailitem_id = ] mailitem_id ] [ OUTPUT ]  
```  
  
## <a name="arguments"></a>인수  
 [  **@profile_name=** ] **'***profile_name***'**  
 메시지를 보내는 프로필의 이름입니다. *profile_name* 유형의 **sysname**, 기본값은 NULL입니다. *profile_name* 기존 데이터베이스 메일 프로필의 이름 이어야 합니다. No *profile_name* 지정 된 **sp_send_dbmail** 현재 사용자에 대 한 기본 개인 프로필을 사용 합니다. 사용자에 기본 개인 프로필이 없는 경우 **sp_send_dbmail** 에 대 한 기본 공개 프로필을 사용 하 여는 **msdb** 데이터베이스입니다. 사용자에 기본 개인 프로필이 없고 데이터베이스에 대 한 기본 공개 프로필이 있으면  **@profile_name**  지정 해야 합니다.  
  
 [  **@recipients=** ] **'***받는 사람에 게***'**  
 메시지를 받을 전자 메일 주소 목록으로, 각 주소는 세미콜론으로 구분되어 있습니다. 받는 사람 목록에 유형임 **varchar (max)**합니다. 이 매개 변수는 선택 사항 중 하나 이상을  **@recipients** ,  **@copy_recipients** , 또는  **@blind_copy_recipients**  지정 해야 합니다 또는 **sp_ send_dbmail** 에서 오류를 반환 합니다.  
  
 [  **@copy_recipients=** ] **'***copy_recipients***'**  
 참조로 메시지를 받을 전자 메일 주소 목록으로, 각 주소는 세미콜론으로 구분되어 있습니다. 복사 받는 사람 목록에 유형임 **varchar (max)**합니다. 이 매개 변수는 선택 사항 중 하나 이상을  **@recipients** ,  **@copy_recipients** , 또는  **@blind_copy_recipients**  지정 해야 합니다 또는 **sp_ send_dbmail** 에서 오류를 반환 합니다.  
  
 [  **@blind_copy_recipients=** ] **'***blind_copy_recipients***'**  
 숨은 참조로 메시지를 받을 전자 메일 주소 목록으로, 각 주소는 세미콜론으로 구분되어 있습니다. 숨은 받는 사람 목록에 유형임 **varchar (max)**합니다. 이 매개 변수는 선택 사항 중 하나 이상을  **@recipients** ,  **@copy_recipients** , 또는  **@blind_copy_recipients**  지정 해야 합니다 또는 **sp_ send_dbmail** 에서 오류를 반환 합니다.  
  
 [  **@from_address=** ] **'***from_address***'**  
 전자 메일 메시지의 '보낸 사람 주소' 값입니다. 이것은 메일 프로필의 설정을 재정의하는 데 사용되는 선택적 매개 변수입니다. 이 매개 변수는 형식 **varchar (max)**합니다. SMTP 보안 설정에 따라 재정의 허용 여부가 결정됩니다. 매개 변수를 지정하지 않으면 기본값은 NULL입니다.  
  
 [  **@reply_to=** ] **'***reply_to***'**  
 전자 메일 메시지의 '회신 주소' 값입니다. 전자 메일 주소만 유효한 값으로 허용됩니다. 이것은 메일 프로필의 설정을 재정의하는 데 사용되는 선택적 매개 변수입니다. 이 매개 변수는 형식 **varchar (max)**합니다. SMTP 보안 설정에 따라 재정의 허용 여부가 결정됩니다. 매개 변수를 지정하지 않으면 기본값은 NULL입니다.  
  
 [  **@subject=** ] **'***주체***'**  
 전자 메일 메시지의 제목입니다. 제목은 형식의 **nvarchar (255)**합니다. 제목을 지정하지 않으면 기본값은 'SQL Server Message'입니다.  
  
 [  **@body=** ] **'***본문***'**  
 전자 메일 메시지의 본문입니다. 메시지 본문은 형식의 **nvarchar (max)**, 기본값은 NULL입니다.  
  
 [  **@body_format=** ] **'***body_format***'**  
 메시지 본문의 형식입니다. 이 매개 변수는 형식 **varchar (20)**, 기본값은 NULL입니다. 이 매개 변수를 지정할 경우 나가는 메시지의 헤더가 보내져 메시지 본문이 지정된 형식임을 나타냅니다. 매개 변수에 포함할 수 있는 값은 다음과 같습니다.  
  
-   TEXT  
  
-   HTML  
  
 기본값은 TEXT입니다.  
  
 [  **@importance=** ] **'***중요도***'**  
 메시지의 중요도입니다. 이 매개 변수는 형식 **varchar(6)**합니다. 매개 변수에 포함할 수 있는 값은 다음과 같습니다.  
  
-   낮음  
  
-   보통  
  
-   높음  
  
 기본값은 Normal입니다.  
  
 [  **@sensitivity=** ] **'***민감도***'**  
 메시지의 기밀성입니다. 이 매개 변수는 형식 **varchar(12)**합니다. 매개 변수에 포함할 수 있는 값은 다음과 같습니다.  
  
-   보통  
  
-   Personal  
  
-   Private  
  
-   Confidential  
  
 기본값은 Normal입니다.  
  
 [  **@file_attachments=** ] **'***file_attachments***'**  
 전자 메일 메시지에 첨부되는 파일 이름 목록으로, 각 파일 이름은 세미콜론으로 구분되어 있습니다. 목록의 파일은 절대 경로로 지정해야 합니다. 첨부 파일 목록은 유형 **nvarchar (max)**합니다. 기본적으로 데이터베이스 메일의 첨부 파일은 파일당 1MB로 제한됩니다.  
  
 [  **@query=** ] **'***쿼리***'**  
 실행할 쿼리입니다. 쿼리 결과를 파일로 첨부할 수도 있고 전자 메일 메시지의 본문에 포함할 수도 있습니다. 유형의 쿼리는 **nvarchar (max)**, 유효한 포함 될 수 있습니다 및 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문을 합니다. 스크립트 호출에서 하므로 지역 변수는 별도 세션에서 쿼리가 실행 되는 참고 **sp_send_dbmail** 는 쿼리에 사용할 수 없습니다.  
  
 [  **@execute_query_database=** ] **'***execute_query_database***'**  
 저장 프로시저가 쿼리를 실행하는 데이터베이스 컨텍스트입니다. 이 매개 변수는 형식 **sysname**, 현재 데이터베이스의 기본값입니다. 이 매개 변수는 해당 하는 경우  **@query**  지정 됩니다.  
  
 [  **@attach_query_result_as_file=** ] *attach_query_result_as_file*  
 쿼리의 결과 집합이 첨부 파일로 반환되는지 여부를 지정합니다. *attach_query_result_as_file* 유형의 **비트**, 기본값은 0입니다.  
  
 쿼리 결과의 내용을 후 전자 메일 메시지의 본문에 포함 된 값이 0 이면는  **@body**  매개 변수입니다. 값이 1이면 결과가 첨부 파일로 반환됩니다. 이 매개 변수는 해당 하는 경우  **@query**  지정 됩니다.  
  
 [  **@query_attachment_filename=** ] *query_attachment_filename*  
 쿼리 결과 집합 첨부 파일에 사용할 파일 이름을 지정합니다. *query_attachment_filename* 유형의 **nvarchar (255)**, 기본값은 NULL입니다. 이 매개 변수는 무시 됩니다 때 *attach_query_result* 은 0입니다. 때 *attach_query_result* 는 1이 고이 매개 변수가 NULL 이면 데이터베이스 메일에서 임의로 파일 이름을 만듭니다.  
  
 [  **@query_result_header=** ] *query_result_header*  
 쿼리 결과에 열 머리글을 포함할 것인지 여부를 지정합니다. Query_result_header 값은 형식이 **비트**합니다. 값이 1이면 쿼리 결과에 열 머리글이 포함됩니다. 값이 0이면 쿼리 결과에 열 머리글이 포함되지 않습니다. 이 매개 변수의 기본값은 **1**합니다. 이 매개 변수는 해당 하는 경우  **@query**  지정 됩니다.  
  
 [  **@query_result_width**  =] *query_result_width*  
 쿼리 결과에 서식을 지정할 때 사용하는 문자 줄 너비입니다. *query_result_width* 유형의 **int**, 기본값은 256입니다. 10과 32767 사이의 값을 지정해야 합니다. 이 매개 변수는 해당 하는 경우  **@query**  지정 됩니다.  
  
 [  **@query_result_separator=** ] **'***query_result_separator***'**  
 쿼리 출력에서 열을 구분하는 데 사용되는 문자입니다. 구분 기호는 형식의 **char(1)**합니다. 기본값은 ' '(공백)입니다.  
  
 [  **@exclude_query_output=** ] *exclude_query_output*  
 쿼리 실행 출력을 전자 메일 메시지로 반환할지 여부를 지정합니다. **exclude_query_output** 는 bit 이며 기본값은 0입니다. 경우이 매개 변수는 0, 실행의는 **sp_send_dbmail** 저장된 프로시저는 콘솔에는 쿼리 실행의 결과로 반환 되는 메시지를 인쇄 합니다. 이 매개 변수는 1, 실행 하는 경우는 **sp_send_dbmail** 저장된 프로시저를 인쇄 하지 않을 쿼리 실행 메시지가 콘솔에 있습니다.  
  
 [  **@append_query_error=** ] *append_query_error*  
 에 지정 된 쿼리에서 오류가 반환 될 때 전자 메일을 보낼지 여부를 지정 된  **@query**  인수입니다. **append_query_error** 은 **비트**, 기본값은 0입니다. 이 매개 변수가 1이면 데이터베이스 메일에서 전자 메일 메시지의 본문에 쿼리 오류 메시지를 포함하여 전자 메일 메시지를 보냅니다. 전자 메일 메시지를 데이터베이스 메일에 보내지 않으면이 매개 변수가 0 이면 및 **sp_send_dbmail** 실패를 나타내는 반환 코드 1로 끝납니다.  
  
 [  **@query_no_truncate=** ] *query_no_truncate*  
 큰 가변 길이 데이터 형식의 잘림을 방지 하는 옵션을 사용 하 여 쿼리를 실행할 것인지를 지정 합니다 (**varchar (max)**, **nvarchar (max)**, **varbinary (max)** **xml**, **텍스트**, **ntext**, **이미지**, 및 사용자 정의 데이터 형식). 설정된 경우 쿼리 결과에 열 머리글이 포함되지 않습니다. *query_no_truncate* 값은 형식이 **비트**합니다. 값이 0이거나 지정되지 않은 경우에는 쿼리의 열이 256자로 잘립니다. 값이 1이면 쿼리의 열이 잘리지 않습니다. 이 매개 변수의 기본값은 0입니다.  
  
> [!NOTE]  
>  많은 양의 데이터와 함께 사용할 때의 @**query_no_truncate** 옵션 추가 리소스가 소비 하 고 서버 성능이 저하 될 수 있습니다.  
  
 [ **@query_result_no_padding** ] *@query_result_no_padding*  
 형식은 bit이고, 기본값은 0입니다. 1로 설정 하면 쿼리 결과이 패딩 되지 않으면 파일 크기를 줄일 수 있습니다. 설정 하는 경우 @query_result_no_padding 1로 설정 된 @query_result_width 매개 변수를는 @query_result_no_padding 매개 변수를 덮어씁니다는 @query_result_width 매개 변수입니다.  
  
 이 경우 오류는 발생하지 않습니다.  
  
 설정 하는 경우는 @query_result_no_padding 1로 설정 된 @query_no_truncate 매개 변수를 오류가 발생 합니다.  
  
 [  **@mailitem_id=** ] *mailitem_id* [출력]  
 선택적 출력 매개 변수는 반환 된 *mailitem_id* 메시지의 합니다. *mailitem_id* 유형의 **int**합니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 반환 코드 0은 성공을 의미합니다. 다른 값은 실패를 의미합니다. 실패 한 문에 대 한 오류 코드에 저장 되는 @@ERROR 변수입니다.  
  
## <a name="result-sets"></a>결과 집합  
 성공 시 "Mail queued" 메시지를 반환합니다.  
  
## <a name="remarks"></a>주의  
 사용 하기 전에 데이터베이스 메일을 설정 해야 데이터베이스 메일 구성 마법사를 사용 하 여 또는 **sp_configure**합니다.  
  
 **sysmail_stop_sp** 외부 프로그램이 사용 하는 Service Broker 개체를 중지 하 여 데이터베이스 메일을 중지 합니다. **sp_send_dbmail** 여전히 사용 하 여 데이터베이스 메일이 중지 되 면 메일을 받습니다 **sysmail_stop_sp**합니다. 데이터베이스 메일을 시작 하려면 사용 **sysmail_start_sp**합니다.  
  
 때  **@profile**  를 지정 하지 않으면 **sp_send_dbmail** 기본 프로필을 사용 합니다. 전자 메일 메시지를 보내는 사용자에게 기본 개인 프로필이 있을 경우 이 프로필이 사용됩니다. 사용자에 게 기본 개인 프로필이 없을 경우 **sp_send_dbmail** 기본 공개 프로필을 사용 합니다. 사용자에 대 한 기본 개인 프로필이 없 및 기본 공개 프로필이 없을 경우 **sp_send_dbmail** 에서 오류를 반환 합니다.  
  
 **sp_send_dbmail** 콘텐츠가 없는 전자 메일 메시지를 지원 하지 않습니다. 전자 메일 메시지를 보내려면 중 하나 이상을 지정 해야 하면  **@body** ,  **@query** ,  **@file_attachments** , 또는  **@subject** . 그렇지 않으면 **sp_send_dbmail** 에서 오류를 반환 합니다.  
  
 데이터베이스 메일에서는 현재 사용자의 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 보안 컨텍스트를 사용하여 파일에 대한 액세스를 제어합니다. 따라서 사용자에 게 인증 된 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인증 사용 하 여 파일을 첨부할 수 없습니다  **@file_attachments** 합니다. Windows에서는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]를 사용하여 원격 컴퓨터에서 다른 원격 컴퓨터로 자격 증명을 제공할 수 없습니다. 그러므로 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]를 실행하는 컴퓨터가 아닌 컴퓨터에서 명령을 실행할 경우 데이터베이스 메일은 네트워크 공유 위치에서 파일을 첨부할 수 없습니다.  
  
 두  **@query**  및  **@file_attachments**  지정 된 파일을 찾을 수 없습니다 및 쿼리가 여전히 실행 되지만 전자 메일이 전송 되지 않습니다.  
  
 쿼리를 지정한 경우 결과 집합의 서식은 인라인 텍스트로 지정됩니다. 결과 내 이진 데이터는 16진수 형식으로 전송됩니다.  
  
 매개 변수  **@recipients** ,  **@copy_recipients** , 및  **@blind_copy_recipients**  전자 메일 주소의 세미콜론으로 구분 된 목록입니다. 이러한 매개 변수 중 하나 이상을 지정 해야 합니다 또는 **sp_send_dbmail** 에서 오류를 반환 합니다.  
  
 실행할 때 **sp_send_dbmail** 트랜잭션 컨텍스트 없이 데이터베이스 메일을 시작 하 고 암시적 트랜잭션을 커밋하고 있습니다. 실행할 때 **sp_send_dbmail** 에서 기존 트랜잭션 내에서 데이터베이스 메일은 사용자 커밋 또는 모든 변경 내용이 롤백됩니다. 내부 트랜잭션은 시작되지 않습니다.  
  
## <a name="permissions"></a>Permissions  
 실행 권한은 **sp_send_dbmail** 의 모든 멤버에 대 한 기본은 **수** 데이터베이스 역할에는 **msdb** 데이터베이스입니다. 그러나 메시지를 보내는 사용자에 게 없을 경우 요청에 대 한 프로필을 사용할 수 있는 권한을 **sp_send_dbmail** 에서 오류를 반환 하 고 메시지를 보내지 않습니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-sending-an-e-mail-message"></a>1. 전자 메일 메시지 보내기  
 이 예제에서는 전자 메일 주소를 사용 하 여 상대방에 게 전자 메일 메시지를 보냅니다 `myfriend@Adventure-Works.com`합니다. 메시지의 제목은 `Automated Success Message`입니다. 메시지의 본문에는 `'The stored procedure finished successfully'`라는 문장이 포함되어 있습니다.  
  
```  
EXEC msdb.dbo.sp_send_dbmail  
    @profile_name = 'Adventure Works Administrator',  
    @recipients = 'yourfriend@Adventure-Works.com',  
    @body = 'The stored procedure finished successfully.',  
    @subject = 'Automated Success Message' ;  
```  
  
### <a name="b-sending-an-e-mail-message-with-the-results-of-a-query"></a>2. 쿼리 결과를 포함하여 전자 메일 메시지 보내기  
 이 예제에서는 전자 메일 주소를 사용 하 여 상대방에 게 전자 메일 메시지를 보냅니다 `yourfriend@Adventure-Works.com`합니다. 메시지의 제목은 `Work Order Count`이며 이 메시지는 `DueDate`가 2004년 4월 30일부터 2일 내인 작업 주문 번호를 보여 주는 쿼리를 실행합니다. 데이터베이스 메일은 결과를 텍스트 파일로 첨부합니다.  
  
```  
EXEC msdb.dbo.sp_send_dbmail  
    @profile_name = 'Adventure Works Administrator',  
    @recipients = 'yourfriend@Adventure-Works.com',  
    @query = 'SELECT COUNT(*) FROM AdventureWorks2012.Production.WorkOrder  
                  WHERE DueDate > ''2004-04-30''  
                  AND  DATEDIFF(dd, ''2004-04-30'', DueDate) < 2' ,  
    @subject = 'Work Order Count',  
    @attach_query_result_as_file = 1 ;  
```  
  
### <a name="c-sending-an-html-e-mail-message"></a>3. HTML 전자 메일 메시지 보내기  
 이 예제에서는 전자 메일 주소를 사용 하 여 상대방에 게 전자 메일 메시지를 보냅니다 `yourfriend@Adventure-Works.com`합니다. 메시지의 제목은 `Work Order List`이며 이 메시지에는 `DueDate`가 2004년 4월 30일부터 2일 내인 작업 주문을 보여 주는 HTML 문서가 포함되어 있습니다. 데이터베이스 메일은 메시지를 HTML 형식으로 보냅니다.  
  
```  
DECLARE @tableHTML  NVARCHAR(MAX) ;  
  
SET @tableHTML =  
    N'<H1>Work Order Report</H1>' +  
    N'<table border="1">' +  
    N'<tr><th>Work Order ID</th><th>Product ID</th>' +  
    N'<th>Name</th><th>Order Qty</th><th>Due Date</th>' +  
    N'<th>Expected Revenue</th></tr>' +  
    CAST ( ( SELECT td = wo.WorkOrderID,       '',  
                    td = p.ProductID, '',  
                    td = p.Name, '',  
                    td = wo.OrderQty, '',  
                    td = wo.DueDate, '',  
                    td = (p.ListPrice - p.StandardCost) * wo.OrderQty  
              FROM AdventureWorks.Production.WorkOrder as wo  
              JOIN AdventureWorks.Production.Product AS p  
              ON wo.ProductID = p.ProductID  
              WHERE DueDate > '2004-04-30'  
                AND DATEDIFF(dd, '2004-04-30', DueDate) < 2   
              ORDER BY DueDate ASC,  
                       (p.ListPrice - p.StandardCost) * wo.OrderQty DESC  
              FOR XML PATH('tr'), TYPE   
    ) AS NVARCHAR(MAX) ) +  
    N'</table>' ;  
  
EXEC msdb.dbo.sp_send_dbmail @recipients='yourfriend@Adventure-Works.com',  
    @subject = 'Work Order List',  
    @body = @tableHTML,  
    @body_format = 'HTML' ;  
```  
  
## <a name="see-also"></a>관련 항목:  
 [데이터베이스 메일](../../relational-databases/database-mail/database-mail.md)   
 [데이터베이스 메일 구성 개체](../../relational-databases/database-mail/database-mail-configuration-objects.md)   
 [데이터베이스 메일 저장 프로시저 &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/database-mail-stored-procedures-transact-sql.md)   
 [sp_addrolemember&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addrolemember-transact-sql.md)  
  
  