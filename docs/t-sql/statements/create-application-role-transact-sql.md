---
title: "응용 프로그램 역할 (Transact SQL) 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- APPLICATION_ROLE_TSQL
- CREATE APPLICATION ROLE
- sql13.swb.applicationrole.permissions.f1
- APPLICATION
- APPLICATION ROLE
- CREATE_APPLICATION_ROLE_TSQL
- APPLICATION_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- CREATE APPLICATION ROLE statement
- application roles [SQL Server], creating
ms.assetid: 647386da-ee80-41cf-86c9-dd590f9d66b6
caps.latest.revision: 37
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 68f185c59672e4414192fc75dbb7bb137800d69f
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="create-application-role-transact-sql"></a>CREATE APPLICATION ROLE(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  현재 데이터베이스에 응용 프로그램 역할을 추가합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
CREATE APPLICATION ROLE application_role_name   
    WITH PASSWORD = 'password' [ , DEFAULT_SCHEMA = schema_name ]  
```  
  
## <a name="arguments"></a>인수  
 *application_role_name*  
 응용 프로그램 역할의 이름을 지정합니다. 이 이름은 데이터베이스의 다른 보안 주체를 참조하는 데 사용된 이름이 아니어야 합니다.  
  
 암호 **='***암호***'**  
 데이터베이스 사용자가 응용 프로그램 역할을 활성화하는 데 사용할 암호를 지정합니다. 항상 강력한 암호를 사용해야 합니다. *암호* 의 인스턴스를 실행 하는 컴퓨터의 Windows 암호 정책 요구 사항을 충족 해야 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]합니다.  
  
 DEFAULT_SCHEMA  **=**  *schema_name*  
 서버가 이 역할에 대한 개체의 이름을 확인할 때 검색할 첫 번째 스키마를 지정합니다. DEFAULT_SCHEMA를 정의하지 않으면 응용 프로그램 역할이 기본 스키마로 DBO를 사용합니다. *schema_name* 데이터베이스에 존재 하지 않는 스키마 일 수 있습니다.  
  
## <a name="remarks"></a>주의  
  
> [!IMPORTANT]  
>  응용 프로그램 역할 암호가 설정된 경우 암호 복잡성이 검사됩니다. 응용 프로그램 역할을 호출하는 응용 프로그램은 해당 암호를 저장해야 합니다. 응용 프로그램 역할 암호는 항상 암호화된 상태로 저장되어야 합니다.  
  
 응용 프로그램 역할에 표시 되는 [sys.database_principals](../../relational-databases/system-catalog-views/sys-database-principals-transact-sql.md) 카탈로그 뷰에 있습니다.  
  
 응용 프로그램 역할을 사용 하는 방법에 대 한 정보를 참조 하십시오. [응용 프로그램 역할](../../relational-databases/security/authentication-access/application-roles.md)합니다.  
  
> [!CAUTION]  
>  [!INCLUDE[ssCautionUserSchema](../../includes/sscautionuserschema-md.md)]  
  
## <a name="permissions"></a>Permissions  
 데이터베이스에 대한 ALTER ANY APPLICATION ROLE 권한이 필요합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 암호 `weekly_receipts` 및 기본 스키마로 `987Gbv876sPYY5m23`가 있는 `Sales`라는 응용 프로그램 역할을 만듭니다.  
  
```  
CREATE APPLICATION ROLE weekly_receipts   
    WITH PASSWORD = '987G^bv876sPY)Y5m23'   
    , DEFAULT_SCHEMA = Sales;  
GO  
```  
  
## <a name="see-also"></a>관련 항목:  
 [응용 프로그램 역할](../../relational-databases/security/authentication-access/application-roles.md)   
 [sp_setapprole&#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-setapprole-transact-sql.md)   
 [ALTER APPLICATION role&#40; Transact SQL &#41;](../../t-sql/statements/alter-application-role-transact-sql.md)   
 [DROP APPLICATION role&#40; Transact SQL &#41;](../../t-sql/statements/drop-application-role-transact-sql.md)   
 [암호 정책](../../relational-databases/security/password-policy.md)   
 [EVENTDATA&#40;Transact-SQL&#41;](../../t-sql/functions/eventdata-transact-sql.md)  
  
  