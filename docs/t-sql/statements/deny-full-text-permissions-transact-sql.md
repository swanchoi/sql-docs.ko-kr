---
title: "DENY 전체 텍스트 사용 권한 (Transact SQL) | Microsoft Docs"
ms.custom: 
ms.date: 05/15/2017
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
- full-text search [SQL Server], permissions
- denying permissions [SQL Server], fulll-text
- full-text catalogs [SQL Server], permissions
- full-text stoplist [SQL Server], permissions
- DENY statement, full-text permissions
ms.assetid: d86e9a1d-0938-4ec2-a169-2d0564f3642e
caps.latest.revision: 26
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 010507ec0b9fdcec89c6f8ee687b1c26b4c4436e
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="deny-full-text-permissions-transact-sql"></a>DENY 전체 텍스트 사용 권한(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  전체 텍스트 카탈로그 및 전체 텍스트 중지 목록에 대한 사용 권한을 거부합니다.  
  

 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
DENY permission [ ,...n ] ON  
    FULLTEXT   
        {  
           CATALOG :: full-text_catalog_name  
           |  
           STOPLIST :: full-text_stoplist_name  
        }  
    TO database_principal [ ,...n ] [ CASCADE ]  
        [ AS denying_principal ]  
```  
  
## <a name="arguments"></a>인수  
 *사용 권한*  
 사용 권한의 이름입니다. 보안 개체에 대한 사용 권한의 올바른 매핑에 대해서는 이 항목 뒷부분의 "주의" 섹션에 설명되어 있습니다.  
  
 전체 텍스트 카탈로그에 **::***전체 text_catalog_name*  
 사용 권한을 거부할 전체 텍스트 카탈로그를 지정합니다. 범위 한정자 **::** 가 필요 합니다.  
  
 전체 텍스트 중지 목록에 **::***전체 text_stoplist_name*  
 사용 권한을 거부할 전체 텍스트 중지 목록을 지정합니다. 범위 한정자 **::** 가 필요 합니다.  
  
 *데이터베이스 _ 보안 주체*  
 사용 권한을 거부할 보안 주체를 지정합니다. 다음 중 하나일 수 있습니다.  
  
-   데이터베이스 사용자  
  
-   데이터베이스 역할  
  
-   응용 프로그램 역할  
  
-   Windows 로그인에 매핑된 데이터베이스 사용자  
  
-   Windows 그룹에 매핑된 데이터베이스 사용자  
  
-   인증서에 매핑된 데이터베이스 사용자  
  
-   비대칭 키에 매핑된 데이터베이스 사용자  
  
-   서버 보안 주체에 매핑되지 않은 데이터베이스 사용자  
  
 CASCADE  
 사용 권한이 거부된 보안 주체에게 사용 권한을 부여 받은 다른 보안 주체의 사용 권한도 거부됨을 나타냅니다.  
  
 *denying_principal*  
 이 쿼리를 실행하는 보안 주체가 사용 권한을 거부하는 권한을 부여할 수 있는 다른 보안 주체를 지정합니다. 다음 중 하나일 수 있습니다.  
  
-   데이터베이스 사용자  
  
-   데이터베이스 역할  
  
-   응용 프로그램 역할  
  
-   Windows 로그인에 매핑된 데이터베이스 사용자  
  
-   Windows 그룹에 매핑된 데이터베이스 사용자  
  
-   인증서에 매핑된 데이터베이스 사용자  
  
-   비대칭 키에 매핑된 데이터베이스 사용자  
  
-   서버 보안 주체에 매핑되지 않은 데이터베이스 사용자  
  
  
## <a name="fulltext-catalog-permissions"></a>FULLTEXT CATALOG 사용 권한  
 전체 텍스트 카탈로그는 사용 권한 계층에서 부모 데이터베이스에 포함된 데이터베이스 수준 보안 개체입니다. 다음 표에는 전체 텍스트 카탈로그에 대해 거부할 수 있는 가장 제한적인 특정 사용 권한이 의미상 이러한 사용 권한을 포함하는 보다 일반적인 사용 권한과 함께 나열되어 있습니다.  
  
|전체 텍스트 카탈로그 사용 권한|전체 텍스트 카탈로그 사용 권한에 포함되는 사용 권한|데이터베이스 사용 권한에 포함된 사용 권한|  
|-----------------------------------|----------------------------------------------|------------------------------------|  
|CONTROL|CONTROL|CONTROL|  
|TAKE OWNERSHIP|CONTROL|CONTROL|  
|ALTER|CONTROL|ALTER ANY FULLTEXT CATALOG|  
|REFERENCES|CONTROL|REFERENCES|  
|VIEW DEFINITION|CONTROL|VIEW DEFINITION|  
  
## <a name="fulltext-stoplist-permissions"></a>FULLTEXT STOPLIST 사용 권한  
 전체 텍스트 중지 목록은 사용 권한 계층에서 부모 데이터베이스에 포함된 데이터베이스 수준 보안 개체입니다. 다음 표에는 전체 텍스트 중지 목록에 대해 거부할 수 있는 가장 제한적인 특정 사용 권한과, 의미상 이러한 사용 권한을 포함하는 보다 일반적인 사용 권한이 함께 나열되어 있습니다.  
  
|전체 텍스트 중지 목록 사용 권한|전체 텍스트 중지 목록 사용 권한에 포함되는 사용 권한|데이터베이스 사용 권한에 포함된 사용 권한|  
|------------------------------------|-----------------------------------------------|------------------------------------|  
|ALTER|CONTROL|ALTER ANY FULLTEXT CATALOG|  
|CONTROL|CONTROL|CONTROL|  
|REFERENCES|CONTROL|REFERENCES|  
|TAKE OWNERSHIP|CONTROL|CONTROL|  
|VIEW DEFINITION|CONTROL|VIEW DEFINITION|  
  
## <a name="permissions"></a>Permissions  
 전체 텍스트 카탈로그에 대한 CONTROL 권한이 필요합니다. AS 옵션을 사용하는 경우 지정된 보안 주체가 전체 텍스트 카탈로그를 소유해야 합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [APPLICATION role&#40; 만들기 Transact SQL &#41;](../../t-sql/statements/create-application-role-transact-sql.md)   
 [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/create-asymmetric-key-transact-sql.md)   
 [CREATE CERTIFICATE&#40;Transact-SQL&#41;](../../t-sql/statements/create-certificate-transact-sql.md)   
 [전체 텍스트 카탈로그 &#40; 만들기 Transact SQL &#41;](../../t-sql/statements/create-fulltext-catalog-transact-sql.md)   
 [전체 텍스트 중지 목록 &#40; 만들기 Transact SQL &#41;](../../t-sql/statements/create-fulltext-stoplist-transact-sql.md)   
 [DENY&#40;Transact-SQL&#41;](../../t-sql/statements/deny-transact-sql.md)   
 [암호화 계층](../../relational-databases/security/encryption/encryption-hierarchy.md)   
 [sys.fn_my_permissions &#40; Transact SQL &#41;](../../relational-databases/system-functions/sys-fn-my-permissions-transact-sql.md)   
 [GRANT 전체 텍스트 사용 권한 &#40; Transact SQL &#41;](../../t-sql/statements/grant-full-text-permissions-transact-sql.md)   
 [HAS_PERMS_BY_NAME&#40;Transact-SQL&#41;](../../t-sql/functions/has-perms-by-name-transact-sql.md)   
 [사용 권한&#40;데이터베이스 엔진&#41;](../../relational-databases/security/permissions-database-engine.md)   
 [보안 주체&#40;데이터베이스 엔진&#41;](../../relational-databases/security/authentication-access/principals-database-engine.md)   
 [sys.fn_builtin_permissions&#40;Transact-SQL&#41;](../../relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql.md)   
 [sys.fulltext_catalogs &#40; Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql.md)   
 [sys.fulltext_stoplists&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql.md)  
  
  
