---
title: catalog.set_execution_property_override_value | Microsoft Docs
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 37cb3c01-f4c0-4978-8e40-a975456def5a
caps.latest.revision: 4
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 20f2c882a78f5e60931b0152d5877898e1972d0a
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="catalogsetexecutionpropertyoverridevalue"></a>catalog.set_execution_property_override_value
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 카탈로그의 실행 인스턴스에 대한 속성 값을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```tsql  
set_execution_property_override_value [ @execution_id = execution_id  
    , [ @property_path = ] property_path  
    , [ @property_value = ] property_value  
    , [ @sensitive = ] sensitive  
  
```  
  
## <a name="arguments"></a>인수  
 [ @execution_id =] *execution_id*  
 실행 인스턴스의 고유 식별자입니다. *execution_id* 은 **bigint**합니다.  
  
 [ @property_path =] *property_path*  
 패키지의 속성에 대한 경로입니다. *property_path* 은 **nvarchar (4000)**합니다.  
  
 [ @property_value =] *property_value*  
 속성에 할당할 재정의 값입니다. *property_value* 은 **nvarchar (max)**합니다.  
  
 [ @sensitive =] *중요 한*  
 값이 1이면 속성이 중요하며 저장될 때 암호화됩니다. 값이 0이면 속성이 중요하지 않으며 값이 일반 텍스트로 저장됩니다. *중요 한* 인수가 **비트**합니다.  
  
## <a name="remarks"></a>주의  
 이 절차와 동일한 기능을 수행는 **속성 재정의** 섹션의 **고급** 탭은 **패키지 실행** 대화 상자. 속성에 대 한 경로에서 파생 되는 **패키지 경로** 패키지 태스크의 속성입니다.  
  
## <a name="return-code-value"></a>반환 코드 값  
 0(성공)  
  
## <a name="result-sets"></a>결과 집합  
 없음  
  
## <a name="errors-and-warnings"></a>오류 및 경고  
 다음 목록에서는 오류나 경고가 발생하는 몇 가지 조건을 설명합니다.  
  
-   사용자에게 적절한 권한이 없는 경우  
  
-   실행 식별자가 잘못된 경우  
  
-   속성 경로가 잘못된 경우  
  
-   속성 값의 데이터 형식이 속성의 데이터 형식과 일치하지 않는 경우  
  
## <a name="see-also"></a>관련 항목:  
 [catalog.set_execution_parameter_value&#40;SSISDB 데이터베이스&#41;](../../integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database.md)  
  
  