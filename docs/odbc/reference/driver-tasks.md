---
title: "드라이버 작업 | Microsoft Docs"
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
- ODBC architecture [ODBC], drivers
- drivers [ODBC], tasks
ms.assetid: 184c795a-c2e8-4d20-9902-12e60b2f0e45
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 331e3aee3a4a60cbfa1a1308b71da80bf9772f23
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="driver-tasks"></a>드라이버 작업
드라이버에서 수행 하는 특정 작업은 다음과 같습니다.  
  
-   에 연결 하 고 데이터 원본에서 해제 합니다.  
  
-   드라이버 관리자에서 확인 되지 함수 오류를 검사 합니다.  
  
-   트랜잭션을 시작 합니다. 이 응용 프로그램에 투명 합니다.  
  
-   SQL 문 실행에 대 한 데이터 소스에 제출 하는 중입니다. 드라이버는 ODBC SQL DBMS 전용 SQL;을 수정 해야 특정 DBMS SQL로 ODBC에 정의 된 이스케이프 절을 대체 하는 제한 됨 경우가 많습니다.  
  
-   데이터를 보내는 및 응용 프로그램에 의해 지정 된 대로 데이터 형식으로 변환 하는 포함 하 여 데이터 원본에서 데이터를 검색 합니다.  
  
-   DBMS 관련 오류를 ODBC Sqlstate에 매핑합니다.