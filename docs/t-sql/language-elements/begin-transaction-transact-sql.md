---
title: BEGIN TRANSACTION (TRANSACT-SQL) | Microsoft Docs
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- BEGIN_TRANSACTION_TSQL
- TRANSACTION_TSQL
- TRANSACTION
- BEGIN TRANSACTION
- BEGIN TRAN
- BEGIN_TRAN_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- transaction logs [SQL Server], BEGIN TRANSACTION statement
- marked transactions [SQL Server], BEGIN TRANSACTION statement
- BEGIN TRANSACTION statement
- local transactions [SQL Server]
- marking transactions [SQL Server]
- transactions [SQL Server], starting
- transaction names [SQL Server]
- starting point marked for transactions
- starting transactions
ms.assetid: c6258df4-11f1-416a-816b-54f98c11145e
caps.latest.revision: 56
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: f52f237795de00f4ad78403bed986ac571005c31
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="begin-transaction-transact-sql"></a>BEGIN TRANSACTION(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-asdw-pdw-_md](../../includes/tsql-appliesto-ss2008-asdb-asdw-pdw-md.md)]

  명시적 로컬 트랜잭션의 시작 위치를 표시합니다. 명시적 트랜잭션이 BEGIN TRANSACTION 문으로 시작 하 고 COMMIT 또는 ROLLBACK 문을 사용 하 여 종료 합니다.  

 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
--Applies to SQL Server and Azure SQL Database
 
BEGIN { TRAN | TRANSACTION }   
    [ { transaction_name | @tran_name_variable }  
      [ WITH MARK [ 'description' ] ]  
    ]  
[ ; ]  
```  
 
```  
--Applies to Azure SQL Data Warehouse and Parallel Data Warehouse
 
