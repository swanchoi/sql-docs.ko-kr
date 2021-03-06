---
title: ODBC 드라이버 하위 키 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- subkeys [ODBC], drivers subkey
- registry entries for components [ODBC], drivers subkey
- drivers subkey [ODBC]
ms.assetid: 8edbf68f-d05d-4d77-92f6-e9500008f520
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 43be1c5e75998903ff4e64fc5f4230818a873ffc
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47772021"
---
# <a name="odbc-drivers-subkey"></a>ODBC 드라이버 하위 키
ODBC 드라이버 하위 키 아래에서 값을 설치 된 드라이버를 나열합니다. 이러한 값의 형식은 다음 표에 표시 됩니다.  
  
|이름|데이터 형식|data|  
|----------|---------------|----------|  
|*드라이버 설명*|REG_SZ|**설치**|  
  
 합니다 *드라이버 설명* 이름은 드라이버 개발자가 정의 됩니다. 일반적으로 드라이버를 사용 하 여 연결 된 dbms의 이름입니다.  
  
 예를 들어, 서식 있는 텍스트 파일 및 SQL Server에 대 한 드라이버가 설치 되어 있습니다. ODBC 드라이버 하위 키 값 수 있습니다.  
  
```  
Text : REG_SZ : Installed  
SQL Server : REG_SZ : Installed  
```
