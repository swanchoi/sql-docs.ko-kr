---
title: 클러스터 다이어그램 연습 (데이터 마이닝 추가 기능) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Visio shapes, cluster
- diagram, cluster
- shapes, data mining
- shapes, cluster
- data mining layout toolbar
ms.assetid: 761bef6a-37d4-4b19-944e-f2aadc75a242
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: ee4a7a09471078753589463c058ba5ea2e39c4d2
ms.sourcegitcommit: 1ab115a906117966c07d89cc2becb1bf690e8c78
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2018
ms.locfileid: "52420008"
---
# <a name="cluster-diagram-walkthrough-data-mining-add-ins"></a>클러스터 다이어그램 연습(데이터 마이닝 추가 기능)
  클러스터링 모델을 만든 후 Visio를 사용 하 여 가져올 수 있습니다 합니다 **클러스터** 셰이프 및 사용자 지정 레이아웃을 개선 하 고 계속 합니다. 합니다 **Visio 용 데이터 마이닝 셰이프** 데이터 마이닝 다이어그램을 사용 하 여 작업에 대 한 다음 사용자 지정 컨트롤을 포함 합니다.  
  
-   클러스터 다이어그램의 렌더링 컨트롤  
  
     이러한 옵션의 일부인 합니다 **클러스터 마법사** Visio 작업 영역에 셰이프를 끌어서 놓을 때 시작 되는 합니다.  
  
-   **Data Mining Layout** 도구 모음  
  
     이러한 옵션은 데이터 마이닝 셰이프와 상호 작용하는 데 도움이 되도록 Visio 작업 영역에 추가되며, 사용하고 있는 데이터 마이닝 모델의 유형에 따라 다릅니다.  
  
## <a name="build-a-cluster-diagram"></a>클러스터 다이어그램 작성  
 이 연습에서는 Visio에서 클러스터링 다이어그램을 작성하고 사용자 지정하는 방법을 보여 줍니다.  
  
 이 연습을 실행하려면 사용할 수 있는 클러스터링 모델이 이미 있어야 합니다. 모델이 없는 경우 사용 합니다 [클러스터 마법사 &#40;Excel 용 데이터 마이닝 추가 기능&#41; ](cluster-wizard-data-mining-add-ins-for-excel.md) 마법사 모든 기본값을 사용 하 여 샘플 통합 문서의 학습 데이터 집합을 사용 하 여 모델을 만듭니다.  
  
#### <a name="use-the-cluster-visio-shape-wizard"></a>클러스터 Visio 셰이프 마법사 사용  
  
1.  표시 되지 않으면 **Microsoft 데이터 마이닝 셰이프** 에 **셰이프** 목록에서 클릭 **추가 셰이프**를 선택 **스텐실 열기**, 연는 기본 설치 위치에서 템플릿입니다.  
  
     \<드라이브 >: files\microsoft SQL Server 2012 DM Add-ins  
  
2.  끌기 합니다 **클러스터** 셰이프를 페이지로 합니다.  
  
3.  시작 페이지에는 **클러스터 Visio 셰이프 마법사**, 클릭 **다음**합니다.  
  
4.  에 **데이터 원본을 선택** 페이지를 **클러스터 마법사**에 대 한 연결을 선택는 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] 시각화 하려는 데이터 마이닝 모델을 포함 하는 서버입니다.  
  
5.  적절 한 마이닝 모델을 선택 하 고 클릭 **다음**합니다.  
  
     를 클러스터링 모델을 선택 했는지 확인 하려면에서 설명을 검토 합니다 **속성** 창입니다.  
  
6.  연결에 성공 하면 페이지에서 **클러스터 다이어그램 옵션**, Visio 프레젠테이션에 포함할 클러스터 다이어그램의 유형을 결정 합니다.  
  
     **클러스터 셰이프만 표시**  
     이 옵션은 각 클러스터가 사각형이나 선택한 다른 셰이프로 표시되는 간단한 클러스터 다이어그램을 만듭니다.  
  
     **특징 차트로 클러스터 표시**  
     이 옵션은 위와 동일한 차트를 만들지만 셰이프 내에 클러스터의 특징을 설명하는 히스토그램이 있습니다.  
  
     ![Visio의 클러스터 특징 차트 예가](media/dm13-visio-cluster-samplecharshape.gif "Visio의 클러스터 특징 차트 예")  
  
     **판별 차트로 클러스터 표시**  
     이 옵션은 클러스터 다이어그램과 동일한 차트를 만들지만 다른 클러스터와 가장 크게 구별되는 현재 클러스터의 특징을 나열합니다.  
  
     마법사에서 다이어그램이 작성된 후 클러스터를 마우스 오른쪽 단추로 클릭하고 새 차트 유형을 선택하여 다른 차트 유형으로 전환할 수 있습니다. 이제 옵션을 선택 **특징 차트로 클러스터 표시**합니다.  
  
