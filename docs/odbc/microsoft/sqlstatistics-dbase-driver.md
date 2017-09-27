---
title: "SQLStatistics (dBASE 드라이버) | Microsoft Docs"
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
- SQLStatistics function [ODBC], dBASE Driver
- DBase driver [ODBC], SQLStatistics
ms.assetid: 631cec1b-66b7-4103-b9a7-ffd81da3c442
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 29d7759aa941a04014a3ed87ac75c5794ef2ad29
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="sqlstatistics-dbase-driver"></a>SQLStatistics (dBASE 드라이버)
> [!NOTE]  
>  이 항목에서는 dBASE 드라이버 관련 정보를 제공 합니다. 이 함수에 대 한 일반 정보에서 해당 항목을 참조 하십시오. [ODBC API 참조](../../odbc/reference/syntax/odbc-api-reference.md)합니다.  
  
|열|설명|  
|------------|--------------|  
|TABLE_QUALIFIER|디렉터리 경로입니다.<br /><br /> 패턴 일치에서 지원 되지 않습니다는 *szTableQualifier* 인수입니다.|  
|TABLE_OWNER|소유자 이름입니다. 지원 되지 않으므로이 열에 NULL이 반환 됩니다.|  
|TABLE_NAME|구분 되지 않은 테이블 이름입니다.<br /><br /> 패턴 일치에서 지원 되지 않습니다는 *szTableName* 인수입니다.|  
|INDEX_QUALIFIER|항상 NULL이 반환 됩니다.|  
|INDEX_NAME|인덱스에 따라 다릅니다.|  
|TYPE|형식에 대 한 SQL_TABLE_STAT 또는 SQL_INDEX_OTHER만 반환 됩니다.|  
|SEQ_IN_INDEX|인덱스에 따라 다릅니다.|  
|COLUMN_NAME|인덱스에 따라 다릅니다.|  
|COLLATION|인덱스에 따라 다릅니다.|  
|PAGES|항상 NULL이 반환 됩니다.|  
  
 고유성 기반 필터링 (의 *fUnique* 인수). *fAccuracy* 매개 변수가 무시 됩니다.