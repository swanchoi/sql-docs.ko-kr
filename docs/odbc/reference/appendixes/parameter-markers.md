---
title: 매개 변수 표식 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- minimum SQL syntax supported [ODBC]
- ODBC drivers [ODBC], minimum SQL syntax supported
- parameter markers [ODBC]
ms.assetid: 07213d04-cd31-45fd-a8c8-2e16e09eeaf4
author: MightyPen
ms.author: genemi
ms.reviewer: ''
manager: craigg
ms.openlocfilehash: cda6719eb46a4a05222bd54062e6cab98459d7dc
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2019
ms.locfileid: "56042884"
---
# <a name="parameter-markers"></a>매개 변수 표식
SQL-92 사양에 따라 응용 프로그램은 다음 위치에 매개 변수 표식을 배치할 수 없습니다. 보다 포괄적인 목록은 SQL-92 사양을 참조 하세요.  
  
-   에 **선택** 목록  
  
-   둘 다로 *식을* 에 *비교 조건자*  
  
-   이항 연산자의 피연산자가 모두로  
  
-   첫 번째와 두 번째 피연산자가 모두의는 **BETWEEN** 작업  
  
-   첫 번째 및 세 번째 피연산자로 **BETWEEN** 작업  
  
-   식 및 첫 번째 값을 **IN** 작업  
  
-   단항 피연산자로 + 또는-작업  
  
-   함수의 인수로 *집합 함수 참조*  
  
 매개 변수 표식에 대 한 자세한 내용은 SQL-92 사양을 참조 하세요. 매개 변수에 대 한 자세한 내용은 참조 하십시오 [문 매개 변수](../../../odbc/reference/develop-app/statement-parameters.md)합니다.
