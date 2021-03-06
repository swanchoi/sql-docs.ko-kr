---
title: 스파크라인 및 데이터 막대 추가(보고서 작성기 및 SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
ms.assetid: 0b297c2e-d48b-41b0-aabd-29680cdcdb05
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: ac5256d0f2d0cddea9f3b6ef29163381e1deccbd
ms.sourcegitcommit: 31800ba0bb0af09476e38f6b4d155b136764c06c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56288502"
---
# <a name="add-sparklines-and-data-bars-report-builder-and-ssrs"></a>스파크라인 및 데이터 막대 추가(보고서 작성기 및 SSRS)
  스파크라인과 데이터 막대는 불필요한 정보는 거의 없이 많은 정보를 제공하는 작은 여분의 차트입니다. 자세한 내용은 [스파크라인 및 데이터 막대 추가&#40;보고서 작성기 및 SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md)를 참조하세요.  
  
 스파크라인과 데이터 막대는 가장 일반적으로 테이블이나 행렬의 셀에 배치됩니다. 일반적으로 스파크라인은 각각 한 계열만 표시하며 데이터 막대는 하나 이상의 데이터 요소를 포함할 수 있습니다. 스파크라인과 데이터 막대는 모두 테이블이나 행렬의 각 행에 대한 계열 정보를 반복하여 효과를 끌어냅니다.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-sparkline-or-data-bar-to-a-table-or-matrix"></a>테이블이나 행렬에 스파크라인 또는 데이터 막대를 추가하려면  
  
1.  테이블이나 행렬을 아직 만들지 않은 경우 표시할 데이터가 포함된 테이블이나 행렬을 만듭니다. 자세한 내용은 [테이블&#40;보고서 작성기 및 SSRS&#41;](tables-report-builder-and-ssrs.md) 또는 [행렬&#40;보고서 작성기 및 SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md)을 참조하세요.  
  
2.  테이블이나 행렬에 열을 삽입합니다. 자세한 내용은 [열 삽입 또는 삭제&#40;보고서 작성기 및 SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md)를 참조하세요.  
  
3.  **삽입** 탭에서 **스파크라인** 또는 **데이터 막대**를 클릭한 다음 새 열의 셀을 클릭합니다.  
  
    > [!NOTE]  
    >  스파크라인은 테이블의 세부 그룹에는 배치할 수 없으며 그룹과 연결된 셀에 배치해야 합니다.  
  
4.  **스파크라인/데이터 막대 유형 변경** 대화 상자에서 원하는 스파크라인이나 데이터 막대의 유형을 클릭한 다음 **확인**을 클릭합니다.  
  
5.  스파크라인이나 데이터 막대를 클릭합니다.  
  
     **차트 데이터** 창이 열립니다.  
  
6.  **값** 영역에서 **필드 추가** 더하기 기호(**+**)를 클릭한 다음 차트에 표시할 값이 포함된 필드를 클릭합니다.  
  
7.  **범주 그룹** 영역에서 **필드 추가** 더하기 기호(**+**)를 클릭한 다음 그룹화할 값이 포함된 필드를 클릭합니다.  
  
     일반적으로 스파크라인과 데이터 막대의 경우 각 행에 한 계열만 필요하기 때문에 **계열 그룹** 영역에 필드를 추가하지 않습니다.  
  
## <a name="see-also"></a>관련 항목  
 [차트&#40;보고서 작성기 및 SSRS&#41;](charts-report-builder-and-ssrs.md)   
 [테이블 또는 행렬에서 차트의 데이터 정렬&#40;보고서 작성기 및 SSRS&#41;](align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs.md)  
  
  
