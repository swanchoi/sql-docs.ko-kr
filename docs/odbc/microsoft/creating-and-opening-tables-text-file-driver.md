---
title: "만들기 및 열기 테이블 (텍스트 파일 드라이버) | Microsoft Docs"
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
- text file driver [ODBC], creating and opening tables
ms.assetid: e6a07dda-a665-4f5b-a8d6-9ff479700513
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 41190a0a3eabda2f73c8f6046a64b7b7db929fa1
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="creating-and-opening-tables-text-file-driver"></a>만들기 및 테이블 (텍스트 파일 드라이버) 열기
텍스트 드라이버를 사용 하면 Odbcinst.ini에 지정 된 형식을 사용 하 여 새 테이블이 만들어집니다. 지정 하지 않으면 테이블이 CSVDELIMITED 형식으로 만들어집니다. 기본적으로 정수 열 11 자로 기본 하 및 FLOAT 열 22 자가 하 기본 키를 누릅니다. 날짜 열에는 YYYY-월-일 형식을 사용합니다. CHAR 및 LONGCHAR 열 만들기 문에 지정 된 너비는입니다.