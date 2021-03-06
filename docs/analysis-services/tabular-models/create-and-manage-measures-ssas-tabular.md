---
title: Analysis Services 테이블 형식 모델에서 측정값 만들기 및 관리 | Microsoft Docs
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 1c3794d9ed2927cf86b9aada08588f71b3a55b8a
ms.sourcegitcommit: 8a64c59c5d84150659a015e54f8937673cab87a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2018
ms.locfileid: "53072610"
---
# <a name="create-and-manage-measures"></a>측정값 만들기 및 관리 
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
  측정값은 보고서나 Excel 피벗 테이블 또는 피벗 차트에 사용하기 위해 만드는 수식입니다. COUNT 또는 SUM과 같은 표준 집계 함수를 기반으로 측정값을 만들거나 DAX를 사용하여 고유한 수식을 정의할 수 있습니다. 이 항목의에서 태스크에서는 테이블의 측정값 표를 사용 하 여 측정값을 만들고 방법에 설명 합니다.  
  
## <a name="tasks"></a>태스크  
 을 만들고 측정값을 관리 하는 테이블의 측정값 표를 사용 합니다. 모델 디자이너의 데이터 뷰에서만 테이블에 대한 측정값 표를 볼 수 있습니다. 다이어그램 뷰에서는 측정값을 만들거나 측정값 표를 볼 수 없지만 기존 측정값을 볼 수는 있습니다. 테이블의 측정값 표를 보려면 **테이블** 메뉴를 클릭한 다음 **측정값 표 표시**를 클릭합니다.  
  
###  <a name="bkmk_create_stand"></a> 표준 집계 수식을 사용하여 측정값을 만들려면  
  
-   측정값을 만들 열을 클릭한 후 **열** 메뉴를 클릭하고 **자동 합계**를 가리킨 다음 집계 유형을 클릭합니다.  
  
     기본 이름 뒤에 측정값 표의 해당 열 바로 아래에 있는 첫 번째 셀의 수식이 추가되어 측정값이 자동으로 만들어집니다.  
  
###  <a name="bkmk_create_custom"></a> 사용자 지정 수식을 사용하여 측정값을 만들려면  
  
-   측정값 표에서 측정값을 만들려는 열 아래의 셀을 클릭한 다음 수식 표시줄에 이름과 콜론(:), 등호(=) 및 수식을 차례로 입력합니다. Enter 키를 눌러 수식을 적용합니다.  
  
###  <a name="bkmk_edit"></a> 측정값을 편집하려면  
  
-   측정값 표에서 측정값을 클릭한 다음 **속성** 창에서 다른 속성 값을 입력하거나 선택합니다.  
  
###  <a name="bkmk_rename"></a> 측정값의 이름을 바꾸려면  
  
-   측정값 표에서 측정값을 클릭한 다음 **속성** 창의 **측정값 이름**에 새 이름을 입력하고 Enter 키를 누릅니다.  
  
     수식 입력줄에서 측정값 이름을 바꿀 수도 있습니다. 수식 앞에 측정값 이름이 표시되고 그 뒤에 콜론이 표시됩니다.  
  
###  <a name="bkmk_delete"></a> 측정값을 삭제하려면  
  
-   측정값 표에서 측정값을 마우스 오른쪽 단추로 클릭한 다음 **삭제**를 클릭합니다.  
  
## <a name="see-also"></a>관련 항목  
 [측정값 그룹](../../analysis-services/tabular-models/measures-ssas-tabular.md)   
 [Kpi](../../analysis-services/tabular-models/kpis-ssas-tabular.md)   
 [계산된 열](../../analysis-services/tabular-models/ssas-calculated-columns.md)  
  
  
