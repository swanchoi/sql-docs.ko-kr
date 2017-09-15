---
title: "동시성 제어 이해 | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98b7dabe-9b12-4e1d-adeb-e5b5cb0c96f3
caps.latest.revision: 24
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 52c954cb3acc87753f9ede5a0fc786bd9ed9b755
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="understanding-concurrency-control"></a>동시성 제어 이해
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  동시성 제어란 여러 명의 사용자가 동시에 행을 업데이트할 때 데이터베이스의 무결성을 유지하기 위해 사용되는 여러 가지 기술을 말합니다. 잘못된 동시성으로 인해 커밋되지 않은 읽기, 가상 읽기, 반복되지 않는 읽기와 같은 문제가 발생할 수 있습니다. [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] 에서 사용 하는 모든 동시성 기술에 대 한 인터페이스를 제공 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 이러한 문제를 해결 합니다.  
  
> [!NOTE]  
>  에 대 한 자세한 내용은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 동시성의 "동시 데이터 액세스 관리"를 참조 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 온라인 설명서.  
  
## <a name="remarks"></a>주의  
 JDBC 드라이버에서 지원하는 동시성 유형은 다음과 같습니다.  
  
|동시성 유형|특징|행 잠금|Description|  
|----------------------|---------------------|---------------|-----------------|  
|CONCUR_READ_ONLY|읽기 전용|아니요|커서를 통한 업데이트는 지원되지 않으며 결과 집합을 구성하는 행에 대해 잠금이 보유되지 않습니다.|  
|CONCUR_UPDATABLE|낙관적 읽기/쓰기|아니요|데이터베이스에서 행 경합이 발생할 가능성은 희박하지만 발생할 가능성도 있다고 간주합니다. 타임스탬프 비교를 통해 행 무결성을 검사합니다.|  
|CONCUR_SS_SCROLL_LOCKS|비관적 읽기/쓰기|예|데이터베이스에서 행 경합이 발생할 가능성이 있다고 간주합니다. 행 잠금 없이 행 무결성이 보장됩니다.|  
|CONCUR_SS_OPTIMISTIC_CC|낙관적 읽기/쓰기|아니요|데이터베이스에서 행 경합이 발생할 가능성은 희박하지만 발생할 가능성도 있다고 간주합니다. 타임스탬프 비교를 통해 행 무결성을 검사합니다.<br /><br /> 에 대 한 [!INCLUDE[ssVersion2005](../../includes/ssversion2005_md.md)] 및 이상 버전에서는 서버는이 유형은 CONCUR_SS_OPTIMISTIC_CCVAL로 변경 테이블에 타임 스탬프 열이 없는 경우.<br /><br /> 에 대 한 [!INCLUDE[ssVersion2000](../../includes/ssversion2000_md.md)], 기본 테이블에 타임 스탬프 열을 경우 OPTIMISTIC WITH ROW VERSIONING OPTIMISTIC WITH VALUES가 지정 하는 경우에 사용 됩니다. OPTIMISTIC WITH ROW VERSIONING을 지정하고 테이블에 타임스탬프가 없는 경우 OPTIMISTIC WITH VALUES가 사용됩니다.|  
|CONCUR_SS_OPTIMISTIC_CCVAL|낙관적 읽기/쓰기|아니요|데이터베이스에서 행 경합이 발생할 가능성은 희박하지만 발생할 가능성도 있다고 간주합니다. 행 데이터 비교를 통해 행 무결성을 검사합니다.|  
  
## <a name="result-sets-that-are-not-updateable"></a>업데이트할 수 없는 결과 집합  
 업데이트할 수 있는 결과 집합은 행을 삽입, 업데이트 및 삭제할 수 있는 결과 집합입니다. 다음과 같은 경우에 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 업데이트 가능한 커서를 만들 수 없습니다. "결과 집합을 업데이트할 수 없습니다."라는 예외가 발생합니다.  
  
|원인|Description|해결책|  
|-----------|-----------------|------------|  
|JDBC 2.0(또는 이후 버전) 구문을 사용하여 문을 작성할 수 없습니다.|JDBC 2.0에서는 문 작성을 위한 새로운 메서드가 도입되었습니다. JDBC 1.0 구문을 사용한 경우 결과 집합이 기본적으로 읽기 전용으로 설정됩니다.|문을 작성할 때 결과 집합 유형과 동시성을 지정하십시오.|  
|TYPE_SCROLL_INSENSITIVE를 사용하여 문이 작성되었습니다.|[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]정적 스냅샷 커서를 만듭니다. 이 커서는 다른 사용자가 행을 업데이트하지 못하도록 커서를 보호하기 위해 기본 테이블 행과의 연결을 끊습니다.|정적 커서를 만들지 않으려면 TYPE_SCROLL_SENSITIVE, TYPE_SS_SCROLL_KEYSET, TYPE_SS_SCROLL_DYNAMIC 또는 TYPE_FORWARD_ONLY를 CONCUR_UPDATABLE과 함께 사용하십시오.|  
|테이블 디자인이 KEYSET 또는 DYNAMIC 커서를 방해합니다.|기본 테이블에 고유 키 수 있도록 없는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 행을 고유 하 게 식별할 수 있도록 합니다.|테이블에 고유 키를 추가하여 각 행의 고유 ID를 제공하십시오.|  
  
## <a name="see-also"></a>관련 항목:  
 [JDBC 드라이버로 결과 집합 관리](../../connect/jdbc/managing-result-sets-with-the-jdbc-driver.md)  
  
  