BEGIN { TRAN | TRANSACTION }   
[ ; ]  
```  

  
## <a name="arguments"></a>인수  
 *transaction_name*  
 **적용 대상:** (2008부터 시작) 하는 SQL Server, Azure SQL 데이터베이스
 
 트랜잭션에 할당된 이름입니다. *transaction_name* 식별자 하지만 32 자를 허용 되지 않습니다 보다 긴 식별자에 대 한 규칙을 따라야 합니다. 중첩된 BEGIN...COMMIT 또는 BEGIN...ROLLBACK 문의 가장 바깥쪽 쌍에서만 트랜잭션 이름을 사용합니다. *transaction_name* 항상 대/소문자 구분, 경우에 인스턴스의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 대/소문자를 무시 합니다.  
  
 @*tran_name_variable*  
 **적용 대상:** (2008부터 시작) 하는 SQL Server, Azure SQL 데이터베이스
 
 유효한 트랜잭션 이름이 포함된 사용자 정의 변수의 이름입니다. 변수를 사용 하 여 선언 해야 합니다는 **char**, **varchar**, **nchar**, 또는 **nvarchar** 데이터 형식입니다. 변수에 32자보다 더 많은 문자가 전달되는 경우 처음 32자만 사용되고 나머지 문자는 잘립니다.  
  
 WITH MARK ['*설명*']  
**적용 대상:** (2008부터 시작) 하는 SQL Server, Azure SQL 데이터베이스

로그에 트랜잭션이 표시되도록 지정합니다. *설명* 표시를 설명 하는 문자열입니다. A *설명* 128 자를 후에 msdb.dbo.logmarkhistory 테이블에 저장 되기 전에 128 자로 잘립니다 보다 더 이상.  
  
 WITH MARK를 사용할 경우 트랜잭션 이름을 반드시 지정해야 합니다. WITH MARK를 사용하면 명명된 표시에 트랜잭션 로그를 복원할 수 있습니다.  
  
## <a name="general-remarks"></a>일반적인 주의 사항
BEGIN TRANSACTION @ 증가@TRANCOUNT 1입니다.
  
BEGIN TRANSACTION은 연결에서 참조하는 데이터가 논리적, 물리적으로 일관성 있는 시점을 나타냅니다. 오류가 발생할 경우 BEGIN TRANSACTION 이후에 발생한 모든 데이터 수정 사항을 롤백하여 데이터를 이러한 일관성 있는 상태로 되돌릴 수 있습니다. 트랜잭션이 오류 없이 완료되고 COMMIT TRANSACTION이 실행되어 수정 사항이 데이터베이스에 영구히 반영되거나, 오류가 발생하여 ROLLBACK TRANSACTION 문이 모든 수정 사항을 지울 때까지 모든 트랜잭션은 지속됩니다.  
  
BEGIN TRANSACTION은 해당 문을 실행한 연결에 대해 로컬 트랜잭션을 시작합니다. 현재 트랜잭션 격리 수준 설정에 따라 해당 연결에서 실행한 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문을 지원하기 위해 획득한 리소스는 트랜잭션이 COMMIT TRANSACTION 또는 ROLLBACK TRANSACTION 문으로 완료될 때까지 잠금 상태가 됩니다. 트랜잭션이 장기간 처리 중이면 다른 사용자가 이러한 잠긴 리소스에 액세스할 수 없고 로그가 잘리지 않을 수도 있습니다.  
  
 BEGIN TRANSACTION은 로컬 트랜잭션을 시작하지만 응용 프로그램에서 INSERT, UPDATE 또는 DELETE 문 실행과 같이 로그에 기록되는 동작을 수행하기 전에는 트랜잭션 로그에 기록되지 않습니다. 응용 프로그램은 SELECT 문의 트랜잭션 격리 수준을 보호하기 위해 잠금을 확보하는 등의 동작을 수행하지만 수정 동작을 수행할 때까지는 로그에 아무것도 기록되지 않습니다.  
  
 일련의 중첩된 트랜잭션에 속한 여러 트랜잭션을 트랜잭션 이름으로 명명하는 것은 트랜잭션에 큰 영향을 주지 않습니다. 가장 바깥쪽의 첫 번째 트랜잭션 이름만 시스템에 등록됩니다. 유효한 저장점 이름이 아닌 다른 이름으로 롤백하면 오류가 발생합니다. 롤백 이전에 실행된 문은 오류 발생 시 실제로 롤백되지 않고 외부 트랜잭션이 롤백될 경우에만 롤백됩니다.  
  
 문을 커밋하거나 롤백하기 전에 다음 동작을 수행하면 BEGIN TRANSACTION 문에 의해 시작된 로컬 트랜잭션이 분산 트랜잭션으로 에스컬레이션됩니다.  
  
-   연결된 서버에서 원격 테이블을 참조하는 INSERT, DELETE 또는 UPDATE 문을 실행합니다. 연결 된 서버에 액세스 하는 데 사용 되는 OLE DB 공급자 ITransactionJoin 인터페이스를 지원 하지 않는 INSERT, UPDATE 또는 DELETE 문이 실패 합니다.  
  
-   REMOTE_PROC_TRANSACTIONS 옵션이 ON으로 설정된 경우 원격 저장 프로시저를 호출합니다.  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]의 로컬 복사본은 트랜잭션 컨트롤러가 되고 MS DTC([!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator)를 사용하여 분산 트랜잭션을 관리합니다.  
  
 BEGIN DISTRIBUTED TRANSACTION을 사용하여 트랜잭션을 분산 트랜잭션으로 명시적으로 실행할 수 있습니다. 자세한 내용은 참조 [BEGIN DISTRIBUTED TRANSACTION &#40; Transact SQL &#41; ](../../t-sql/language-elements/begin-distributed-transaction-transact-sql.md).  
  
 SET IMPLICIT_TRANSACTIONS가 ON인 경우 BEGIN TRANSACTION 문을 실행하면 두 개의 중첩 트랜잭션이 만들어집니다. 자세한 내용은 참조 하십시오 [SET implicit_transactions&#40; Transact SQL &#41;](../../t-sql/statements/set-implicit-transactions-transact-sql.md)  
  
## <a name="marked-transactions"></a>표시된 트랜잭션  
 WITH MARK 옵션을 사용하면 트랜잭션 이름이 트랜잭션 로그에 저장됩니다. 데이터베이스를 이전 상태로 복원할 때 날짜와 시간 대신 표시된 트랜잭션을 사용할 수 있습니다. 자세한 내용은 참조 [관련 데이터베이스를 일관 되 복구 &#40;에 표시 된 트랜잭션을 사용 하 여 전체 복구 모델 &#41; ](../../relational-databases/backup-restore/use-marked-transactions-to-recover-related-databases-consistently.md) 및 [복원 &#40; Transact SQL &#41; ](../../t-sql/statements/restore-statements-transact-sql.md).  
  
 또한 트랜잭션은 로그 표시는 관련 데이터베이스 집합을 논리적으로 일관성 있는 상태로 복구해야 하는 경우에 필요합니다. 표시는 분산 데이터베이스에 의해 관련 데이터베이스의 트랜잭션 로그에 저장될 수 있습니다. 이러한 표시에 관련 데이터베이스 집합을 복구하는 경우 트랜잭션이 일관된 데이터베이스 집합이 만들어집니다. 관련 데이터베이스에서 표시의 위치를 정하는 데는 특별한 절차가 필요합니다.  
  
 데이터베이스가 표시된 트랜잭션에 의해 업데이트되는 경우에만 표시가 트랜잭션 로그에 저장됩니다. 데이터를 수정하지 않는 트랜잭션은 표시되지 않습니다.  
  
 BEGIN TRAN *new_name* WITH MARK 표시 되지 않은 기존 트랜잭션 내에서 중첩 될 수 있습니다. 그럴 *new_name* 트랜잭션이 지정할 이미 있습니다. 이름에도 불구 하 고 트랜잭션의 표시 이름이 됩니다. 다음 예에서 표시의 이름은 `M2`입니다.  
  
```  
BEGIN TRAN T1;  
UPDATE table1 ...;  
BEGIN TRAN M2 WITH MARK;  
UPDATE table2 ...;  
SELECT * from table1;  
COMMIT TRAN M2;  
UPDATE table3 ...;  
COMMIT TRAN T1;  
```  
  
 트랜잭션을 중첩할 때 이미 표시된 트랜잭션을 표시하려고 하면 오류 메시지가 아닌 경고 메시지가 표시됩니다.  
  
 "BEGIN TRAN T1 WITH MARK ...;"  
  
 "UPDATE table1 ...;"  
  
 "BEGIN TRAN M2 WITH MARK ...;"  
  
 "서버: 메시지 3920, 수준 16, 상태 1, 줄 3"  
  
 "WITH MARK 옵션은 첫 번째 BEGIN TRAN WITH MARK 문에만 적용되므로  
  
 무시됩니다."  
  
## <a name="permissions"></a>Permissions  
 public 역할의 멤버 자격이 필요합니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-using-an-explicit-transaction"></a>1. 명시적 트랜잭션을 사용 하 여
**적용 대상:** (2008부터 시작) 하는 SQL Server, Azure SQL 데이터베이스, Azure SQL 데이터 웨어하우스, 병렬 데이터 웨어하우스

이 예제에서는 AdventureWorks를 사용 합니다. 

```
BEGIN TRANSACTION;  
DELETE FROM HumanResources.JobCandidate  
    WHERE JobCandidateID = 13;  
