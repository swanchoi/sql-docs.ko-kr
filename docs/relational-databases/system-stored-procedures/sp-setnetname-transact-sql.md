---
title: sp_setnetname (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_setnetname
- sp_setnetname_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_setnetname
ms.assetid: f416ba81-3835-4588-b0a3-2fe75589490e
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 67d07d2ea4bd1656ed8f24458410f5812ed22e70
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47704761"
---
# <a name="spsetnetname-transact-sql"></a>sp_setnetname(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  네트워크 이름 설정 **sys.servers** 의 원격 인스턴스에 대 한 실제 네트워크 컴퓨터 이름으로 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]입니다. 이 프로시저를 사용하여 잘못된 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 식별자를 포함하는 네트워크 이름을 가진 컴퓨터에 원격 저장 프로시저 호출을 실행할 수 있습니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_setnetname  
@server = 'server',   
     @netname = 'network_name'  
```  
  
## <a name="arguments"></a>인수  
 **@server = '** *server* **'**  
 사용자가 코드화한 원격 저장 프로시저 호출 구문에서 참조되는 원격 서버의 이름입니다. 에 정확히 한 행 **sys.servers** 이 사용 하 여 이미 있어야 *server*합니다. *server* 은 **sysname**이며 기본값은 없습니다.  
  
 **@netname ='** *network_name* **'**  
 원격 저장 프로시저 호출이 수행되는 컴퓨터의 네트워크 이름입니다. *network_name* 됩니다 **sysname**, 기본값은 없습니다.  
  
 이 이름은 반드시 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 컴퓨터 이름과 일치해야 하며 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 식별자에 사용할 수 없는 문자를 포함할 수 있습니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 1(실패)  
  
## <a name="result-sets"></a>결과 집합  
 없음  
  
## <a name="remarks"></a>Remarks  
 컴퓨터 이름에 잘못된 식별자가 있는 경우 Windows 컴퓨터에 일부 원격 저장 프로시저를 호출하면 문제가 발생할 수 있습니다.  
  
 연결된 서버와 원격 서버는 같은 네임스페이스에 있으므로 이름이 같으면 안 됩니다. 그러나 정의할 수 있습니다 지정된 된 서버에 대해 원격 서버와 연결된 된 서버 이름을 다르게 지정 하 고 사용 하 여 **sp_setnetname** 둘 중의 네트워크 이름을 기본 서버의 네트워크 이름으로 설정 합니다.  
  
```  
--Assume sqlserv2 is actual name of SQL Server   
--database server  
EXEC sp_addlinkedserver 'sqlserv2';  
GO  
EXEC sp_addserver 'rpcserv2';  
GO  
EXEC sp_setnetname 'rpcserv2', 'sqlserv2';  
```  
  
> [!NOTE]  
>  사용 하 여 **sp_setnetname** 로컬 서버에 연결된 된 서버를 가리키도록 지원 되지 않습니다. 이런 방법으로 참조된 서버는 분산 트랜잭션에 참여할 수 없습니다.  
  
## <a name="permissions"></a>사용 권한  
 멤버 자격이 필요 합니다 **sysadmin** 하 고 **setupadmin** 고정 서버 역할입니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 원격 저장 프로시저 호출을 실행하는 데 사용되는 일반적인 관리 시퀀스를 보여 줍니다.  
  
```  
USE master;  
GO  
EXEC sp_addserver 'Win_1';  
EXEC sp_setnetname 'Win_1','Win-1';  
EXEC Win_1.master.dbo.sp_who;  
```  
  
## <a name="see-also"></a>관련 항목  
 [데이터베이스 엔진 저장 프로시저 &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/database-engine-stored-procedures-transact-sql.md)   
 [sp_addlinkedserver&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql.md)   
 [sp_addserver &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addserver-transact-sql.md)   
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
