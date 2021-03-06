---
title: 차원 처리 대상 편집기 (고급 페이지) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimprocessingtransformation.advanced.f1
helpviewer_keywords:
- Dimension Processing Destination Editor
ms.assetid: 2b30835a-2680-4d98-89a4-4f17e29e3818
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: 9e8cddc307b53e640aa9b43a459c062b411cd64b
ms.sourcegitcommit: 5a8678bf85f65be590676745a7fe4fcbcc47e83d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58389231"
---
# <a name="dimension-processing-destination-editor-advanced-page"></a>차원 처리 대상 편집기(고급 페이지)
  **차원 처리 대상 편집기** 대화 상자의 **고급** 페이지를 사용하여 오류 처리 방법을 구성할 수 있습니다.  
  
 차원 처리 대상에 대한 자세한 내용은 [Dimension Processing Destination](data-flow/dimension-processing-destination.md)을 참조하십시오.  
  
## <a name="options"></a>변수  
 **기본 오류 구성 사용**  
 기본 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] 오류 처리를 사용할지 여부를 지정합니다. 기본적으로 이 값은 `True`입니다.  
  
 **키 오류 동작**  
 사용할 수 없는 키 값이 있는 레코드의 처리 방법을 지정합니다.  
  
|값|Description|  
|-----------|-----------------|  
|**ConvertToUnknown**|사용할 수 없는 키 값을 `UnknownMember` 값으로 변환합니다.|  
|**DiscardRecord**|레코드를 삭제합니다.|  
  
 **오류 무시**  
 오류를 무시하도록 지정합니다.  
  
 **오류 발생 시 중지**  
 오류가 발생하면 처리를 중지하도록 지정합니다.  
  
 **오류 개수**  
 **오류 발생 시 중지**를 선택한 경우 처리를 중지하는 데 기준이 되는 오류 임계값을 지정합니다.  
  
 **오류 시 수행할 동작**  
 **오류 발생 시 중지**를 선택한 경우 오류 임계값에 도달했을 때 수행할 동작을 지정합니다.  
  
|값|Description|  
|-----------|-----------------|  
|**StopProcessing**|처리를 중지합니다.|  
|**StopLogging**|오류 기록을 중지합니다.|  
  
 **키를 찾을 수 없는 경우**  
 키를 찾을 수 없을 때 수행할 동작을 지정합니다. 기본적으로 이 값은 **ReportAndContinue**입니다.  
  
|값|Description|  
|-----------|-----------------|  
|**IgnoreError**|오류를 무시하고 처리를 계속합니다.|  
|**ReportAndContinue**|오류를 보고하고 처리를 계속합니다.|  
|**ReportAndStop**|오류를 보고하고 처리를 중지합니다.|  
  
 **중복 키**  
 중복 키 오류가 발생할 때 수행할 동작을 지정합니다. 기본적으로 이 값은 **IgnoreError**입니다.  
  
|값|Description|  
|-----------|-----------------|  
|**IgnoreError**|오류를 무시하고 처리를 계속합니다.|  
|**ReportAndContinue**|오류를 보고하고 처리를 계속합니다.|  
|**ReportAndStop**|오류를 보고하고 처리를 중지합니다.|  
  
 **Null 키가 알 수 없는 상태로 변환된 경우**  
 Null 키가 `UnknownMember` 값으로 변환된 경우 수행할 동작을 지정합니다. 기본적으로 이 값은 **IgnoreError**입니다.  
  
|값|Description|  
|-----------|-----------------|  
|**IgnoreError**|오류를 무시하고 처리를 계속합니다.|  
|**ReportAndContinue**|오류를 보고하고 처리를 계속합니다.|  
|**ReportAndStop**|오류를 보고하고 처리를 중지합니다.|  
  
 **Null 키가 허용되지 않는 경우**  
 Null 키가 허용되지 않는데 Null 키가 있는 경우에 수행할 동작을 지정합니다. 기본적으로 이 값은 **ReportAndContinue**입니다.  
  
|값|Description|  
|-----------|-----------------|  
|**IgnoreError**|오류를 무시하고 처리를 계속합니다.|  
|**ReportAndContinue**|오류를 보고하고 처리를 계속합니다.|  
|**ReportAndStop**|오류를 보고하고 처리를 중지합니다.|  
  
 **오류 로그 경로**  
 오류 로그의 경로를 입력하거나 **찾아보기(...)** 단추를 클릭하여 대상을 선택합니다.  
  
 **찾아보기(...)**  
 오류 로그의 경로를 선택합니다.  
  
## <a name="see-also"></a>관련 항목  
 [Integration Services 오류 및 메시지 참조](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [차원 처리 대상 편집기&#40;연결 관리자 페이지&#41;](../../2014/integration-services/dimension-processing-destination-editor-connection-manager-page.md)   
 [차원 처리 대상 편집기&#40;매핑 페이지&#41;](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md)  
  
  
