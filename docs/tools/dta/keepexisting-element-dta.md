---
title: KeepExisting 요소 (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- KeepExisting element
ms.assetid: e67aae61-d06d-4a03-85ba-6516c3502dce
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: ece977251d71ff25a0dba52a0ba4f2d1f72d55a1
ms.sourcegitcommit: 0f7cf9b7ab23df15624d27c129ab3a539e8b6457
ms.translationtype: MTE75
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51290829"
---
# <a name="keepexisting-element-dta"></a>KeepExisting 요소(DTA)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  데이터베이스 엔진 튜닝 관리자가 권장 구성을 생성할 때 유지해야 하는 물리적인 디자인 구조(인덱스, 인덱싱된 뷰 또는 분할)를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <KeepExisting>...</KeepExisting>  
```  
  
## <a name="element-characteristics"></a>요소 특징  
  
|특징|설명|  
|--------------------|-----------------|  
|**데이터 형식 및 길이**|**string**, 서버에서 지정한 길이 제한 적용|  
|**허용된 값**|**NONE**<br /> 기존 구조 없음<br /><br /> **ALL**<br /> 모든 기존 구조<br /><br /> **ALIGNED**<br /> 모든 파티션 정렬 구조<br /><br /> **CL_IDX**<br /> 테이블의 모든 클러스터형 인덱스<br /><br /> **IDX**<br /> 테이블의 모든 클러스터형 및 비클러스터형 인덱스<br /><br /> 이 요소에 이러한 값 중 하나만 사용합니다.|  
|**기본값**|없음|  
|**발생 빈도**|(선택 사항) 각 **TuningOptions** 요소에 한 번만 사용할 수 있습니다.|  
  
## <a name="element-relationships"></a>요소 관계  
  
|관계|요소|  
|------------------|--------------|  
|**부모 요소**|[TuningOptions 요소&#40;DTA&#41;](../../tools/dta/tuningoptions-element-dta.md)|  
|**자식 요소**|없음|  
  
## <a name="example"></a>예제  
 이 요소의 사용 예제를 보려면 [단순 XML 입력 파일 예제&#40;DTA&#41;](../../tools/dta/simple-xml-input-file-sample-dta.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [XML 입력 파일 참조&#40;데이터베이스 엔진 튜닝 관리자&#41;](../../tools/dta/xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
