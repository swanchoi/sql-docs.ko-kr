---
title: 처리 및 저장소 용량-Analytics Platform System | Microsoft Docs
description: 비즈니스 요구 사항을 Analytics Platform System (APS) 어플라이언스에서에 필요한 계산 노드의 디스크의 크기와 데이터 배율 단위의 수를 결정 합니다.
author: mzaman1
manager: craigg
ms.prod: sql
ms.technology: data-warehouse
ms.topic: conceptual
ms.date: 04/17/2018
ms.author: murshedz
ms.reviewer: martinle
ms.openlocfilehash: f20de8ebc4e3b2970e439dbc413e588aa08b5324
ms.sourcegitcommit: 9c99f992abd5f1c174b3d1e978774dffb99ff218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2019
ms.locfileid: "54361573"
---
# <a name="processing-and-storage-capacity-in-analytics-platform-system"></a>Analytics Platform System의 처리 및 저장소 용량
비즈니스 요구 사항을 Analytics Platform System (APS) 어플라이언스에서에 필요한 계산 노드의 디스크의 크기와 데이터 배율 단위의 수를 결정 합니다. 이러한 처리 및 저장소 계산을 사용 하 여 용량 구매 및 계획 결정을 안내 합니다.  
  
  
## <a name="section1"></a>처리 용량에 대 한 계획  
쿼리 성능에 대 한 SQL Server 병렬 데이터 웨어하우스 (PDW)에 데이터에에서 대해 병렬로 작동 하는 CPU 코어 수에 따라 크게 달라 집니다. 제한 내에서 병렬 처리 수준 증가 방대한 병렬 처리 (MPP) 쿼리 성능이 향상 됩니다. 데이터 크기가 비교적 작은 경우에 큰 병렬 처리 함으로써 MPP 쿼리 엔진의 성능을 향상 되었습니다.  
  
예를 들어, 12 계산 노드를 사용 하 여 어플라이언스 병렬로 데이터를 처리 하는 192 CPU 코어에 있습니다. 192 양방향 병렬 처리입니다. 56 계산 노드가 포함 된 어플라이언스 코어가 896 병렬로 모든 작동 합니다. 이 크기의 병렬 처리의 MPP 컴퓨팅 없이 달성 가능한 아닙니다.  
  
눈에 띄는 활용 한 번에 둘 이상의 계산 노드가 추가 계산 노드 수가 늘어나면 기기 확장 필요 합니다. 하드웨어 공급 업체에는 어플라이언스를 크기 조정의 이점은 더 많은 계산 노드 간에 데이터를 재배포는 비용 보다 높은 되도록 데이터 배율 단위의 특정 구성을 지원 합니다.  
  
### <a name="data-scale-unit-configuration-examples---hpe"></a>HPE-데이터 배율 단위 구성 예  
이들은 데이터 규모 Uunits에 대 한 지원 되는 HPE 구성의 예입니다. 최신의 지원 되는 구성에서 다를 수 있지만 약 20% 용량을 늘려야 하는 방법의 예로 제공 됩니다.  
  
되며 다음 한 행에서 데이터 확장 Uunits 증가 된 백분율 용량 향상 것입니다. 예를 들어, 8 6에서 데이터 규모 단위를 늘리면을 33% 되며 CPU 코어 및 메모리를 제공 합니다.  또한이 테이블에 표시 되지 않습니다는 공간이 증가 합니다.  
  
|데이터 배율 단위|계산 노드|CPU 코어|메모리 (GB)|되며|  
|--------------------|-----------------|-------------|-----------------|----------|  
|1|2|32|512|-|  
|2|4|64|1024|100%|  
|3|6|96|1536|50%|  
|4|8|128|2048|33%|  
|5|10|160|2560|25%|  
|6|12|192|3072|20%|  
|8|16|256|4096|33%|  
|10|20|320|5120|25%|  
|12|24|384|6144|20%|  
|16|32|512|8192|33%|  
|20|40|640|10240|25%|  
|24|48|768|12288|20%|  
|28|56|896|14336|17%|  
  
설명:  
  
-   **데이터 크기 조정 단위** 어플라이언스 당 합니다. 데이터 확장 단위를 알아보려면 [분석 플랫폼 시스템 하드웨어 구성 요소](hardware-components.md)합니다.  
  
-   **계산 노드** 어플라이언스 당 합니다.  
  
-   **CPU 코어** 어플라이언스 당 합니다. 계산 노드당 코어 16 개, 각 미러 디스크 쌍 당 코어 한 개 있습니다. 계산 노드 디스크 구조를 참조 하세요 [분석 플랫폼 시스템 하드웨어 구성 요소](hardware-components.md)합니다.  
  
