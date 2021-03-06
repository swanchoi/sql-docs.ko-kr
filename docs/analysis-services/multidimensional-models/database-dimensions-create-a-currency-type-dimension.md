---
title: 통화 유형 차원 만들기 | Microsoft Docs
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 73c44e299e448606ce37848ee8f58dd0e15aea76
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
ms.locfileid: "34027090"
---
# <a name="database-dimensions---create-a-currency-type-dimension"></a>데이터베이스 차원-통화 유형 차원 만들기
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
   [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]에서 통화 유형 차원은 재무 보고용 통화 목록을 나타내는 특성이 있는 차원입니다.  
  
 통화 차원을 사용하면 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]에서 통화 변환 기능을 큐브에 추가할 수 있습니다. 통화 변환 기능을 큐브에 추가하려면 비즈니스 인텔리전스 마법사를 사용하여 통화 측정값을 클라이언트 애플리케이션의 로캘에 알맞은 값으로 변환하는 MDX(Multidimensional Expressions) 스크립트 명령을 정의합니다. 이 MDX 스크립트를 만들려면 비즈니스 인텔리전스 마법사에 다음 정보가 필요합니다.  
  
-   원본 통화를 나타내는 통화 차원. 이 차원은 원본 통화 차원입니다.  
  
-   사용할 환율을 나타내는 측정값 그룹  
  
 비즈니스 인텔리전스 마법사는 이 정보를 사용하여 대상 통화를 나타내는 통화 차원인 적합한 대상 통화 차원을 식별하는 통화 변환 프로세스를 디자인합니다. 비즈니스 인텔리전스 마법사는 비즈니스 인텔리전스 솔루션에 필요한 통화 변환 수에 따라 여러 대상 통화 차원을 정의할 수 있습니다. 통화 환산을 정의하는 방법은 [통화 환산&#40;Analysis Services&#41;](../../analysis-services/currency-conversions-analysis-services.md)을 참조하세요.  
  
 차원을 통화 차원으로 식별하려면 차원의 **Type** 속성을 **Currency**로 설정합니다.  
  
## <a name="dimension-structure"></a>차원 구조  
 통화 차원에는 통화 차원의 차원 테이블에 있는 개별 통화를 식별하는 키 특성이 기본적으로 포함되어 있습니다. 키 특성의 값은 원본 통화 차원 및 대상 통화 차원에 따라 다릅니다.  
  
-   특성을 원본 통화 차원의 키 특성으로 식별하려면 특성의 **Type** 속성을 **CurrencySource**로 설정합니다.  
  
-   특성을 대상 통화 차원으로 식별하려면 특성의 **Type** 속성을 **CurrencyDestination**으로 설정합니다.  
  
 보고를 위해 필요한 경우 원본 통화 차원과 대상 통화 차원 모두에 다음 특성이 포함될 수 있습니다.  
  
-   통화 이름 특성  
  
     특성을 통화 이름 특성으로 식별하려면 특성의 **Type** 속성을 **CurrencyName**으로 설정합니다.  
  
-   통화 원본 특성  
  
     특성을 통화 원본 특성으로 식별하려면 특성의 **Type** 속성을 **CurrencySource**로 설정합니다.  
  
-   통화 ISO(International Standards Organization) 코드  
  
     특성을 통화 ISO 코드 특성으로 식별하려면 특성의 **Type** 속성을 **CurrencyIsoCode**로 설정합니다.  
  
 특성 유형에 대한 자세한 내용은 [특성 유형 구성](../../analysis-services/multidimensional-models/attribute-properties-configure-attribute-types.md)을 참조하세요.  
  
## <a name="defining-account-intelligence-with-the-business-intelligence-wizard"></a>비즈니스 인텔리전스 마법사를 사용하여 계정 인텔리전스 정의  
 계정 차원을 정의하여 큐브에 추가한 후에는 비즈니스 인텔리전스 마법사를 사용하여 계정 유형 식별 및 매핑과 같은 계정 인텔리전스 기능을 차원에 추가할 수 있습니다. 자세한 내용은 [차원에 계정 인텔리전스 추가](../../analysis-services/multidimensional-models/bi-wizard-add-account-intelligence-to-a-dimension.md)를 참조하세요.  
  
## <a name="see-also"></a>관련 항목:  
 [특성 및 특성 계층](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md)   
 [비즈니스 인텔리전스 마법사 F1 도움말](http://msdn.microsoft.com/library/155ac80c-63ae-47aa-9e86-9396e3d920eb)   
 [차원 유형](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/database-dimension-properties-types.md)  
  
  
