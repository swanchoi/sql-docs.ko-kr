---
title: Analysis Services 테이블 형식 모델 테이블의 데이터 필터링 | Microsoft Docs
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 9b1fcdda5bd49f8056a6035ec10da8fb52f1c5d1
ms.sourcegitcommit: 8a64c59c5d84150659a015e54f8937673cab87a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2018
ms.locfileid: "53072130"
---
# <a name="filter-data-in-a-table"></a>테이블의 데이터 필터링 
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
  데이터를 가져올 때 필터를 적용하여 테이블에 로드되는 행을 제어할 수 있습니다. 데이터를 가져온 후에는 개별 행을 삭제할 수 없습니다. 그러나 사용자 지정 필터를 적용하여 행이 표시되는 방식을 제어할 수 있습니다. 필터링 조건을 충족하지 않는 행은 숨겨집니다. 하나 이상의 열을 기준으로 필터링할 수 있습니다. 필터는 가산적이므로 현재 필터를 기준으로 필터를 추가할 때마다 데이터의 하위 집합이 줄어듭니다.  
  
> [!NOTE]  
>  필터 미리 보기 창에서는 표시되는 서로 다른 값의 수가 제한됩니다. 제한을 초과하는 경우 메시지가 표시됩니다.  
  
### <a name="to-filter-data-based-on-column-values"></a>열 값을 기준으로 데이터를 필터링하려면  
  
1.  모델 디자이너에서 테이블을 선택한 다음 필터링 기준으로 사용할 열의 머리글에 있는 화살표를 클릭합니다.  
  
2.  자동 필터 메뉴에서 다음 중 하나를 수행합니다.  
  
    -   열 값 목록에서 필터링 기준으로 사용할 값을 하나 이상 선택하거나 선택을 취소한 다음 **확인**을 클릭합니다.  
  
         값의 수가 너무 많은 경우 개별 항목이 목록에 표시되지 않을 수 있습니다. 대신 "표시할 항목이 너무 많음"이라는 메시지가 나타납니다.  
  
    -   열 형식에 따라 **숫자 필터** 또는 **텍스트 필터** 를 클릭한 다음 **같음**과 같은 비교 연산자 명령 중 하나를 클릭하거나 **사용자 지정 필터**를 클릭합니다. **사용자 지정 필터** 대화 상자에서 필터를 만든 다음 **확인**을 클릭합니다.  
  
### <a name="to-clear-a-filter-for-a-column"></a>열에 대한 필터를 지우려면  
  
1.  필터를 지우려는 열의 머리글에 있는 화살표를 클릭합니다.  
  
2.  클릭 **에서 필터 지우기 \<열 이름 >** 합니다.  
  
### <a name="to-clear-all-filters-for-a-table"></a>테이블에 대한 필터를 모두 지우려면  
  
1.  모델 디자이너에서 필터를 지우려는 테이블을 선택합니다.  
  
2.  **열** 메뉴에서 **필터 모두 지우기**를 클릭합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [데이터 필터링 및 정렬](http://msdn.microsoft.com/library/55ebd7a6-2458-4398-911f-fcfeb2413f1b)   
 [큐브 뷰](../../analysis-services/tabular-models/perspectives-ssas-tabular.md)   
 [Roles](../../analysis-services/tabular-models/roles-ssas-tabular.md)  
  
  
