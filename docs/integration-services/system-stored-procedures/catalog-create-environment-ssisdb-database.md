---
title: catalog.create_environment(SSISDB 데이터베이스) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: language-reference
ms.assetid: 66367092-9f6e-40e6-90bd-81efb078ab70
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: 2710243c72f9e245100c3fdd30a9147c89b7d4d8
ms.sourcegitcommit: 7ccb8f28eafd79a1bddd523f71fe8b61c7634349
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2019
ms.locfileid: "58274365"
---
# <a name="catalogcreateenvironment-ssisdb-database"></a>catalog.create_environment(SSISDB 데이터베이스)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 카탈로그에 환경을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```sql  
catalog.create_environment [@folder_name =] folder_name  
     , [@environment_name =] environment_name  
  [  , [@environment_description =] environment_description ]  
```  
  
## <a name="arguments"></a>인수  
 [@folder_name =] *folder_name*  
 환경을 포함할 폴더의 이름입니다. *folder_name*은 **nvarchar(128)** 입니다.  
  
 [@environment_name =] *environment_name*  
 환경의 이름입니다. *environment_name*은 **nvarchar(128)** 입니다.  
  
 [@environment_description=] *environment_description*  
 환경에 대한 설명(옵션)입니다. *environment_description*은 **nvarchar(1024)** 입니다.  
  
## <a name="return-code-value"></a>반환 코드 값  
 0(성공)  
  
## <a name="result-sets"></a>결과 집합  
 없음  
  
## <a name="permissions"></a>사용 권한  
 이 저장 프로시저를 실행하려면 다음 권한 중 하나가 필요합니다.  
  
-   폴더에 대한 READ 및 MODIFY 권한  
  
-   **ssis_admin** 데이터베이스 역할에 대한 멤버 자격  
  
-   데이터베이스 역할  
  
-   **sysadmin** 서버 역할에 대한 멤버 자격  
  
## <a name="errors-and-warnings"></a>오류 및 경고  
 다음 목록에서는 오류나 경고가 발생하는 몇 가지 조건을 설명합니다.  
  
-   폴더 이름을 찾을 수 없는 경우  
  
-   이름이 같은 환경이 지정된 폴더에 이미 있는 경우  
  
## <a name="remarks"></a>Remarks  
 환경 이름은 폴더 내에서 고유해야 합니다.  
  
  
