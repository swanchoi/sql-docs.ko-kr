---
title: 자격 증명 만들기 | Microsoft 문서
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: security
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- credentials [SQL Server], creating
- authentication [SQL Server], credentials
- logins [SQL Server], credentials
ms.assetid: c1e77e91-2a69-40d9-b8b3-97cffc710586
author: VanMSFT
ms.author: vanto
manager: craigg
ms.openlocfilehash: e55e29f428185f195b65ae046df3aa63b8c35c3a
ms.sourcegitcommit: 2429fbcdb751211313bd655a4825ffb33354bda3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "52539657"
---
# <a name="create-a-credential"></a>Create a Credential
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  이 항목에서는 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] 또는 [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] 을 사용하여 [!INCLUDE[tsql](../../../includes/tsql-md.md)]에서 자격 증명을 만드는 방법에 대해 설명합니다.  
  
 자격 증명을 사용하여 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 인증 사용자가 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]외부에서 ID를 가질 수 있습니다. 자격 증명은 주로 EXTERNAL_ACCESS 권한 집합이 포함된 어셈블리에서 코드를 실행하는 데 사용됩니다. [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 인증 사용자가 백업을 저장할 파일 위치와 같은 도메인 리소스에 액세스해야 할 경우에도 자격 증명을 사용할 수 있습니다.  
  
 자격 증명은 여러 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 로그인에 동시에 매핑할 수 있습니다. [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 로그인은 한 번에 하나의 자격 증명에만 매핑할 수 있습니다. 자격 증명을 만들었으면 **로그인 속성(일반 페이지)** 을 사용하여 로그인을 자격 증명에 매핑합니다.  
  
 **항목 내용**  
  
-   **시작하기 전 주의 사항:**  
  
     [제한 사항](#Restrictions)  
  
     [보안](#Security)  
  
-   **다음을 사용하여 자격 증명을 만듭니다.**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> 시작하기 전 주의 사항  
  
###  <a name="Restrictions"></a> 제한 사항  
  
-   공급자에 대해 매핑된 로그인 자격 증명이 없으면 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 서비스 계정에 매핑된 자격 증명이 사용됩니다.  
  
-   자격 증명이 고유한 공급자에 대해 사용되는 경우 로그인에 여러 개의 매핑된 자격 증명이 있을 수 있습니다. 로그인별로 각 공급자에 하나의 매핑된 자격 증명만 있어야 합니다. 동일한 자격 증명이 다른 로그인에 매핑될 수 있습니다.  
  
###  <a name="Security"></a> 보안  
  
####  <a name="Permissions"></a> Permissions  
 자격 증명을 만들거나 수정하려면 ALTER ANY CREDENTIAL 권한이 필요하고 로그인을 자격 증명에 매핑하려면 ALTER ANY LOGIN 권한이 필요합니다.  
  
##  <a name="SSMSProcedure"></a> SQL Server Management Studio 사용  
  
#### <a name="to-create-a-credential"></a>자격 증명을 만들려면  
  
1.  개체 탐색기에서 **보안** 폴더를 확장합니다.  
  
2.  **자격 증명** 폴더를 마우스 오른쪽 단추로 클릭하고 **새 자격 증명...** 을 선택합니다.  
  
3.  **새 자격 증명** 대화 상자의 **자격 증명 이름** 상자에 자격 증명의 이름을 입력합니다.  
  
4.  **의 컨텍스트를 벗어날 때 나가는 연결에 사용할 계정의 이름을** ID [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]상자에 입력합니다. 일반적으로 이 이름은 Windows 사용자 계정이지만 ID는 다른 유형의 계정일 수 있습니다.  
  
     또는 줄임표 **(…)** 를 클릭하여 **사용자 또는 그룹 선택** 대화 상자를 엽니다.  
  
5.  **암호** 상자와 **암호 확인** 상자에 **ID** 상자에서 지정한 계정의 암호를 입력합니다. **ID** 가 Windows 사용자 계정일 경우 이 상자의 내용은 Windows 암호에 해당합니다. 암호가 필요하지 않은 경우 **암호** 를 비워 둘 수 있습니다.  
  
6.  **암호화 공급자 사용**을 선택하여 EKM(확장 가능 키 관리) 공급자가 자격 증명을 확인하도록 설정합니다. 자세한 내용은 [EKM&#40;확장 가능 키 관리&#41;](../../../relational-databases/security/encryption/extensible-key-management-ekm.md)을 참조하세요.  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="TsqlProcedure"></a> Transact-SQL 사용  
  
#### <a name="to-create-a-credential"></a>자격 증명을 만들려면  
  
1.  **개체 탐색기**에서 [!INCLUDE[ssDE](../../../includes/ssde-md.md)]인스턴스에 연결합니다.  
  
2.  표준 도구 모음에서 **새 쿼리**를 클릭합니다.  
  
3.  다음 예를 복사하여 쿼리 창에 붙여 넣고 **실행**을 클릭합니다.  
  
    ```  
    -- Creates the credential called "AlterEgo.".   
    -- The credential contains the Windows user "Mary5" and a password.  
    CREATE CREDENTIAL AlterEgo WITH IDENTITY = 'Mary5',   
        SECRET = '<EnterStrongPasswordHere>';  
    GO  
    ```  
  
 자세한 내용은 [CREATE CREDENTIAL&#40;Transact-SQL&#41;](../../../t-sql/statements/create-credential-transact-sql.md)을 참조하세요.  
  
  