-   **메모리** 어플라이언스 당 합니다. 각 코어 256GB 메모리가 있습니다.  
  
### <a name="data-scale-unit-configuration-examples---dell-quanta"></a>데이터 크기 조정 단위 구성 예제-Dell, 퀀텀  
이들은 데이터 규모 Uunits에 대 한 지원 되는 Dell과 퀀텀 구성의 예입니다. 최신의 지원 되는 구성에서 다를 수 있지만 약 20% 용량을 늘려야 하는 방법의 예로 제공 됩니다.  
  
되며 다음 한 행에서 데이터 확장 Uunits 증가 된 백분율 용량 향상 것입니다. 예를 들어, 8 6에서 데이터 규모 단위를 늘리면을 33% 되며 CPU 코어 및 메모리를 제공 합니다. 또한이 테이블에 표시 되지 않습니다는 공간이 증가 합니다.  
  
|데이터 배율 단위|계산 노드|CPU 코어|메모리 (GB)|되며|  
|--------------------|-----------------|-------------|-----------------|----------|  
|1|3|48|768|-|  
|2|6|96|1536|100%|  
|3|9|144|2,304|50%|  
|4|12|192|3,072|33%|  
|5|15|240|3,840|25%|  
|6|18|288|4,608|20%|  
|7|21|336|5,376|17%|  
|8|24|384|6,144|14%|  
|9|27|432|6,912|13%|  
|12|36|576|9,216|33%|  
|15|45|720|11,520|25%|  
|18|54|864|13,824|20%|  
  
## <a name="section2"></a>저장소 용량 계획  
이 테이블을 로드 하 고 최대 6 페타바이트 크기의 압축 되지 않은 데이터를 완벽 하 게 작성된 된 분석 플랫폼 시스템 어플라이언스를 저장할 수는 예상 합니다. 
  
|공급 업체|드라이브 크기|실제 데이터 저장소 / 계산 노드|랙 당 최대 계산 노드|랙 당 최대 물리적 데이터 저장소|랙 당 최대 사용자 데이터 저장소를 예상합니다.|최대 랙|어플라이언스 당 최대 사용자 데이터 저장소를 예상합니다.|  
|----------|--------------|------------------------------------------|----------------------------------|------------------------------------------|------------------------------------------------|-----------------|-----------------------------------------------------|  
|HPE|1TB|16TB|8|128 TB|320 TB|7|2,240 TB|  
|HPE|2TB|32TB|8|256TB|640 TB|7|4,480 TB|  
|HPE|4TB|64TB|8|512 TB|1280 TB|7|8,960 TB|  
|DELL|1TB|16TB|9|144 TB|360 TB|6|2,160 TB|  
|DELL|2TB|32TB|9|288 TB|720 TB|6|4, 320 TB|  
|DELL|4TB|64TB|9|576 TB|1440 TB|6|8,640 TB|   
  
설명:  
  
-   **드라이브 크기** 각 하드웨어 공급 업체에서 1, 2 또는 4TB입니다.  
  
-   **계산 노드당 실제 데이터 저장소** = (드라이브 크기) * (계산 노드 당 16 개 디스크). 미러 디스크 중복 되므로 포함 되지 않습니다.  
  
-   **랙 당 최대 계산 노드** 하드웨어 공급 업체에 따라 다릅니다.  
  
-   **랙 당 최대 물리적 데이터 저장소** = (계산 노드당 실제 데이터 저장소) * (랙 당 최대 계산 노드).  
  
-   **랙 당 최대 사용자 데이터 저장소를 예상** = (랙 당 최대 물리적 데이터 저장소) * (5:1 압축 비율에 대 한 5) \* (로그 및 tempDB에 대 한 50%). 이 압축 되지 않은 사용자 데이터를 로드 하 고 기기에 저장할 수에 대 한 일반적인 예상치입니다. 이것은 예상 값 이며 소프트웨어에 의해 적용 되지 않습니다. 실제 사용자 데이터 저장소는 데이터 및 구성에 따라 달라 집니다.  
  
-   **최대 랙** 각 하드웨어 공급 업체에만 적용 됩니다.  
  
-   **어플라이언스 당 최대 데이터 저장소를 예상** = (랙 당 예상 최대 데이터 저장소) * (최대 랙). 사용자 데이터를 로드 하 고 완벽 하 게 작성된 된 기기에 저장할 수 없습니다 grand total 크기의 일반적인 예상치입니다.  
  
