---
title: "유형의 드라이버 | Microsoft Docs"
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
- driver compatibility issues [ODBC]
- ODBC drivers [ODBC], backward compatibility
- backward compatibility [ODBC], application and driver compatibility
- compatibility [ODBC], application and driver compatibility
ms.assetid: 864c53c1-b68a-48b6-b6bc-5ecb520bb9dc
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 464ba066af26c84c35f178b1a008d2e10a852119
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="types-of-drivers"></a>유형의 드라이버
ODBC 드라이버는 다음과 같이 분류할 수 있습니다.  
  
-   **32 비트 ODBC 2입니다.**  
     ***x* 드라이버** 32 비트 드라이버입니다.  
  
    -   ODBC 2만 내보냅니다*.x* 함수입니다.  
  
    -   ODBC 2에서 보여 줍니다. *x* 동작 변경 내용에 대 한 동작입니다.  
  
-   **ISO 및 Open 그룹 규격 드라이버** 32 비트 드라이버입니다.  
  
    -   Open Group 또는 ISO CLI 문서에서 설명 하는 모든 함수를 내보냅니다. ODBC에서 사용 되지 않는 함수 중 몇 가지도 포함 됩니다.  
  
    -   동작 변경 내용에 대 한 ODBC 3.0 동작을 수행 합니다.  
  
    -   ODBC 3.0 드라이버 관리자를 통해 반드시 이동 하지 않습니다.  
  
-   **ODBC 3.0 드라이버** 32 비트 드라이버입니다.  
  
    -   사용 되지 않는 함수와 뺀 ODBC 3.0에 있는 함수만 내보냅니다.  
  
    -   ODBC 2 현상이 수 있습니다. *x* SQL_ATTR_APP_ODBC_VERSION 환경 특성을 기반으로 동작 또는 동작 변경 내용에 대해 ODBC 3.0 동작 합니다.  
  
-   **ODBC 3.5 (또는 이후 버전) ANSI 드라이버** 32 비트 드라이버입니다.  
  
    -   사용 되지 않는 함수와 뺀 ODBC 3.5에 있는 함수만 내보냅니다.  
  
    -   ODBC 2 현상이 수 있습니다. *x* SQL_ATTR_APP_ODBC_VERSION 환경 특성을 기반으로 동작 또는 ODBC 3.0 동작 또는 동작 변경 내용에 대해 ODBC 3.5 동작 합니다.  
  
-   **ODBC 3.5 또는 그 이상의 유니코드 드라이버** 32 비트 드라이버입니다.  
  
    -   ODBC 3.5 ANSI 드라이버의 모든 기능을 지원합니다.  
  
    -   모든 ODBC 문자열 Api의 유니코드 버전을 내보냅니다.  
  
    -   저장 하 고 데이터 원본에 대해 유니코드 데이터를 처리할 수 있습니다.  
  
> [!NOTE]  
>  16 비트 ODBC 드라이버는 ODBC 3와 직접 작동 하지 않습니다. *x* 드라이버 관리자입니다. 그러나 이후에 3까지 썽크는 2.0 ODBC 드라이버 관리자를 사용 하는 16 비트 드라이버에 대 한 같습니다. *x* 드라이버 관리자입니다.