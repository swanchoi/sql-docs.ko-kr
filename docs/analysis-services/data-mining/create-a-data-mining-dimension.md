---
title: 데이터 마이닝 차원 만들기 | Microsoft Docs
ms.date: 05/01/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: data-mining
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 2455ccc283af429cb314aa2e5182f8b2ee58c18e
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
ms.locfileid: "34014210"
---
# <a name="create-a-data-mining-dimension"></a>데이터 마이닝 차원 만들기
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  마이닝 구조가 OLAP 큐브를 기반으로 하는 경우에는 마이닝 모델의 내용을 포함하는 차원을 만들 수 있습니다. 그런 다음 차원을 다시 원본 큐브에 통합할 수 있습니다.  
  
 또한 차원을 찾아보거나 차원을 사용하여 모델 결과를 탐색하거나 MDX를 사용하여 차원을 쿼리할 수 있습니다.  
  
### <a name="to-create-a-data-mining-dimension"></a>데이터 마이닝 차원을 만들려면  
  
1.  [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]의 데이터 마이닝 디자이너에서 **마이닝 구조** 탭이나 **마이닝 모델** 탭을 선택합니다.  
  
2.  **마이닝 모델** 메뉴에서 **데이터 마이닝 차원 만들기**를 선택합니다.  
  
     **데이터 마이닝 차원 만들기** 대화 상자가 열립니다.  
  
3.  **데이터 마이닝 차원 만들기** 대화 상자의 **모델 이름** 목록에서 OLAP 마이닝 모델을 선택합니다.  
  
4.  **차원 이름** 입력란에 새 데이터 마이닝 차원의 이름을 입력합니다.  
  
5.  새 데이터 마이닝 차원을 포함하는 큐브를 만들려면 **큐브 만들기**를 선택합니다. **큐브 만들기**를 선택한 후에는 큐브의 새 이름을 입력할 수 있습니다.  
  
6.  **확인**을 클릭합니다.  
  
     데이터 마이닝 차원이 생성되어 솔루션 탐색기의 **차원** 폴더에 추가됩니다. **큐브 만들기**를 선택한 경우에는 새 큐브도 생성되어 **큐브** 폴더에 추가됩니다.  
  
## <a name="see-also"></a>관련 항목:  
 [마이닝 구조 태스크 및 방법](../../analysis-services/data-mining/mining-structure-tasks-and-how-tos.md)  
  
  