7.  옵션을 그대로 둡니다 **차트의 행 수가**를 5로 합니다.  
  
     이 옵션은 모델에서 클러스터의 수를 변경 되지 않습니다. 각 클러스터의 기능으로 표시 될 수 있는 특성의 수를 제한 하기만 합니다.  
  
     하지만 나중에 항목 수를 늘릴 수 없습니다 있도록 옵션은 차트 데이터에 대 한 필터로 작동 합니다.  
  
8.  **고급**을 클릭합니다.  
  
     합니다 **클러스터 옵션** 대화 상자는 다이어그램에 사용 된 셰이프의 시각적 모양을 사용자 지정 위치. 그래프에 사용된 색과 클러스터에 사용된 셰이프를 변경할 수 있습니다.  
  
     합니다 **음영 변수** 컨트롤이 Office 2013에서 작동 하지 않습니다.  
  
     ![셰이프 색을 선택 하는 고급](media/dm13-visio-clusteroptions-advanced.gif "셰이프 색을 선택 하는 고급을 클릭 합니다.")  
  
     **팁:** 일부 색은 Visio 테마 및 셰이프 편집 컨트롤을 사용하여 나중에 변경할 수 있습니다. 그러나 Visio 테마는 이러한 색 선택 중 일부를 재정의하기도 하므로 기본 색부터 시작하여 점차적으로 변경을 적용하는 것이 좋습니다.  
  
9. 클릭 **완료** 그래프를 만듭니다.  
  
     마법사는 데이터 마이닝 모델에서 정보를 검색하고 셰이프를 렌더링한 다음 각 클러스터를 특성 및 값으로 채웁니다.  
  
     ![종속성 네트워크](media/dm13-visiodepnet-defaultgraph.gif "종속성 네트워크")  
  
## <a name="explore-and-modify-the-finished-diagram"></a>완성된 다이어그램 탐색 및 수정  
 다이어그램이 완성된 후 다음 예와 같이 Visio 컨트롤을 사용하여 모양을 계속해서 사용자 지정할 수 있습니다.  
  
 ![Visio를 사용 하 여 사용자 지정 클러스터 다이어그램](media/dm13-visio-clustercomplete1.gif "Visio를 사용 하 여 사용자 지정 클러스터 다이어그램")  
  
 기본적인 클러스터 셰이프는 모두 마법사에서 생성됩니다. 다이어그램을 업데이트하고 개인 설정하려면 다음 도구를 사용하십시오.  
  
1.  슬라이더를 끌어 합니다 **클러스터 옵션** 컨트롤 약한 관계를 필터링 하 고 다이어그램을 간소화 합니다.  
  
2.  Visio를 사용 하 여 **페이지 레이아웃 재지정** 다른 클러스터 레이아웃을 실험할 수 있습니다.  
  
3.  사용 합니다 **커넥터** 옵션을 합니다 **디자인** 선을 지나가지 클러스터 않도록 연결선 스타일을 변경 하려면 탭 합니다.  
  
4.  클릭 합니다 **추가 기능** 리본을 한 후 데이터 마이닝 다이어그램을 사용 하 여 작업에 사용 되는 사용자 지정 도구 모음 중 하나를 표시 합니다.  
  
     **레이아웃**  
     현재 페이지에 맞도록 클러스터의 정렬을 최적화합니다.  
  
     **페이지 크기 조정**  
     이 컨트롤은 이전 HTML 버전용입니다. Visio 페이지 크기 조정 컨트롤을 대신 사용하십시오.  
  
     **설명**  
     클러스터가 선택된 경우 이 옵션을 클릭하면 클러스터에 대한 세부 정보가 표시됩니다.  
  
     ![클러스터에 대 한 세부 정보를 가져오려면 설명을 클릭](media/dm13-visio-cluster-description-control.gif "클러스터에 대 한 세부 정보를 가져오려면 설명을 클릭")  
  
     **가장자리 수준**  
     클러스터를 연결하는 선에 대한 신뢰성 점수를 표시합니다.  
  
     그러나 일부 배경을 비롯하여 마법사에서 생성된 기본 서식 이외의 특수한 서식을 적용하는 경우 이러한 점수가 표시되지 않을 수도 있습니다.  
  
     **슬라이더**  
     클러스터 사이의 선을 필터링합니다. 슬라이더를 위로 이동하면 가장 중요한 연결을 제외하고 모두 제거됩니다.  
  
     **음영**  
     이 컨트롤은 Office 2013에서 작동하지 않습니다.  
  
5.  사용 하 여는 **이동 및 확대/축소** 컨트롤을 **작업창** Visio의 영역 **보기** 리본의 클러스터 집합에 집중 하 고 다이어그램을 이동 합니다.  
  
6.  클러스터를 마우스 오른쪽 단추로 클릭하여 클러스터 셰이프와 관련된 옵션을 표시합니다.  
  
    -   차트 스타일 변경  
  
    -   클러스터 특징 차트 추가  
  
    -   클러스터 판별 차트 추가  
  
## <a name="see-also"></a>관련 항목  
 [Visio 데이터 마이닝 다이어그램 문제 해결 &#40;SQL Server 데이터 마이닝 추가 기능&#41;](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
