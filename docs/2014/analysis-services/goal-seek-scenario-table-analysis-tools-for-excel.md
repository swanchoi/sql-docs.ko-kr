---
title: 목표 검색 시나리오 (Excel 용 테이블 분석 도구) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- scenario analysis
- goal seek scenario
ms.assetid: efe50306-cf7c-46b3-9cc4-e7f0b6968b0c
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 85f0c099aba12fe9a4049fe787e248cfe580ff3b
ms.sourcegitcommit: 1ab115a906117966c07d89cc2becb1bf690e8c78
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2018
ms.locfileid: "52400466"
---
# <a name="goal-seek-scenario-table-analysis-tools-for-excel"></a>목표 검색 시나리오(Excel용 테이블 분석 도구)
  ![테이블 분석 도구의 목표 검색 단추](media/tat-goalseek.gif "테이블 분석 도구의 목표 검색 단추")  
  
 **목표 검색** 시나리오 도구는 보완 합니다 [경우에 어떻게](what-if-scenario-table-analysis-tools-for-excel.md) 시나리오 도구. **What-if** 도구를 알려는 변경의 영향을 반면 합니다 **목표 검색** 도구 원하는 결과 얻기 위해 변경 해야 하는 기본 요소를 알려 줍니다.  
  
 예를 들어, 고객 만족도를 높일 것이 목표인 가정해 보겠습니다. 사용할 수 있습니다 **목표 검색** 분석을 판단 하는 요소는 가능성이 높은 고객 만족도 높이고 이러한 변경이 비용 효율적인 지 여부를 결정 합니다.  
  
 도구에서는 분석을 완료하면 원본 데이터 테이블에 두 개의 열을 새로 만듭니다. 이러한 열에 표시 된 *가능성* 대상된 결과 얻을 수 있는 하 고 있는 경우 권장 되는 변경 합니다.  
  
 이 도구에서는 데이터 집합을 분석하고 전체 집합에 대한 예측을 수행할 수도 있고 분석을 만든 다음 시나리오를 한 번에 하나씩 테스트할 수도 있습니다.  
  
## <a name="using-the-goal-seek-scenario-tool"></a>목표 검색 시나리오 도구 사용  
  
1.  Excel 테이블을 엽니다.  
  
2.  클릭 **시나리오**, 선택한 **목표값 찾기**합니다.  
  
3.  **시나리오 분석: 목표 검색** 대화 상자에서 대상이 포함 된 열 목록에서 값입니다.  
  
4.  달성 하려는 값을 지정 합니다.  
  
     열 목표에 연속 숫자 값이 들어 있으면 원하는 값 증감분을 지정할 수도 있습니다. 예를 들어, 선택할 수 있습니다 **Sales** 열으로 대상이 120% 증가로 임을 지정 합니다.  
  
     목표를 값 범위로 지정하고 하한과 상한을 입력할 수도 있습니다.  
  
5.  변경할 값이 들어 있는 열을 지정합니다. 즉 원하는 결과를 얻기 위해 조정할 열을 선택합니다.  
  
6.  필요에 따라 클릭 **분석에 사용할 열 선택**, 유용한 정보를 포함 하는 열을 선택 합니다. 분석에 도움이 되지 않는 열은 선택 취소합니다.  
  
    > [!NOTE]  
    >  목표 또는 변경을 위해 사용할 열의 선택은 취소하지 마십시오. 이러한 열은 필수 사항입니다.  
  
7.  전체 테이블에 대해 예측할지 선택한 행에 대해서만 예측할지 지정합니다.  
  
8.  선택한 경우에 **전체 테이블** 옵션, 도구는 두 개의 새 열에서 원본 테이블에 예측 값을 추가 합니다.  
  
9. 옵션을 선택한 경우 **이 행**, 분석 결과를 검토를 위해 대화 상자에 출력 됩니다. 이 대화 상자는 여러 가지 값과 목표를 계속 시도해 볼 수 있도록 열린 상태로 유지됩니다.  
  
