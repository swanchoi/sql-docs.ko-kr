---
title: 프로젝트 옵션 (DB2ToSQL) 설정 | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: f325a606-97ac-48bc-b344-b55f5e086a48
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: 16bf79c185a23399d48d141b5d773e2e0d41dc3f
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47785591"
---
# <a name="setting-project-options-db2tosql"></a>프로젝트 옵션 설정 (DB2ToSQL)
각 SSMA 프로젝트에 대 한 프로젝트 수준 옵션을 설정할 수 있습니다. 이러한 옵션에는 변환 개체, 개체 로드, 사용자 인터페이스 및 데이터 마이그레이션 설정을 지정합니다. 개체를 변환 하기 전에 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터를 마이그레이션하거나 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], 구성 옵션을 프로젝트에 적절 한지 확인 합니다.  
  
SSMA를 사용 하면 모든 프로젝트에 대 한 기본 옵션을 구성할 수 있습니다. 이러한 옵션은 사용자가 만든 모든 새 프로젝트에 적용 됩니다. 그런 다음 각 프로젝트에 대 한 옵션을 사용자 지정할 수 있습니다.  
  
## <a name="configuration-options-and-modes"></a>구성 옵션 및 모드  
SSMA는 프로젝트 설정의 5 개 집합에 있습니다.  
  
-   프로젝트 정보  
  
-   일반 (변환, 마이그레이션, 개체 로드)  
  
-   Synchronization  
  
-   GUI  
  
-   형식 매핑  
  
또한 이러한 설정을 구성 하기 위한 4 가지 모드에 있습니다.  
  
-   Default  
  
-   Optimistic  
  
-   전체  
  
-   사용자 지정  
  
대부분의 사용자에 대 한 기본 모드를 사용 하는 것이 좋습니다. 최적 모드는 현재 DB2 구문을 많이 유지 및 읽기가 쉽습니다. 그러나 현재 구문을 유지 정확 하지 않을 합니다. 값이 같은 DB2 구문 변환 해야 하는 경우 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 구문, 전체 모드를 가장 완벽 변환을 수행 하지만 결과 코드를 읽기가 어려울 수 있습니다. 사용자 지정 모드 옵션을 설정합니다.  
  
설정 및 각 모드에는 설정 적용 방법에 대 한 자세한 내용은 다음 항목을 참조 합니다.  
  
-   [프로젝트 설정 &#40;변환&#41; &#40;DB2ToSQL&#41;](../../ssma/db2/project-settings-conversion-db2tosql.md)  
  
-   [프로젝트 설정 &#40;마이그레이션&#41; &#40;DB2ToSQL&#41;](../../ssma/db2/project-settings-migration-db2tosql.md)  
  
-   [프로젝트 설정&#40;동기화&#41; &#40;DB2ToSQL&#41;](../../ssma/db2/project-settings-synchronization-db2tosql.md)  
  
-   [프로젝트 설정 &#40;GUI&#41; &#40;DB2ToSQL&#41;](../../ssma/db2/project-settings-gui-db2tosql.md)  
  
-   [프로젝트 설정 &#40;형식 매핑&#41; &#40;DB2ToSQL&#41;](../../ssma/db2/project-settings-type-mapping-db2tosql.md)  
  
## <a name="setting-project-options"></a>프로젝트 옵션 설정  
SSMA에 모든 프로젝트에 대 한 기본 설정을 구성할 수 있습니다. 이러한 설정은 SSMA 구성 파일에 저장 되며 사용자가 만든 모든 새 프로젝트에 적용 됩니다.  
  
**기본 프로젝트 옵션을 설정 하려면**  
  
1.  에 **도구** 메뉴에서 클릭 **기본 프로젝트 설정**합니다.  
  
2.  에 **기본 프로젝트 설정** 대화 상자에서 다음 절차 중 하나를 사용 합니다.  
  
    -   설정을 보거나에서 변경 하는 데 필요한는 마이그레이션 프로젝트 형식을 선택 **마이그레이션 대상 버전** 클릭 드롭다운 **일반** 선택 변환한 왼쪽된 창 맨 아래에서 또는 마이그레이션입니다.  
  
    -   에 미리 정의 된 모드를 선택 하는 **모드** 드롭다운 목록 상자에서 **기본**를 **Optimistic**, 또는 **전체**합니다.  
  
    -   사용자 지정 설정을 지정 하려면 선택 하거나 새 설정이 나 값을 입력 합니다.  
  
3.  클릭 **확인** 설정을 저장 합니다.  
  
현재 프로젝트에 대 한 설정을 사용자 지정할 수도 있습니다. 이러한 설정은 현재 프로젝트 파일에 저장 됩니다.  
  
**현재 프로젝트에 대 한 설정을 사용자 지정 하려면**  
  
1.  에 **도구** 메뉴에서 클릭 **프로젝트 설정을**합니다.  
  
2.  에 **프로젝트 설정** 대화 상자에서 다음 절차 중 하나를 사용 합니다.  
  
    -   에 미리 정의 된 모드를 선택 하는 **모드** 드롭다운 목록 상자에서 **기본**를 **Optimistic**, 또는 **전체**합니다.  
  
    -   사용자 지정 모드를 지정 하는 **모드** 상자에서 **사용자 지정**를 선택한 다음 적절 한 프로젝트 설정 합니다.  
  
3.  클릭 **확인** 설정을 저장 합니다.  
  
## <a name="next-steps"></a>다음 단계  
다음 단계는 마이그레이션 프로젝트 요구 사항에 따라 달라 집니다.  
  
-   원본 및 대상 데이터 형식 매핑 사용자 지정을 참조 하세요 [매핑 DB2 및 SQL Server 데이터 형식 &#40;DB2ToSQL&#41;](../../ssma/db2/mapping-db2-and-sql-server-data-types-db2tosql.md)합니다.  
  
-   DB2 데이터베이스 개체 정의를 변환할 수이 고, 그렇지 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 개체 정의 합니다. 자세한 내용은 [DB2 스키마 변환 &#40;DB2ToSQL&#41;](../../ssma/db2/converting-db2-schemas-db2tosql.md)합니다.  
  
## <a name="see-also"></a>관련 항목  
[DB2 및 SQL Server 데이터 형식 매핑 &#40;DB2ToSQL&#41;](../../ssma/db2/mapping-db2-and-sql-server-data-types-db2tosql.md)  
  
