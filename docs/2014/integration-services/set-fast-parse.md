---
title: 빠른 구문 분석 설정 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
ms.assetid: dcd1dc09-6eaf-440b-9ce6-fef779ff794f
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: e8914ebe397d6e38b95673cef264e537ec820a31
ms.sourcegitcommit: 5a8678bf85f65be590676745a7fe4fcbcc47e83d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58391811"
---
# <a name="set-fast-parse"></a>빠른 구문 분석 설정
  빠른 구문 분석을 사용하는 원본 또는 변환의 각 열에는 빠른 구문 분석 속성을 설정해야 합니다. 이 속성을 설정하려면 플랫 파일 원본 및 데이터 변환의 고급 편집기를 사용합니다.  
  
### <a name="to-set-fast-parse"></a>빠른 구문 분석을 설정하려면  
  
1.  플랫 파일 원본이나 데이터 변환을 마우스 오른쪽 단추로 클릭하고 **고급 편집기 표시**를 클릭합니다.  
  
2.  **고급 편집기** 대화 상자에서 **입/출력 속성** 탭을 클릭합니다.  
  
3.  **입/출력** 창에서 빠른 구문 분석을 설정할 열을 클릭합니다.  
  
4.  속성 창에서 확장을 **사용자 지정 속성** 노드와 설정 합니다 `FastParse` 속성을 `True`입니다.  
  
5.  **확인**을 클릭합니다.  
  
  