COMMIT;  
```

### <a name="b-rolling-back-a-transaction"></a>2. 트랜잭션 롤백
**적용 대상:** (2008부터 시작) 하는 SQL Server, Azure SQL 데이터베이스, Azure SQL 데이터 웨어하우스, 병렬 데이터 웨어하우스

다음 예제에서는 트랜잭션을 롤백하면 결과 보여 줍니다. 이 예제에서는 ROLLBACK 문을 롤백합니다 INSERT 문이 되지만 만든된 테이블은 계속 존재 합니다.

```
 
CREATE TABLE ValueTable (id int);  
BEGIN TRANSACTION;  
       INSERT INTO ValueTable VALUES(1);  
       INSERT INTO ValueTable VALUES(2);  
ROLLBACK;  

```

### <a name="c-naming-a-transaction"></a>3. 트랜잭션 이름 지정 
**적용 대상:** (2008부터 시작) 하는 SQL Server, Azure SQL 데이터베이스

다음 예에서는 트랜잭션의 이름을 지정하는 방법을 보여 줍니다.  
  
```  
DECLARE @TranName VARCHAR(20);  
SELECT @TranName = 'MyTransaction';  
  
BEGIN TRANSACTION @TranName;  
USE AdventureWorks2012;  
DELETE FROM AdventureWorks2012.HumanResources.JobCandidate  
    WHERE JobCandidateID = 13;  
  
COMMIT TRANSACTION @TranName;  
GO  
```  
  
### <a name="d-marking-a-transaction"></a>4. 트랜잭션 표시  
**적용 대상:** (2008부터 시작) 하는 SQL Server, Azure SQL 데이터베이스

다음 예에서는 트랜잭션을 표시하는 방법을 보여 줍니다. `CandidateDelete` 트랜잭션이 표시됩니다.  
  
```  
BEGIN TRANSACTION CandidateDelete  
    WITH MARK N'Deleting a Job Candidate';  
GO  
USE AdventureWorks2012;  
GO  
DELETE FROM AdventureWorks2012.HumanResources.JobCandidate  
    WHERE JobCandidateID = 13;  
GO  
COMMIT TRANSACTION CandidateDelete;  
GO  
```  
  
## <a name="see-also"></a>관련 항목:  
 [BEGIN DISTRIBUTED TRANSACTION&#40;Transact-SQL&#41;](../../t-sql/language-elements/begin-distributed-transaction-transact-sql.md)   
 [COMMIT TRANSACTION&#40;Transact-SQL&#41;](../../t-sql/language-elements/commit-transaction-transact-sql.md)   
 [커밋 작업 &#40; Transact SQL &#41;](../../t-sql/language-elements/commit-work-transact-sql.md)   
 [ROLLBACK TRANSACTION&#40;Transact-SQL&#41;](../../t-sql/language-elements/rollback-transaction-transact-sql.md)   
 [ROLLBACK WORK &#40; Transact SQL &#41;](../../t-sql/language-elements/rollback-work-transact-sql.md)   
 [SAVE TRANSACTION&#40;Transact-SQL&#41;](../../t-sql/language-elements/save-transaction-transact-sql.md)  
  
  
