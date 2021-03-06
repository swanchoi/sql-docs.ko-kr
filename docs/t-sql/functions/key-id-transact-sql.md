---
title: KEY_ID(Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- Key_ID
- Key_ID_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- identification numbers [SQL Server], symmetric keys
- KEY_ID function
- symmetric keys [SQL Server], IDs
- IDs [SQL Server], symmetric keys
ms.assetid: d7309542-dbbe-41dc-b42e-5d9a1c8b4838
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 1ffafacce7d82645d0f1e8c0335637d26d850798
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47604761"
---
# <a name="keyid-transact-sql"></a>KEY_ID(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  현재 데이터베이스에 있는 대칭 키의 ID를 반환합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
Key_ID ( 'Key_Name' )  
```  
  
## <a name="arguments"></a>인수  
 **'** *Key_Name* **'**  
 데이터베이스에 있는 대칭 키의 이름입니다.  
  
## <a name="return-types"></a>반환 형식  
 **int**  
  
## <a name="remarks"></a>Remarks  
 임시 키의 이름은 숫자 기호(#)로 시작해야 합니다.  
  
## <a name="permissions"></a>Permissions  
 임시 키는 생성된 세션에서만 사용할 수 있으므로 액세스 권한이 필요 없습니다. 임시 키가 아닌 키에 액세스하려면 호출자는 이 키에 대한 사용 권한이 필요하며 VIEW 권한이 거부된 경험이 없어야 합니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-returning-the-id-of-a-symmetric-key"></a>1. 대칭 키의 ID 반환  
 다음은 `ABerglundKey1`이라는 키의 ID를 반환하는 예입니다.  
  
```  
SELECT KEY_ID('ABerglundKey1');  
```  
  
### <a name="b-returning-the-id-of-a-temporary-symmetric-key"></a>2. 임시 대칭 키의 ID 반환  
 다음은 임시 대칭 키의 ID를 반환하는 예입니다. 키 이름 앞에 `#`이 있습니다.  
  
```  
SELECT KEY_ID('#ABerglundKey2');  
```  
  
## <a name="see-also"></a>참고 항목  
 [KEY_GUID &#40;Transact-SQL&#41;](../../t-sql/functions/key-guid-transact-sql.md)   
 [CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/create-symmetric-key-transact-sql.md)   
 [sys.symmetric_keys &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql.md)   
 [sys.key_encryptions&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-key-encryptions-transact-sql.md)   
 [암호화 계층](../../relational-databases/security/encryption/encryption-hierarchy.md)  
  
  