### <a name="requirements"></a>요구 사항  
 이 도구에서는 숫자 값 또는 불연속 값을 처리할 수 있는 Microsoft 로지스틱 회귀 알고리즘을 사용합니다.  
  
 예측을 여러 번 실행하고 나중에 여러 열을 선택할 수 있지만 각 목표 및 변경의 조합은 별도로 계산해야 합니다.  
  
 유용한 정보가 있는 열을 분석에 사용하도록 선택하면 더 좋은 결과를 얻을 수 있습니다. 하지만 포함되는 열이 너무 적으면 결과를 얻기 어려울 수 있습니다.  
  
 한 번에 하나씩 예측을 만드는 경우 원하는 결과가 이미 들어 있는 행을 선택하지 않아야 합니다. 그렇지 않으면 오류가 발생할 수 있습니다. 즉 목표 검색의 목적이 자전거 구매를 촉진하는 요인을 파악하는 것이라면 자전거를 구매하지 않은 고객만 포함해야 합니다.  
  
## <a name="understanding-the-results-of-goal-seek-analysis"></a>목표 검색 분석 결과 이해  
 목표 검색 시나리오를 만들 때 도구에서는 다음과 같은 3가지 작업을 수행합니다.  
  
-   테이블의 데이터에 대한 주요 요소를 저장하는 데이터 마이닝 구조 만들기  
  
-   데이터 기반의 로지스틱 회귀 마이닝 모델 만들기  
  
-   지정한 각 값에 대한 예측 만들기  
  
 목표 검색 시나리오를 한 번에 하나씩 테스트하는 경우 결과를 대화형으로 확인할 수 있습니다. 이 만드는 것과 같습니다는 *단일 예측 쿼리*합니다.  
  
 도구에서 보고서를 **결과** 원하는 목표를 달성 하는 시나리오 찾기에 성공 했는지 여부가 상자의 대화 상자 창. 성공적인 솔루션을 찾은 경우에는 필요한 변경에 대한 권장 사항도 생성됩니다. 예를 들어 합니다 **목표 검색** 도구를 확인할 수 있습니다는 통근 거리가 5 마일 이내 되도록 합니다.  
  
 예제 결과:  
  
 **구입에 대 한 목표 검색 솔루션을 찾았습니다.**  
  
 **가장 가까운 일치 가져온 ' 2-5 마일 '로 '통근 거리'를 변경 하 여 합니다.**  
  
 이 결과는 데이터 테이블의 기존 행을 기반으로 합니다. 이는 특정 고객에 대해 다른 모든 요소는 그대로 두고 통근 거리만 2-5마일로 줄이는 경우 고객이 자전거를 구매할 가능성이 다소 높아짐을 의미합니다.  
  
 지정 하 여 Excel 테이블에서 모든 행에 대 한 목표 검색 예측을 만들면 **전체 테이블**, thetool 원래 데이터 테이블에 새 열 두 개를 만듭니다. 테이블에 추가된 첫 번째 열은 목표 충족이 가능함을 나타내는 녹색 원 내의 체크 표시를 포함하거나, 목표 달성이 가능하도록 변경할 수 없음을 나타내는 빨강 원 내의 X표를 포함합니다.  
  
 두 번째 열에는 권장 변경 사항이 포함됩니다.  
  
> [!NOTE]  
>  권장 및 성공에 대한 신뢰도 수준은 알고리즘으로 미리 결정되며 변경할 수 없습니다.  
  
## <a name="related-tools"></a>관련 도구  
 고급 데이터 마이닝 기능을 제공하는 별도의 추가 기능인 Excel용 데이터 마이닝 클라이언트에는 행위를 예측하는 데이터 마이닝 모델을 만들기 위한 마법사가 포함되어 있습니다. 자세한 내용은 [데이터 마이닝 모델을 만드는](creating-a-data-mining-model.md)합니다.  
  
 사용 되는 알고리즘에 대 한 자세한 합니다 **목표값 찾기** 시나리오 도구에서 "Microsoft 로지스틱 회귀 알고리즘" 항목을 참조 하십시오 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Onl 온라인 설명서.  
  
## <a name="see-also"></a>관련 항목:  
 [Excel용 테이블 분석 도구](table-analysis-tools-for-excel.md)  
  
  
