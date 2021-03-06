---
title: Transact-SQL을 사용하여 FILESTREAM 데이터 액세스 | Microsoft 문서
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], Transact-SQL
ms.assetid: a6bf0ce7-7e5e-4a07-8917-ee526c9d0a05
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 88fe39b5be43082ffc9648814eccf5384585f2b2
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48061043"
---
# <a name="access-filestream-data-with-transact-sql"></a>Transact-SQL을 사용하여 FILESTREAM 데이터 액세스
  이 항목에서는 [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT, UPDATE 및 DELETE 문을 사용하여 FILESTREAM 데이터를 관리하는 방법에 대해 설명합니다.  
  
> [!NOTE]  
>  이 항목의 예에서는 [FILESTREAM 사용 데이터베이스 만들기](create-a-filestream-enabled-database.md) 및 [FILESTREAM 데이터 저장용 테이블 만들기](create-a-table-for-storing-filestream-data.md)에서 만든 FILESTREAM 사용 데이터베이스 및 테이블이 필요합니다.  
  
##  <a name="ins"></a> FILESTREAM 데이터가 들어 있는 행 삽입  
 FILESTREAM 데이터를 지원하는 테이블에 행을 추가하려면 [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT 문을 사용합니다. FILESTREAM 열에 데이터를 삽입할 때 NULL을 삽입할 수 있습니다 또는 `varbinary(max)` 값입니다.  
  
### <a name="inserting-null"></a>NULL 삽입  
 다음 예에서는 `NULL`을 삽입하는 방법을 보여 줍니다. FILESTREAM 값이 `NULL`이면 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 이 파일 시스템에 파일을 만들지 않습니다.  
  
 [!code-sql[FILESTREAM#FS_InsertNULL](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertnull)]  
  
### <a name="inserting-a-zero-length-record"></a>길이가 0인 레코드 삽입  
 다음 예에서는 `INSERT` 를 사용하여 길이가 0인 레코드를 만드는 방법을 보여 줍니다. 길이가 0인 레코드는 파일 핸들을 가져와야 하지만 Win32 API를 사용하여 파일을 조작하는 경우에 유용합니다.  
  
 [!code-sql[FILESTREAM#FS_InsertZero](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertzero)]  
  
### <a name="creating-a-data-file"></a>데이터 파일 만들기  
 다음 예에서는 `INSERT` 를 사용하여 데이터가 들어 있는 파일을 만드는 방법을 보여 줍니다. [!INCLUDE[ssDE](../../includes/ssde-md.md)] 은 문자열 `Seismic Data` 를 `varbinary(max)` 값으로 변환합니다. FILESTREAM은 Windows 파일이 아직 없는 경우 이를 만든 다음 데이터를 데이터 파일에 추가합니다.  
  
 [!code-sql[FILESTREAM#FS_InsertData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertdata)]  
  
 `Archive``dbo.Records` 테이블의 데이터를 모두 선택하면 결과가 다음 표와 유사하지만 `Id` 열에는 다른 GUID가 포함됩니다.  
  
|Id|SerialNumber|재개|  
|--------|------------------|------------|  
|`C871B90F-D25E-47B3-A560-7CC0CA405DAC`|`1`|`NULL`|  
|`F8F5C314-0559-4927-8FA9-1535EE0BDF50`|`2`|`0x`|  
|`7F680840-B7A4-45D4-8CD5-527C44D35B3F`|`3`|`0x536569736D69632044617461`|  
  
##  <a name="upd"></a> FILESTREAM 데이터 업데이트  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] 을 사용하여 파일 시스템 파일의 데이터를 업데이트할 수 있지만 많은 양의 데이터를 파일로 스트리밍해야 하는 경우에는 이렇게 하지 않는 것이 좋습니다.  
  
 다음 예에서는 파일 레코드에 있는 임의의 텍스트를 `Xray 1`로 바꿉니다.  
  
 [!code-sql[FILESTREAM#FS_UpdateData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_updatedata)]  
  
##  <a name="del"></a> FILESTREAM 데이터 삭제  
 FILESTREAM 필드가 들어 있는 행을 삭제하면 해당 내부 파일 시스템 파일도 삭제됩니다. 행과 그 안에 들어 있는 파일을 삭제하는 유일한 방법은 [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE 문을 사용하는 것입니다.  
  
 다음 예에서는 행과 관련 파일 시스템 파일을 삭제하는 방법을 보여 줍니다.  
  
 [!code-sql[FILESTREAM#FS_DeleteData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_deletedata)]  
  
 `dbo.Archive` 테이블의 데이터를 모두 선택하면 해당 행이 삭제되고 관련 파일도 더 이상 사용할 수 없게 됩니다.  
  
> [!NOTE]  
>  기본 파일은 FILESTREAM 가비지 수집기를 통해 제거됩니다.  
  
## <a name="see-also"></a>관련 항목  
 [FILESTREAM 사용 및 구성](enable-and-configure-filestream.md)   
 [FILESTREAM 응용 프로그램에서 데이터베이스 작업과의 충돌 방지](avoid-conflicts-with-database-operations-in-filestream-applications.md)  
  
  
