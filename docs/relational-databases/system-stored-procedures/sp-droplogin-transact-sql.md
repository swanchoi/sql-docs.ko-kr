---
title: sp_droplogin (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
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
- sp_droplogin
- sp_droplogin_TSQL
dev_langs: TSQL
helpviewer_keywords: sp_droplogin
ms.assetid: e58684d1-c394-48de-906e-da6ee91100c3
caps.latest.revision: "16"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: c544ffb9e3093296f38c357b17e68e18607f7634
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2017
---
# <a name="spdroplogin-transact-sql"></a>sp_droplogin(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 로그인을 제거합니다. 이렇게 하면 해당 로그인 이름으로 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스에 액세스하는 것을 방지할 수 있습니다.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]사용 하 여 [DROP LOGIN](../../t-sql/statements/drop-login-transact-sql.md) 대신 합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_droplogin [ @loginame = ] 'login'  
```  
  
## <a name="arguments"></a>인수  
 [  **@loginame =** ] **'***로그인***'**  
 제거할 로그인입니다. *로그인* 은 **sysname**, 기본값은 없습니다. *로그인* 에 이미 있어야 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]합니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 1(실패)  
  
## <a name="remarks"></a>주의  
 **sp_droplogin** DROP LOGIN을 호출 합니다.  
  
 **sp_droplogin** 사용자 정의 트랜잭션 내에서 실행할 수 없습니다.  
  
## <a name="permissions"></a>Permissions  
 서버에 대한 ALTER ANY LOGIN 권한이 필요합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 `DROP LOGIN`을 사용하여 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스에서 `Victoria` 로그인을 제거합니다. 이것은 기본적으로 사용되는 방법입니다.  
  
```  
DROP LOGIN Victoria;  
GO  
```  
  
## <a name="see-also"></a>관련 항목:  
 [보안 저장 프로시저 &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [DROP login&#40; Transact SQL &#41;](../../t-sql/statements/drop-login-transact-sql.md)   
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  