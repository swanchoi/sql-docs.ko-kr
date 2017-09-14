---
title: "DENY 유형 사용 권한 (Transact SQL) | Microsoft Docs"
ms.custom: 
ms.date: 06/09/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- DENY statement, types
- permissions [SQL Server], types
- type permissions [SQL Server]
- denying permissions [SQL Server], types
ms.assetid: 564e3500-c567-43dc-993b-9ab50e99cf3f
caps.latest.revision: 28
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: d1fab44dfa4778f222965453a16ed052adc640bc
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="deny-type-permissions-transact-sql"></a>DENY 유형 사용 권한(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 유형에 대한 사용 권한을 거부합니다.  

 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
DENY permission  [ ,...n ] ON TYPE :: [ schema_name . ] type_name  
        TO <database_principal> [ ,...n ]  
    [ CASCADE ]  
    [ AS <database_principal> ]  
  
<database_principal> ::=   
        Database_user   
    | Database_role   
    | Application_role   
    | Database_user_mapped_to_Windows_User   
    | Database_user_mapped_to_Windows_Group   
    | Database_user_mapped_to_certificate   
    | Database_user_mapped_to_asymmetric_key   
    | Database_user_with_no_login  
```  
  
## <a name="arguments"></a>인수  
 *사용 권한*  
 유형에 대해 거부할 수 있는 사용 권한을 지정합니다. 사용 권한 목록은 이 항목의 뒤에 나오는 주의 섹션을 참조하세요.  
  
 형식에 **::** [ *schema_name***합니다.** ] *type_name*  
 사용 권한을 거부할 유형을 지정합니다. 범위 한정자 (**::**)가 필요 합니다. 경우 *schema_name* 를 지정 하지 않으면 기본 스키마가 사용 됩니다. 경우 *schema_name* 지정 된 스키마 범위 한정자 (**.**)가 필요 합니다.  
  
 \<데이터베이스 _ 보안 주체 >  
 사용 권한을 거부할 보안 주체를 지정합니다.  
  
 CASCADE  
 사용 권한이 거부된 보안 주체에게 사용 권한을 부여 받은 다른 보안 주체의 사용 권한도 거부됨을 나타냅니다.  
  
 AS \<데이터베이스 _ 보안 주체 >  
 이 쿼리를 실행하는 보안 주체가 사용 권한을 거부하는 권한을 부여할 수 있는 다른 보안 주체를 지정합니다.  
  
 *Database_user*  
 데이터베이스 사용자를 지정합니다.  
  
 *Database_role*  
 데이터베이스 역할을 지정합니다.  
  
 *Application_role*  
   
 응용 프로그램 역할을 지정합니다.  
  
 *Database_user_mapped_to_Windows_User*  
 
 Windows 사용자로 매핑된 데이터베이스 사용자를 지정합니다.  
  
 *Database_user_mapped_to_Windows_Group*  
 
 Windows 그룹으로 매핑된 데이터베이스 사용자를 지정합니다.  
  
 *Database_user_mapped_to_certificate*  
 
 인증서로 매핑된 데이터베이스 사용자를 지정합니다.  
  
 *Database_user_mapped_to_asymmetric_key*  
  
 비대칭 키로 매핑된 데이터베이스 사용자를 지정합니다.  
  
 *Database_user_with_no_login*  
 해당 서버 수준의 보안 주체가 없는 데이터베이스 사용자를 지정합니다.  
  
## <a name="remarks"></a>주의  
 유형은 사용 권한 계층에서 해당 유형의 부모인 스키마에 포함된 스키마 수준 보안 개체입니다.  
  
> [!IMPORTANT]  
>  **GRANT**, **DENY** 및 **해지** 권한은 시스템 형식에 적용 되지 않습니다. 사용자 정의 형식에는 권한을 부여할 수 있습니다. 사용자 정의 형식에 대 한 자세한 내용은 참조 [SQL Server의 사용자 정의 형식 작업](../../relational-databases/clr-integration-database-objects-user-defined-types/working-with-user-defined-types-in-sql-server.md)합니다.  
  
 다음 표에는 유형에 대해 거부할 수 있는 가장 제한적인 특정 사용 권한이 의미상 이러한 사용 권한을 포함하는 보다 일반적인 사용 권한과 함께 나열되어 있습니다.  
  
|유형 사용 권한|유형 사용 권한에 포함된 사용 권한|스키마 사용 권한에 포함된 사용 권한|  
|---------------------|--------------------------------|----------------------------------|  
|CONTROL|CONTROL|CONTROL|  
|CREATE 문을 실행하기 전에|CONTROL|CREATE 문을 실행하기 전에|  
|REFERENCES|CONTROL|REFERENCES|  
|TAKE OWNERSHIP|CONTROL|CONTROL|  
|VIEW DEFINITION|CONTROL|VIEW DEFINITION|  
  
## <a name="permissions"></a>Permissions  
 해당 유형에 대한 CONTROL 권한이 필요합니다. AS 절을 사용하는 경우 지정된 보안 주체가 사용 권한을 거부할 유형을 소유해야 합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 `VIEW DEFINITION`를 지정하여 `CASCADE`에 대해 사용자 정의 형식 `PhoneNumber`에 대한 `KhalidR` 사용 권한을 거부합니다. `PhoneNumber`는 스키마 `Telemarketing`에 있습니다.  
  
```  
DENY VIEW DEFINITION ON TYPE::Telemarketing.PhoneNumber   
    TO KhalidR CASCADE;  
GO  
```  
  
## <a name="see-also"></a>관련 항목:  
 [GRANT 유형 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/grant-type-permissions-transact-sql.md)   
 [REVOKE 유형 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/revoke-type-permissions-transact-sql.md)   
 [CREATE TYPE&#40;Transact-SQL&#41;](../../t-sql/statements/create-type-transact-sql.md)   
 [보안 주체&#40;데이터베이스 엔진&#41;](../../relational-databases/security/authentication-access/principals-database-engine.md)   
 [사용 권한&#40;데이터베이스 엔진&#41;](../../relational-databases/security/permissions-database-engine.md)   
 [보안 개체](../../relational-databases/security/securables.md)  
  
  
