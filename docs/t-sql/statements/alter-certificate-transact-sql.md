---
title: ALTER CERTIFICATE (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 04/12/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ALTER_CERTIFICATE_TSQL
- ALTER CERTIFICATE
dev_langs:
- TSQL
helpviewer_keywords:
- ENCRYPTION BY PASSWORD option
- encryption [SQL Server], certificates
- modifying certificates
- private keys [SQL Server]
- ALTER CERTIFICATE statement
- certificates [SQL Server], modifying
ms.assetid: da4dc25e-72e0-4036-87ce-22de83160836
caps.latest.revision: 46
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: cb83f32e2187025c916ee7291e5b52725db5af2c
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="alter-certificate-transact-sql"></a>ALTER CERTIFICATE(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  인증서를 암호화하는 데 사용된 개인 키를 변경하거나 개인 키가 없는 경우 추가합니다. [!INCLUDE[ssSB](../../includes/sssb-md.md)]에 대한 인증서의 가용성을 변경합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
-- Syntax for SQL Server and Azure SQL Database  
  
ALTER CERTIFICATE certificate_name   
      REMOVE PRIVATE KEY  
    | WITH PRIVATE KEY ( <private_key_spec> [ ,... ] )  
    | WITH ACTIVE FOR BEGIN_DIALOG = [ ON | OFF ]  
  
<private_key_spec> ::=   
      FILE = 'path_to_private_key'   
    | DECRYPTION BY PASSWORD = 'key_password'   
    | ENCRYPTION BY PASSWORD = 'password'   
```  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
ALTER CERTIFICATE certificate_name   
{  
      REMOVE PRIVATE KEY  
    | WITH PRIVATE KEY (   
        FILE = '<path_to_private_key>',  
        DECRYPTION BY PASSWORD = '<key password>' )
}  
```  
  
## <a name="arguments"></a>인수  
 *certificate_name*  
 데이터베이스에서 인증서를 식별하는 고유한 이름입니다.  
  
 파일 **='***path_to_private_key***'**  
 개인 키에 대해 파일 이름을 포함하여 전체 경로를 지정합니다. 이 매개 변수는 로컬 경로이거나 네트워크 위치에 대한 UNC 경로가 될 수 있습니다. 이 파일은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 서비스 계정의 보안 컨텍스트 내에서 액세스할 수 있습니다. 이 옵션을 사용할 경우 지정한 파일에 대한 액세스 권한이 서비스 계정에 있는지 확인해야 합니다.  
  
 DECRYPTION BY PASSWORD **='***key_password***'**  
 개인 키를 해독하는 데 필요한 암호를 지정합니다.  
  
 ENCRYPTION BY PASSWORD **='***암호***'**  
 데이터베이스에서 인증서의 개인 키를 암호화하는 데 사용되는 암호를 지정합니다. *암호* 의 인스턴스를 실행 하는 컴퓨터의 Windows 암호 정책 요구 사항을 충족 해야 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]합니다. 자세한 내용은 [Password Policy](../../relational-databases/security/password-policy.md)을 참조하세요.  
  
 REMOVE PRIVATE KEY  
 데이터베이스 내에서 더 이상 개인 키를 유지하지 않도록 지정합니다.  
  
 ACTIVE FOR BEGIN_DIALOG  **=**  {ON | OFF}  
 [!INCLUDE[ssSB](../../includes/sssb-md.md)] 대화 기능의 시작자가 인증서를 사용할 수 있게 합니다.  
  
## <a name="remarks"></a>주의  
 개인 키로 지정 된 공개 키와 일치 해야 *certificate_name*합니다.  
  
 파일에 있는 암호가 Null 암호로 보호되는 경우에는 DECRYPTION BY PASSWORD 절을 생략할 수 있습니다.  
  
 데이터베이스에 있는 기존 인증서의 개인 키를 파일에서 가져오는 경우 해당 개인 키는 데이터베이스 마스터 키로 자동으로 보호됩니다. 개인 키를 암호로 보호하려면 ENCRYPTION BY PASSWORD 절을 사용합니다.  
  
 REMOVE PRIVATE KEY 옵션을 사용하면 데이터베이스에서 인증서의 개인 키를 삭제할 수 있습니다. 서명의 유효성 검증에 인증서를 사용할 때 또는 개인 키가 필요 없는 [!INCLUDE[ssSB](../../includes/sssb-md.md)] 시나리오에서 이 옵션을 사용할 수 있습니다. 대칭 키를 보호하는 인증서의 개인 키는 제거하지 마십시오.  
  
 데이터베이스 마스터 키를 사용하여 개인 키를 암호화한 경우에는 해독 암호를 지정할 필요가 없습니다.  
  
> [!IMPORTANT]  
>  데이터베이스에서 개인 키를 제거하기 전에 복사본을 만들어 보관하십시오. 자세한 내용은 [BACKUP CERTIFICATE&#40;Transact-SQL&#41;](../../t-sql/statements/backup-certificate-transact-sql.md)를 참조하세요.  
  
 포함된 데이터베이스에서는 WITH PRIVATE KEY 옵션을 사용할 수 없습니다.  
  
## <a name="permissions"></a>Permissions  
 인증서에 대한 ALTER 권한이 필요합니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-changing-the-password-of-a-certificate"></a>1. 인증서 암호 변경  
  
```  
ALTER CERTIFICATE Shipping04   
    WITH PRIVATE KEY (DECRYPTION BY PASSWORD = 'pGF$5DGvbd2439587y',  
    ENCRYPTION BY PASSWORD = '4-329578thlkajdshglXCSgf');  
GO  
```  
  
### <a name="b-changing-the-password-that-is-used-to-encrypt-the-private-key"></a>2. 개인 키를 암호화하는 데 사용된 암호 변경  
  
```  
ALTER CERTIFICATE Shipping11   
    WITH PRIVATE KEY (ENCRYPTION BY PASSWORD = '34958tosdgfkh##38',  
    DECRYPTION BY PASSWORD = '95hkjdskghFDGGG4%');  
GO  
```  
  
### <a name="c-importing-a-private-key-for-a-certificate-that-is-already-present-in-the-database"></a>3. 데이터베이스의 기존 인증서에 대한 개인 키 가져오기  
  
```  
ALTER CERTIFICATE Shipping13   
    WITH PRIVATE KEY (FILE = 'c:\\importedkeys\Shipping13',  
    DECRYPTION BY PASSWORD = 'GDFLKl8^^GGG4000%');  
GO  
```  
  
### <a name="d-changing-the-protection-of-the-private-key-from-a-password-to-the-database-master-key"></a>4. 개인 키 보호를 암호에서 데이터베이스 마스터 키로 변경  
  
```  
ALTER CERTIFICATE Shipping15   
    WITH PRIVATE KEY (DECRYPTION BY PASSWORD = '95hk000eEnvjkjy#F%');  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>예: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] 및[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="e-importing-a-private-key-for-a-certificate-that-is-already-present-in-the-database"></a>5. 데이터베이스의 기존 인증서에 대한 개인 키 가져오기  
  
```  
ALTER CERTIFICATE Shipping13   
    WITH PRIVATE KEY (FILE = '\\ServerA7\importedkeys\Shipping13',  
    DECRYPTION BY PASSWORD = 'GDFLKl8^^GGG4000%');  
GO  
```  
  
## <a name="see-also"></a>관련 항목:  
 [CREATE CERTIFICATE&#40;Transact-SQL&#41;](../../t-sql/statements/create-certificate-transact-sql.md)   
 [DROP certificate&#40; Transact SQL &#41;](../../t-sql/statements/drop-certificate-transact-sql.md)   
 [BACKUP CERTIFICATE&#40;Transact-SQL&#41;](../../t-sql/statements/backup-certificate-transact-sql.md)   
 [암호화 계층](../../relational-databases/security/encryption/encryption-hierarchy.md)   
 [EVENTDATA&#40;Transact-SQL&#41;](../../t-sql/functions/eventdata-transact-sql.md)  
  
  

