---
title: "dm_execution_performance_counters (SSISDB 데이터베이스) | Microsoft Docs"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 1b38e8e3-c560-4b6e-b60e-bfd7cfcd4fdf
caps.latest.revision: 6
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 67d5ece89f5b964acb2bb55a8cc69ff2fb77b93b
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="functions---dmexecutionperformancecounters"></a>Dm_execution_performance_counters 함수-
[!INCLUDE[tsql-appliesto-ss2014-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2014-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] 서버에서 실행 중인 실행 인스턴스에 대한 성능 통계를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```tsql  
dm_execution_performance_counters [ @execution_id = ] execution_id  
  
```  
  
## <a name="arguments"></a>인수  
 [ @execution_id =] *execution_id*  
 하나 이상의 패키지가 포함된 실행의 고유 식별자입니다. 패키지 실행 태스크로 실행되는 패키지는 부모 패키지와 같은 실행 인스턴스에서 실행됩니다.  
  
 실행 ID를 지정하지 않으면 여러 실행에 대한 성능 통계가 반환됩니다. **ssis_admin** 데이터베이스 역할의 멤버에게는 진행 중인 모든 실행에 대한 성능 통계가 반환됩니다.  **ssis_admin** 데이터베이스 역할이 아닌 멤버에게는 읽기 권한이 있는 진행 중인 실행에 대한 성능 통계가 반환됩니다. *execution_id* 는 **BigInt**합니다.  
  
## <a name="remarks"></a>주의  
 다음 표에서는 dm_execution_performance_counter 함수에서 반환된 카운터 이름 값을 보여 줍니다.  
  
|카운터 이름|Description|  
|------------------|-----------------|  
|BLOB bytes read|데이터 흐름 엔진이 모든 원본에서 읽는 BLOB(Binary Large Object) 데이터의 바이트 수입니다.|  
|BLOB bytes written|데이터 흐름 엔진이 모든 대상에 기록하는 BLOB 데이터의 바이트 수입니다.|  
|BLOB files in use|데이터 흐름 엔진이 스풀링을 위해 사용하고 있는 BLOB 파일 수입니다.|  
|Buffer memory|실제 메모리 및 가상 메모리를 포함한 Integration Services 버퍼에서 사용되는 메모리의 양입니다.|  
|Buffers in use|모든 데이터 흐름 구성 요소 및 데이터 흐름 엔진이 사용 중인 모든 유형의 버퍼 개체 수입니다.|  
|Buffers Spooled|디스크에 쓴 버퍼 수입니다.|  
|Flat buffer memory|모든 플랫 버퍼에서 사용되는 메모리의 양(바이트)입니다. 플랫 버퍼는 구성 요소가 데이터 저장에 사용하는 메모리 블록입니다.|  
|Flat buffers in use|데이터 흐름 엔진이 사용하는 플랫 버퍼 수입니다. 모든 플랫 버퍼는 전용 버퍼입니다.|  
|Private buffer memory|모든 전용 버퍼에서 사용되는 메모리의 양입니다. 전용 버퍼는 변환 작업에서 임시 작업용으로 사용하는 버퍼입니다.<br /><br /> 데이터 흐름 엔진이 데이터 흐름을 지원하기 위해 만드는 버퍼는 전용 버퍼가 아닙니다.|  
|Private buffers in use|변환 작업에서 임시 작업용으로 사용하는 버퍼 수입니다.|  
|Rows read|실행 준비가 된 총 행 수입니다.|  
|Rows written|실행에서 쓰여진 총 행 수입니다.|  
  
## <a name="return"></a>반환 값  
 dm_execution_performance_counters 함수는 진행 중인 실행에 대해 다음과 같은 열이 있는 테이블을 반환합니다. 반환되는 정보는 실행에 포함된 모든 패키지에 대한 정보입니다. 진행 중인 실행이 없는 경우 빈 테이블이 반환됩니다.  
  
|열 이름|열 유형|Description|주의|  
|-----------------|-----------------|-----------------|-------------|  
|execution_id|**BigInt**<br /><br /> **NULL** 유효한 값이 아닙니다.|패키지를 포함한 실행의 고유 식별자입니다.||  
|counter_name|**nvarchar (128)**|카운터의 이름입니다.|참조는 **주의** 값 섹션.|  
|counter_value|**BigInt**|카운터가 반환하는 값입니다.||  
  
## <a name="example"></a>예제  
 다음 예에서는 이 함수가 ID가 34인 실행 인스턴스에 대한 통계를 반환합니다.  
  
```  
select * from [catalog].[dm_execution_performance_counters] (34)  
```  
  
## <a name="example"></a>예제  
 다음 예에서는 이 함수가 사용자의 사용 권한에 따라 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] 서버에서 실행 중인 모든 실행 인스턴스에 대한 통계를 반환합니다.  
  
```  
select * from [catalog].[dm_execution_performance_counters] (NULL)  
  
```  
  
## <a name="permissions"></a>Permissions  
 이 기능을 사용하려면 다음 권한 중 하나가 필요합니다.  
  
-   실행 인스턴스에 대한 READ 및 MODIFY 권한  
  
-   멤버 자격에는 **ssis_admin** 데이터베이스 역할  
  
-   멤버 자격에는 **sysadmin** 서버 역할  
  
## <a name="errors-and-warnings"></a>오류 및 경고  
 다음 목록에서는 함수 실패 조건을 설명합니다.  
  
-   사용자에게 지정된 실행에 대한 MODIFY 권한이 없습니다.  
  
-   지정된 실행 ID가 잘못되었습니다.  
  
  