---
title: Sybase ASE 및 SQL Server 데이터 형식 (SybaseToSQL) 매핑 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Mapping Sybase ASE Schemas to SQL Server Schemas
- Type Mapping Settings
ms.assetid: 784365d3-df4e-47ab-8ee0-d8392b52f510
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: 8e50253b7c7fb6c59b4303c528c1ef7267ccf644
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47631281"
---
# <a name="mapping-sybase-ase-and-sql-server-data-types-sybasetosql"></a>Sybase ASE 및 SQL Server 데이터 형식 매핑(SybaseToSQL)
Sybase 적응형 Server Enterprise (ASE) 데이터베이스 형식에서 다른 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 또는 SQL Azure 데이터베이스 형식입니다. ASE 데이터베이스 개체를 변환 하는 경우 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 또는 SQL Azure 개체를 ASE에서 데이터 형식을 매핑하는 방법을 지정 해야 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 또는 SQL Azure입니다. 기본 데이터 형식 매핑을 그대로 사용 하거나 다음 섹션에 표시 된 대로 매핑을 사용자 지정할 수 있습니다.  
  
## <a name="default-mappings"></a>기본 매핑  
SSMA에 기본 데이터 형식 매핑 집합이 있습니다. 기본 매핑 목록을 참조 하세요 [프로젝트 설정 &#40;형식 매핑&#41; &#40;SybaseToSQL&#41;](../../ssma/sybase/project-settings-type-mapping-sybasetosql.md)합니다.  
  
## <a name="type-mapping-inheritance"></a>형식 상속 매핑  
프로젝트 수준, 개체 범주 수준 (예: 모든 저장된 프로시저) 또는 개체 수준에서 형식 매핑을 사용자 지정할 수 있습니다. 설정이 낮은 수준에서 재정의 되지 않는 경우 더 높은 수준에서 상속 됩니다. 예를 들어, 매핑하는 경우 **smallmoney** 하 **money** 프로젝트 수준에서 프로젝트의 모든 개체 범주 수준 개체 또는 개체 수준에서 매핑을 사용자 지정 하지 않으면이 매핑을 사용 합니다.  
  
보면 합니다 **형식 매핑** SSMA 백그라운드에서에서 탭은 상속 되는 형식 매핑을 표시할 색으로 구분 합니다. 형식 매핑의 배경이 노란색 상속 된 형식 매핑 및 현재 수준에서 지정 된 모든 매핑에 대 한 백서입니다.  
  
## <a name="customizing-data-type-mappings"></a>사용자 지정 데이터 형식 매핑  
다음 절차에는 프로젝트, 데이터베이스 또는 개체 수준에서의 데이터 형식을 매핑하는 방법을 보여 줍니다.  
  
**데이터 형식을 매핑할**  
  
1.  전체 프로젝트에 대 한 데이터 형식 매핑 사용자 지정을 하려면 엽니다는 **프로젝트 설정** 대화 상자:  
  
    1.  에 **도구** 메뉴에서 **프로젝트 설정을**합니다.  
  
    2.  왼쪽된 창에서 선택 **형식 매핑**합니다.  
  
        형식 매핑 차트 및 단추를 오른쪽 창에 나타납니다.  
  
    또는 데이터 형식에 맞게 매핑 데이터베이스, 테이블, 뷰 또는 저장된 프로시저 수준에서 데이터베이스, 개체 범주 또는 개체 탐색기에서 선택 Sybase 메타 데이터:  
  
    1.  Sybase 메타 데이터 탐색기에서 폴더 또는 사용자 지정 하려는 개체를 선택 합니다.  
  
    2.  오른쪽 창에서을 클릭 합니다 **형식 매핑** 탭 합니다.  
  
2.  새 매핑을 추가 하려면 다음을 수행 합니다.  
  
    1.  **추가**를 클릭합니다.  
  
    2.  아래 **원본 유형**를 매핑할 ASE 데이터 형식을 선택 합니다.  
  
    3.  형식 길이 필요한 경우의 매핑에 대 한 최소한의 데이터 길이 지정 합니다 **에서** 상자의 및에서 매핑에 대 한 최대 데이터 길이 지정 합니다 **를** 상자.  
  
        이렇게 하면 동일한 데이터 형식의 작고 큰 값 데이터 매핑을 사용자 지정할 수 있습니다.  
  
    4.  아래 **대상 유형**, 대상을 선택 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 또는 SQL Azure 데이터 형식입니다.  
  
        일부 유형의 대상 데이터 형식의 길이 해야합니다. 필요한 경우 새 데이터 길이 입력 합니다 **바꿉니다** 상자입니다.  
  
    5.  **확인**을 클릭합니다.  
  
3.  데이터 형식 매핑을 편집 하려면 다음을 수행 합니다.  
  
    1.  **편집**을 클릭합니다.  
  
    2.  아래 **원본 유형**를 매핑할 ASE 데이터 형식을 선택 합니다.  
  
    3.  형식 길이 필요한 경우의 매핑에 대 한 최소한의 데이터 길이 지정 합니다 **에서** 상자의 및에서 매핑에 대 한 최대 데이터 길이 지정 합니다 **를** 상자.  
  
        이렇게 하면 동일한 데이터 형식의 작고 큰 값 데이터 매핑을 사용자 지정할 수 있습니다.  
  
    4.  아래 **대상 유형**, 대상을 선택 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 또는 SQL Azure 데이터 형식입니다.  
  
        일부 유형의 대상 데이터 형식의 길이 해야합니다. 필요한 경우 새 데이터 길이 입력 합니다 **바꿉니다** 상자를 선택한 다음 클릭 **확인**합니다.  
  
4.  사용자 지정 데이터 형식 매핑을 제거 하려면 다음을 수행 합니다.  
  
    1.  제거 하려는 데이터 형식 매핑을 포함 하는 형식 매핑 목록에서 행을 선택 합니다.  
  
    2.  **제거**를 클릭합니다.  
  
        상속 된 매핑을 제거할 수 없습니다. 그러나 상속된 매핑 사용자 지정 매핑을 특정 개체 또는 개체 범주에 의해 재정의 됩니다.  
  
## <a name="next-steps"></a>다음 단계  
마이그레이션 프로세스의 다음 단계는가 중 하나로 [평가 보고서를 만드는](assessing-sybase-ase-database-objects-for-conversion-sybasetosql.md) 또는 [변환 Sybase ASE 데이터베이스 개체를 SQL Server 또는 SQL Azure 구문](converting-sybase-ase-database-objects-sybasetosql.md)합니다. 평가 보고서를 만드는 경우 Sybase ASE 개체를 평가 하는 동안 자동으로 변환 됩니다.  
  
## <a name="see-also"></a>관련 항목  
[Sybase ASE 데이터베이스를 SQL Server-Azure SQL DB로 마이그레이션 &#40;SybaseToSQL&#41;](../../ssma/sybase/migrating-sybase-ase-databases-to-sql-server-azure-sql-db-sybasetosql.md)  
  
