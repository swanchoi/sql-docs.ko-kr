---
title: 유사 항목 그룹화 변환 편집기 (고급 탭) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.advanced.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: dd820d75-b8a7-4515-aea4-3553ba5b442e
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: 074a3d460a04180a5cfce1406b546fb6a3a3986a
ms.sourcegitcommit: 5a8678bf85f65be590676745a7fe4fcbcc47e83d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58389028"
---
# <a name="fuzzy-grouping-transformation-editor-advanced-tab"></a>유사 항목 그룹화 변환 편집기(고급 탭)
  **유사 항목 그룹화 변환 편집기** 대화 상자의 **고급** 탭을 사용하여 입/출력 열을 지정하고, 유사성 임계값을 설정하고, 구분 기호를 정의할 수 있습니다.  
  
> [!NOTE]  
>  `Exhaustive` 및 `MaxMemoryUsage` 유사 항목 그룹화 변환의 속성을 사용할 수 없습니다는 **유사 항목 그룹화 변환 편집기**를 사용 하 여 설정할 수 있습니다는 **고급 편집기**. 이러한 속성에 대한 자세한 내용은 [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md)의 유사 항목 그룹화 변환 섹션을 참조하십시오.  
  
 유사 항목 그룹화 변환에 대한 자세한 내용은 [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md)을 참조하십시오.  
  
## <a name="options"></a>변수  
 **입력 키 열 이름**  
 각 입력 행에 대한 고유 식별자를 포함하는 출력 열의 이름을 지정합니다. `_key_in` 열에는 각 행을 고유하게 식별하는 값이 있습니다.  
  
 **출력 키 열 이름**  
 중복 행 그룹의 정식 행에 대한 고유 식별자를 포함하는 출력 열의 이름을 지정합니다. `_key_out` 열은 정식 데이터 행의 `_key_in` 값에 해당합니다.  
  
 **유사성 점수 열 이름**  
 유사성 점수를 포함하는 열의 이름을 지정합니다. 유사성 점수는 입력 행과 정식 행의 유사성을 나타내는 0과 1 사이의 값입니다. 정식 행과 더 비슷하게 일치할수록 점수가 1에 가까워집니다.  
  
 **유사성 임계값**  
 슬라이더를 사용하여 유사성 임계값을 설정합니다. 임계값이 1에 가까울수록 두 행이 보다 유사하여 중복으로 처리됩니다. 임계값을 높이면 고려할 레코드 수가 감소하기 때문에 비교 속도를 향상시킬 수 있습니다.  
  
 **토큰 구분 기호**  
 변환에서 데이터 토큰화에 사용할 수 있는 기본 구분 기호 집합을 제공하지만 필요에 따라 목록을 편집하여 구분 기호를 추가 또는 제거할 수 있습니다.  
  
## <a name="see-also"></a>관련 항목  
 [Integration Services 오류 및 메시지 참조](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [유사 항목 그룹화 변환을 사용하여 유사한 데이터 행 식별](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
