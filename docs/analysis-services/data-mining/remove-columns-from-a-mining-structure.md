---
title: 마이닝 구조에서 열 제거 | Microsoft Docs
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: data-mining
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: bd8691d8ec0cc1546e27e8195e7d0bbc20709f59
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
ms.locfileid: "34015880"
---
# <a name="remove-columns-from-a-mining-structure"></a>마이닝 구조에서 열 제거
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  마이닝 구조를 만든 후 데이터 마이닝 디자이너를 사용하여 해당 구조에서 열을 제거할 수 있습니다. 마이닝 구조 열을 제거하는 이유는 다음과 같을 수 있습니다.  
  
-   마이닝 구조에 한 열의 여러 복사본이 포함되어 있으며 모델에 중복 데이터를 사용하지 않으려고 합니다.  
  
-   데이터를 보호해야 하지만 드릴스루를 사용하도록 설정되었습니다.  
  
-   데이터가 모델링에 사용되지 않으며 데이터를 처리해서는 안 됩니다.  
  
 마이닝 구조에서 열을 삭제하면 데이터 원본 뷰 또는 외부 데이터에서는 열이 변경되지 않고 메타데이터만 삭제됩니다. 그러나 마이닝 구조에서 사용되는 열을 변경하면 해당 구조 및 해당 구조를 기반으로 하는 모델을 모두 다시 처리해야 합니다.  
  
### <a name="to-remove-a-column-from-the-mining-structure"></a>마이닝 구조에서 열을 제거하려면  
  
1.  데이터 마이닝 디자이너에서 **마이닝 구조** 탭을 선택합니다.  
  
2.  마이닝 구조 트리를 확장하여 모든 열을 표시합니다.  
  
3.  삭제할 열을 마우스 오른쪽 단추로 클릭하고 **삭제**를 선택합니다.  
  
4.  **개체 삭제** 대화 상자에서 **확인**을 클릭합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [마이닝 구조 태스크 및 방법](../../analysis-services/data-mining/mining-structure-tasks-and-how-tos.md)  
  
  
