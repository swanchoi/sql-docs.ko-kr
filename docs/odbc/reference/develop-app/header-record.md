---
title: 헤더 레코드 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- diagnostic information [ODBC], diagnostic records
- header records [ODBC]
- diagnostic records [ODBC]
ms.assetid: d0fff1ed-5616-422a-a394-7ea1d2486f89
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: b7b6ffacb618dd2b7714be59814f3f1a88a52228
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47813921"
---
# <a name="header-record"></a>헤더 레코드
헤더 레코드의 필드는 반환 코드, 행 개수, 상태 레코드의 수 및 실행 하는 문 유형 등 함수 실행에 대 한 일반 정보를 포함 합니다. 헤더 레코드는 함수에서 SQL_INVALID_HANDLE을 반환 하지 않는 한 항상 만들어집니다. 헤더 레코드의 필드의 전체 목록은 참조 합니다 [SQLGetDiagField](../../../odbc/reference/syntax/sqlgetdiagfield-function.md) 함수 설명 합니다.
