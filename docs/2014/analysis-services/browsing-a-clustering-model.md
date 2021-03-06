---
title: 클러스터링 모델 찾아보기 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- clustering [data mining]
- mining model, clustering
ms.assetid: 7f3f0949-d791-403a-88e2-54cb1a803dae
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 1a0fd00201f782bba8b06ddde8753a86aeb89046
ms.sourcegitcommit: 2429fbcdb751211313bd655a4825ffb33354bda3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "52535718"
---
# <a name="browsing-a-clustering-model"></a>클러스터링 모델 찾아보기
  사용 하 여 클러스터링 모델을 열면 **찾아보기**의 클러스터링 뷰어와 비슷한 대화형 뷰어에서 모델이 표시 됩니다 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]합니다. 이 뷰어는 만들어진 클러스터를 탐색하고 클러스터의 특징을 이해하는 데 도움이 됩니다. 또한 개별 세그먼트를 다른 세그먼트 또는 모집단과 비교하고 대조할 수도 있습니다.  
  
##  <a name="BKMK_Tabs"></a> 모델 탐색  
 합니다 **찾아보기** 창에는 클러스터링 모델을 이해 하 고 기본 데이터 그룹의 특성을 탐색 하는 데 다음 도구가 포함 됩니다.  
  
-   [클러스터 다이어그램](#BKMK_ClusterDiagram)  
  
-   [클러스터 프로필](#BKMK_ClusterProfiles)  
  
-   [클러스터 특징](#BKMK_ClusterCharacteristics)  
  
-   [클러스터 판별](#BKMK_ClusterDiscrimination)  
  
 클러스터링 모델을 테스트 하려면 샘플 데이터를 사용 하 여 샘플 데이터 통합 문서의 학습 탭의 사용 하 여 클러스터링 모델을 빌드합니다 [클러스터 마법사 &#40;Excel 용 데이터 마이닝 추가 기능&#41; ](cluster-wizard-data-mining-add-ins-for-excel.md) 하 고 모든 기본값 .  
  
###  <a name="BKMK_ClusterDiagram"></a> 클러스터 다이어그램  
 합니다 **클러스터 다이어그램** 탭은 마이닝 모델에 있는 모든 클러스터를 표시 합니다. 데이터 집합에서 검색된 그룹 수와 이러한 그룹이 서로 얼마나 가깝거나 멀게 떨어져 있는지를 확인할 수 있습니다.  
  
##### <a name="explore-the-cluster-diagram"></a>클러스터 다이어그램 탐색  
  
1.  다이어그램에서 클러스터 1을 클릭합니다.  
  
     모든 클러스터를 연결하는 회색 선 중에서 선택한 클러스터로 이어지는 선이 변경되어 밝은 파란색으로 강조 표시됩니다.  
  
     ![클러스터 다이어그램 소개](media/dm13-cluster-diagram-intro.gif "클러스터 다이어그램 소개")  
  
     두 클러스터를 연결하는 선의 음영은 클러스터의 유사성 정도를 나타냅니다. 음영이 옅거나 없으면 두 클러스터가 그다지 유사하지 않은 것입니다. 선이 짙을수록 두 클러스터 간의 유사성이 더욱 강하다는 것을 의미합니다.  
  
2.  슬라이더를 클릭하여 클러스터 다이어그램의 왼쪽으로 끌어 뷰어에 표시되는 선의 개수를 조정합니다.  
  
     슬라이더를 아래로 끌면 클러스터 간의 가장 강력한 링크만 표시되므로 관련된 그룹에 집중하는 데 도움이 됩니다.  
  
3.  알림 합니다 **음영 변수** 컨트롤의 오른쪽 위 모서리에는 **클러스터 다이어그램** 창입니다.  
  
     기본 설정은 **채우기**합니다. 이는 클러스터가 짙을수록 지지도가 커짐을 의미합니다.  
  
4.  클러스터 위에 커서를 놓습니다.  
  
     해당 클러스터의 모집단이 포함된 도구 설명이 표시됩니다.  
  
5.  이제 클릭를 **음영 변수** 드롭다운 나열 하 고 선택 합니다 **Age** 변수입니다. 이렇게 하면 값의 목록에 표시 됩니다는 **상태** 입력란입니다.  
  
     이 모델의 입력으로 사용되는 Age 열에는 연속 숫자 값이 포함되어 있지만 클러스터링 목적을 위해 알고리즘에서 항상 숫자를 불연속화합니다. 여기 bin 또는 같은 알고리즘 만든 그룹을 볼 수 있습니다 "매우 낮음 (\<= 27)" 및 "매우 높은 (> = 63)".  
  
6.  합니다 **상태** 드롭다운 목록, 선택 **매우 높은** 다이어그램은 어떻게 변경 되는지 확인 하 고 있습니다.  
  
     음영 변수를 변경하여 이 대상 연령 그룹이 많이 포함된 클러스터와 이 연령 그룹의 고객이 매우 적게 포함된 클러스터를 한눈에 확인할 수 있습니다.  
  
     ![보존 기간을 표시 하도록 클러스터 다이어그램 수정](media/dm13-cluster-diagramshadebyage.gif "보존 기간을 표시 하도록 클러스터 다이어그램 수정")  
  
     음영이 짙을수록 해당 클러스터의 대상 특성 및 값 분포의 모집단이 커집니다.  
  
7.  회색으로 표시 하는 클러스터를 찾습니다 일 경우에는 **음영 변수** Age로 설정 된 > 65.  
  
     클러스터 위로 마우스를 가져갑니다.  
  
     도구 설명에 표시된 값이 이제 이 클러스터에서 65세가 넘는 고객의 모집단을 보여 줍니다.  
  
8.  클러스터를 마우스 오른쪽 단추로 클릭 **클러스터 이름 바꾸기**합니다. 와 같은 설명이 포함 된 새 이름을 입력 **Over 65**합니다. 새 이름이 모델과 함께 서버에 저장되고 다른 클러스터링 뷰에서 클러스터를 식별하는 데 사용될 수 있습니다.  
  
 [맨 위로 이동](#BKMK_Tabs)  
  
###  <a name="BKMK_ClusterProfiles"></a> 클러스터 프로필  
 합니다 **클러스터 프로필** 탭에서는 한 눈에 모든 클러스터의 구성을 한눈에 비교할 수 있습니다. 모델에 익숙해지면 이곳에서 시작하는 것이 좋습니다. 이 뷰는 특정 클러스터를 탐색하다가 관련 클러스터를 찾아야 한다고 이후에 결정하는 경우에도 유용합니다.  
  
 **클러스터 프로필** 또한 클러스터는 서로 다른 방법의 개요를 제공 합니다. 따라서 이 뷰를 사용하여 각 클러스터에 설명이 포함된 이름을 간편하게 지정할 수 있습니다.  
  
##### <a name="explore-the-cluster-profiles"></a>클러스터 프로필 탐색  
  
1.  , occupation 셀을 클릭 합니다 **상태** Occupation에 대 한 모든 값의 목록을 보려면 열입니다.  
  
2.  이제 클러스터 프로필에서 Occupation 위로 커서를 이동합니다.  
  
     도구 설명에 해당 클러스터의 직업 분포가 표시됩니다.  
  
     ![도구 설명 또는 범례에서 자세한 값 보기](media/dm13-cluster-profile-age-tooltip.gif "범례 또는 도구 설명에 자세한 값 보기")  
  
     일부 클러스터 (예: 있는 그래픽), 직업은 알림 완료 되며 특정 직업 레이블 바뀝니다 **다른**합니다.  
  
     히스토그램의 많은 작은 막대를 구별하기가 어려울 수 있기 때문에 이것은 의도적인 것입니다. 기본적으로 가장 중요 한 막대만 유지 되 고 나머지 막대는 회색으로 함께 그룹화 됩니다 **다른** 통 합니다.  
  
     히스토그램에 표시 되는 막대의 수를 변경 하려면 옵션을 사용 하 여 **히스토그램 막대**합니다.  
  
3.  합니다 **Age** 열 다른 다르게 보입니다. Age를 나타내는 데 사용되는 차트에서 다이아몬드를 클릭합니다.  
  
     Age 열에는 원래 연속 숫자만 포함되어 있었습니다. 클러스터링 알고리즘은 불연속 값을 필요로 하므로 Age 열의 숫자 값을 값의 분포에 따라 제한된 수의 연령 그룹으로 나누었습니다.  
  
4.  클러스터 프로필에서 다이아몬드 차트 중 하나를 클릭합니다.  
  
     이러한 다이아몬드 차트는 원본 데이터가 연속 숫자 값을 사용하는 경우에만 표시됩니다. 다이아몬드 차트는 각 클러스터에서 해당 값의 평균 및 표준 편차를 비롯한 몇 가지 유용한 기술 통계를 제공합니다.  
  
    -   다이아몬드 차트의 선은 특성 값의 범위를 나타냅니다. 값에도 표시 됩니다는 **상태** 왼쪽에 있는 열을 **프로필** 차트입니다.  
  
    -   다이아몬드의 중심은 노드의 평균에 배치됩니다.  
  
    -   다이아몬드의 너비는 해당 노드에서 특성의 분산을 나타냅니다. 따라서 다이아몬드가 얇을수록 노드에서 더욱 정확한 예측을 도출할 수 있음을 나타냅니다.  
  
5.  그래프에서 더 많은 공간을 확보 하려면 선택한 당장 볼 필요가 클러스터를 마우스 오른쪽 단추로 클릭 **Hide Column**합니다. 이 모델에서 삭제 되지는 않습니다, 그리고만 열을 일시적으로 축소 합니다.  
  
     숨긴 클러스터를 보려면 수 클릭 하 고 열 가장자리를 끌어 하거나 목록에서 클러스터 이름을 선택 **더 많은 클러스터**합니다.  
  
6.  Bike Buyer를 찾을 때까지 특성 목록을 아래로 스크롤한 다음 Yes 값의 비율이 가장 높은 클러스터를 찾습니다.  
  
     이름 바꾸기, 선택 하려는 클러스터에 대 한 열 머리글을 마우스 오른쪽 단추로 클릭 **클러스터 이름 바꾸기**, 유형과 **자전거 구매자**합니다.  
  
     새 클러스터 이름이 모든 뷰에서 유지되고 서버에서는 모델을 다시 처리할 때까지 유지됩니다.  
  
     ![차트를 보다 쉽게 사용 하 여 클러스터의 이름을 바꿀](media/dm13-cluster-rename.gif "차트를 쉽게 사용할 수 있도록 클러스터 이름 바꾸기")  
  
 **팁**  
  
-   해당 클러스터에 대한 중요도 순으로 특성을 정렬하려면 열 제목을 클릭합니다.  
  
-   뷰어에서 열을 다시 정렬하려면 열을 끕니다.  
  
-   자세한 통계를 보려면 프로필 차트에서 아무 셀 이나 클릭 합니다 **마이닝 범례**합니다.  
  
-   선택한 모든 셀을 마우스 오른쪽 단추로 클릭 **드릴스루 모델 열** Excel에서 새 워크시트에 기본 데이터를 출력 합니다.  
  
-   제목 선택한 클러스터의 열을 마우스 오른쪽 단추로 클릭 **구조 데이터로 드릴스루** 모델에 포함 되지 않은 클러스터 구성원에 대 한 자세한 정보를 얻을 수 있습니다.  
  
     예를 들어, 고객 프로 파일링 하는 경우에 기본 데이터 (마이닝 구조)의 연락처 정보를 유지 하지만 하지 분석에 유용 하지 않기 때문에 모델에 포함 수 있습니다. 그러나 고객이 클러스터에 할당된 후 드릴스루를 사용하여 세부 데이터를 볼 수 있습니다.  
  
 [맨 위로 이동](#BKMK_Tabs)  
  
###  <a name="BKMK_ClusterCharacteristics"></a> 클러스터 특징  
 클러스터 특징 뷰를 사용하면 단일 클러스터를 실제로 탐색하여 이 데이터 그룹의 가장 큰 특징을 결정하는 특성을 찾을 수 있습니다.  
  
##### <a name="explore-the-cluster-characteristics"></a>클러스터 특징 탐색  
  
1.  선택 된 **Over 65** 에서 클러스터를 **클러스터** 목록입니다.  
  
     클러스터를 선택한 후 해당 클러스터를 구성하는 특징을 자세히 확인할 수 있습니다.  
  
     클러스터에 포함된 특성은 **변수** 열에 나열되어 있으며 나열된 특성의 상태는 **값** 열에 나열되어 있습니다.  
  
     특성 상태에 색이 지정 된 막대로 표시 되는이 클러스터에서 해당 확률에 따라 중요도 순서로 나열 됩니다는 **확률** 열입니다.  
  
     ![클러스터링 모델의 특징](media/dm13-cluster-characteristics.gif "클러스터링 모델의 특징")  
  
2.  클릭 합니다 **변수** 특성을 정렬할 열입니다.  
  
     정렬 변수를 변경하여 소득이나 자동차 소유와 같은 변수의 값이 그룹에서 어떻게 분포되어 있는지를 보다 쉽게 확인할 수 있습니다.  
  
3.  클릭 **Excel로 복사**합니다.  
  
     선택한 클러스터의 특징이 포함된 새 워크시트가 통합 문서에 추가됩니다.  
  
4.  이제 목록에서 다른 클러스터를 선택할 **자전거 구매자**합니다.  
  
5.  클릭 **Excel로 복사**합니다.  
  
     새 클러스터 특징 차트가 자체 워크시트에 추가됩니다. 다음 단계에서 수행 하는 이러한 비교할 수 있도록 다른 프로필과 동일한 워크시트로 이동할 수 있습니다.  
  
 **팁**  
  
-   Over 65 클러스터에 있는 고객의 주요 특징은 제품을 구입 하지 않는다는 것을 참고! 그 이유를 알고 싶은 경우 클러스터를 탐색하고 그룹을 비교하거나, 의사 결정 트리 모델 또는 Naïve Bayes 모델과 같이 원인과 결과를 탐색하는 데 유용한 알고리즘을 사용하여 관련 모델을 만들 수도 있습니다.  
  
-   이 클러스터(또는 모든 클러스터)에 대한 특성 및 확률의 전체 목록을 얻으려면 쿼리를 만들면 됩니다. 클러스터링 모델에 대 한 쿼리의 예제를 참조 하세요 [클러스터링 모델 쿼리 예제](data-mining/clustering-model-query-examples.md)합니다.  
  
 [맨 위로 이동](#BKMK_Tabs)  
  
###  <a name="BKMK_ClusterDiscrimination"></a> 클러스터 판별  
 사용 된 **클러스터 판별** 두 클러스터 또는 클러스터와 다른 경우 데이터 집합의 모든 특성을 비교 하는 탭 합니다.  
  
 이 뷰어의 기능을 강조 하기 위해 비교 하겠습니다 그에 따라 만든 Excel의 side-by-side-테이블에는 **클러스터 특징** 보기.  
  
##### <a name="explore-cluster-discrimination"></a>클러스터 판별 탐색  
  
1.  **클러스터 1** 및 **클러스터 2** 목록을 사용하여 비교할 클러스터를 선택합니다.  
  
    -   클러스터 1에서 Over 65를 선택합니다.  
  
    -   클러스터 2에서 Bike Buyers를 선택합니다.  
  
     두 클러스터에 대한 비교가 다음 그래픽과 유사하게 표시됩니다.  
  
     ![클러스터 모델의 비교](media/dm13-cluster-compareclusters.gif "모델에서 클러스터 비교")  
  
     내부적으로 있는지 확인 합니다 **클러스터 판별** 뷰어 복잡 한 쿼리를 보다 쉽게 비교할 수 있도록 두 그룹을 구별 가장 중요 한 특성을 추출할 데이터 마이닝 서버에 보냅니다 두 고객 집합입니다.  
  
2.  중 하나를 클릭 합니다 **유사성...**  열입니다.  
  
     특성 및 값 목록의 오른쪽에 있는 막대가 선택한 클러스터의 특징으로 가장 중요한 기능이나 값을 보여 줍니다.  
  
3.  이제 Excel에서 목록을 비교합니다.  
  
     ![연결 모델에 대 한 종속성 네트워크 그래프](media/dm13-comparing-profiles-in-excel.gif "연결 모델에 대 한 종속성 네트워크 그래프")  
  
     뷰어에서 이미지를 작성하는 데 사용된 기본 통계가 Excel에 테이블로 저장되기 때문에 실제 확률 값을 필터링 및 정렬하고 볼 수 있습니다.  
  
     Excel을 사용하는 것 외에도 데이터 요소를 볼 수 있을 뿐 아니라 그래프를 광범위하게 수정하고 개선할 수도 있는 Visio용 클러스터 뷰어를 사용해 보는 것이 좋습니다. 자세한 내용은 [클러스터 다이어그램 연습 &#40;데이터 마이닝 추가 기능&#41;](cluster-diagram-walkthrough-data-mining-add-ins.md)합니다.  
  
 **팁**  
  
 고객 그룹에 대 한 일부 정보를 받은 후 사용해 합니다 [What-If 시나리오 &#40;Excel 용 테이블 분석 도구&#41; ](what-if-scenario-table-analysis-tools-for-excel.md) 하거나 [목표 검색 시나리오 &#40;Excel 용 테이블 분석 도구&#41; ](goal-seek-scenario-table-analysis-tools-for-excel.md) 도구에서 결과 영향을 변경할 수 있는 모델의 요인을 살펴보십시오.  
  
## <a name="see-also"></a>관련 항목  
 [Excel에서 모델 찾아보기 &#40;SQL Server 데이터 마이닝 추가 기능&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md)   
 [클러스터 마법사 &#40;Excel 용 데이터 마이닝 추가 기능&#41;](cluster-wizard-data-mining-add-ins-for-excel.md)  
  
  
