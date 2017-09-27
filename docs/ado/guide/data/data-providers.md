---
title: "데이터 공급자 | Microsoft Docs"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data providers [ADO]
- OLE DB providers [ADO]
- ADO, OLE DB providers
ms.assetid: 877b9f25-60c4-4ab6-8052-2c28a3849e89
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 5a5264398741c58ac6f9aae504237ec1139ecb2c
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="data-providers"></a>데이터 공급자
데이터 공급자는 다양 한 SQL 데이터베이스, 인덱싱된 순차적 파일, 스프레드시트, 문서 저장소 및 메일 파일 등 데이터 원본을 나타냅니다. 공급자는 행 집합 이라고 하는 일반적인 추상화를 사용 하 여 균일 하 게 데이터를 표시 합니다.  
  
 ADO는 여러 다른 데이터 공급자에 연결할 수 있고 지정된 된 공급자의 특정 기능에 관계 없이 동일한 프로그래밍 모델을 계속 제공 하기 때문에 강력 하 고 유연한 합니다. 그러나 각 데이터 공급자가 고유 하므로 데이터 공급자에 따라 달라 집니다 ADO와 응용 프로그램 상호 작용 하는 방법.  
  
 예를 들어의 OLE DB Provider for SQL Server를 사용 되는 Microsoft SQL Server 데이터베이스에 액세스 하는 기능에 크게 속성과 다릅니다 Microsoft OLE DB Provider for Internet Publishing, 파일에 액세스 하는 데 사용 되는 중 웹 서버에 저장 합니다.