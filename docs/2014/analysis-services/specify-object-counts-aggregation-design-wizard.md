---
title: 개체 수 지정 (집계 디자인 마법사) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.calculatingobjectcounts.f1
ms.assetid: 305d9d79-d1ab-4704-a7b5-3283842b3996
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 3711c21f6d69a7b5fd93456811e4bd3874116774
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48160883"
---
# <a name="specify-object-counts-aggregation-design-wizard"></a>개체 수 지정(집계 디자인 마법사)
  **개체 수 지정** 페이지를 사용하여 큐브의 개체 수를 자동으로 계산하거나 예상 개수를 직접 입력할 수 있습니다. 집계 디자인 마법사는 개체 수를 사용하여 스토리지 요구 사항을 예상합니다.  
  
## <a name="options"></a>변수  
 **큐브 개체**  
 큐브의 차원 및 특성을 표시합니다. 되지 않은 특성에만 해당 `AggregationUsage` 속성으로 설정 `None` 에 **집계 사용 검토** 개수를 지정 하는 특성에만 해당 되므로 마법사의 페이지 표시 됩니다.  
  
 **예상된 개수**  
 측정값 그룹의 예상 행 수와 데이터베이스 차원의 예상 특성 멤버 수를 표시합니다. 예상 개수로 사용할 값을 입력하거나 예상 개수 값을 계산할 수 있습니다. 개수 값을 계산 하려면 입력 `0` 필드를 클릭 한 다음 **개수**합니다. 이미 수가 표시된 필드는 업데이트되지 않습니다.  
  
 **파티션 수**  
 (옵션) 측정값 그룹의 예상 행 수와 파티션의 예상 특성 멤버 수를 입력합니다.  
  
 **개수**  
 모든 빈 필드에 대해 **예상 개수** 열의 값을 계산하고 다시 채웁니다. 이미 수가 표시된 필드는 업데이트되지 않습니다.  
  
## <a name="see-also"></a>관련 항목  
 [집계 디자인 마법사 F1 도움말](aggregation-design-wizard-f1-help.md)   
 [Analysis Services 마법사 &#40;다차원 데이터&#41;](analysis-services-wizards-multidimensional-data.md)  
  
  
