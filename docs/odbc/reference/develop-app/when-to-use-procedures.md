---
title: "프로시저를 사용 하는 경우 | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL statements [ODBC], procedures
- procedures [ODBC], about procedures
ms.assetid: 7dc9e327-dd54-4b10-9f66-9ef5c074f122
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: a7bae5e984d66d8b71a9e4b84708f3ea126c1e0b
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="when-to-use-procedures"></a>프로시저를 사용 하는 경우
모든 프로시저를 사용 하 여 있다는 사실에 기반으로 SQL 문을에서 이동 데이터 원본에 응용 프로그램, 다양 한 프로시저를 사용 하 여 장점이 있습니다. 응용 프로그램에서 남아 상호 운용 가능한 프로시저 호출입니다. 이러한 이점 중 하나:  
  
-   **성능** 프로시저는 SQL 문을 실행 하는 가장 빠른 방법은 일반적으로 합니다. 와 같은 실행을 준비 하 고 문을 컴파일 및 별도 두 단계로 실행 합니다. 준비 된 실행 달리 프로시저는 런타임 시 실행 됩니다. 다른 시간에 컴파일됩니다.  
  
-   **비즈니스 규칙** A *비즈니스 규칙* 회사 비즈니스가 수행 하는 방법에 대 한 규칙입니다. 예를 들어 새 판매 주문을 추가 하려면 영업 사원 제목이 있는 모든 사용자 허용 될 수 있습니다. 프로시저에서 이러한 규칙을 배치 하면 개별 회사 응용 프로그램 코드를 수정 하지 않고도 응용 프로그램에서 호출한 프로시저를 다시 작성 하 여 수직 응용 프로그램을 사용자 지정할 수 있습니다. 예를 들어 주문 입력 응용 프로그램 프로시저를 호출할 수 **InsertOrder** 고정 매개 변수를 가진 방식을 정확 하 게 **InsertOrder** 구현 회사 마다 다를 수 있습니다.  
  
-   **Replaceability** 밀접 하 게 프로시저에 비즈니스 규칙을 배치은 응용 프로그램을 다시 컴파일하지 않고 프로시저를 대체할 수 있습니다. 비즈니스 규칙에는 회사에 구입 하 고 응용 프로그램을 설치한 후이 변경 되 면 회사 해당 규칙을 포함 하는 프로시저를 변경할 수 있습니다. 응용 프로그램의 관점에서 아무 것도 변경 되었습니다. 여전히 특정 작업을 수행 하는 특정 프로시저를 호출 합니다.  
  
-   **특정 DBMS SQL** 프로시저 응용 프로그램 특정 DBMS SQL을 악용 하 고 상호 운용 가능한을 계속 유지 하는 방법을 제공 합니다. 예를 들어 프로시저에서 흐름 제어 문 SQL에서 지 원하는 DBMS에 트래핑 수도 있으며 오류에서 복구 하는 동안 프로시저에서 흐름 제어 문을 지원 하지 않는 DBMS에 오류가 반환 될 수 있습니다.  
  
-   **절차 동등한 트랜잭션을 존속** 일부 데이터 원본의 경우에 트랜잭션이 커밋되거나 롤백될 때 연결에서 모든 준비 된 문에 대 한 액세스 계획 삭제 됩니다. 데이터 원본에 영구적으로 저장 되는 프로시저에서 SQL 문을 배치 하 여 문의 트랜잭션을 지속 됩니다. 준비 된, 부분적으로 준비 절차 생존 하는 여부 또는 준비 되지 않은 상태는 특정 DBMS 합니다.  
  
-   **개발 구분** 프로시저 응용 프로그램의 나머지 부분과에서 별도로 개발 될 수 있습니다. 큰 기업에서 더 이상 특별 한 프로그래머의 기술을 악용 하는 방법을 제공 될 수 있습니다이 합니다. 즉, 응용 프로그램 프로그래머는 사용자 인터페이스 코드를 작성할 수 및 데이터베이스 프로그래머가 프로시저를 작성할 수 있습니다.  
  
 프로시저 및 사용자 지정 응용 프로그램에서 일반적으로 사용 됩니다. 고정 된 작업을 수행 하는 경향이 이러한 응용 프로그램 및 여기에 하드 코드 프로시저 호출 수입니다. 예를 들어 주문 입력 응용 프로그램 절차를 호출할 수 **InsertOrder**, **DeleteOrder**, **UpdateOrder**, 및 **GetOrders** .  
  
 일반 응용 프로그램에서 프로시저를 호출할 필요가 있습니다. 특정 응용 프로그램의 컨텍스트에서 작업을 수행 하는 절차도 작성 된 일반적으로 일반 응용 프로그램을 사용 하 여 없습니다. 예를 들어 스프레드시트에 되지 않아도 호출 하는 **InsertOrder** 위에서 언급 한 프로시저입니다. 또한 일반 응용 프로그램 구성 하지 않아야 프로시저 빨리 문 실행; 제공를 높이기 위해 런타임 시 뿐만 아니라 있기 때문이 직접 또는 준비 된 실행 보다 속도가 느려질 수 DBMS 전용 SQL 문을 필요 합니다.  
  
 이 예외는 종종 프로그래머가 프로시저를 실행 및 프로시저를 테스트 하는 프로그래머를 위한는 방법을 제공할 수 있는 SQL 문을 만들 수 있는 방법을 제공 하는 응용 프로그램 개발 환경입니다. 이러한 환경 호출 **SQLProcedures** 목록 사용할 수 있는 절차와 **SQLProcedureColumns** 입력, 입/출력 및 출력 매개 변수를 나열 하려면 프로시저 반환 값 및 열에는 프로시저에 의해 만들어진 모든 결과 집합입니다. 그러나 이러한 프로시저 개발 해야 미리 각 데이터 소스에 이렇게 하려면 특정 DBMS SQL 문의 해야 합니다.  
  
 프로시저를 사용 하 여 세 가지 주요 단점이 있습니다. 첫 번째 프로시저를 작성 및와 응용 프로그램이 실행 된 각 DBMS에 대 한 컴파일된 해야 하는 합니다. 사용자 지정 응용 프로그램에 대 한 문제가 없을 때 개발 및 유지 관리 세로 응용 프로그램 시간을 다양 한 Dbms에서 실행 되도록 설계 증가할 크게 수 있습니다.  
  
 두 번째 단점은 여러 Dbms 프로시저를 지원 하지 않습니다. 마찬가지로이 다양 한 Dbms 사용 하 여 실행 하도록 설계 세로 응용 프로그램에 문제가 될 가능성이 가장 높은 합니다. 프로시저를 지원 하는지 여부를 확인 하려면 응용 프로그램이 호출 **SQLGetInfo** SQL_PROCEDURES 옵션을 사용 합니다.  
  
 특히 응용 프로그램 개발 환경에 적용 되는 세 번째 단점은 ODBC 프로시저를 만들기 위한 표준 문법을 정의 하지 않습니다. 즉, 응용 프로그램 interoperably 프로시저를 호출할 수 있으며, 있지만 만들 수는 없습니다 interoperably 합니다.