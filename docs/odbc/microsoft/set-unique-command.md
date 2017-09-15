---
title: "집합의 고유한 명령 | Microsoft Docs"
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
- SET UNIQUE command [ODBC]
ms.assetid: 1f69e31e-4599-47cc-ac89-b86fba8703c5
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: bed7fb14102c754d16409259fe7e1f5177652d05
ms.contentlocale: ko-kr
ms.lasthandoff: 09/09/2017

---
# <a name="set-unique-command"></a>고유한 명령 집합
중복 인덱스 키 값을 가진 레코드는 인덱스 파일에서 유지 관리 하는지 여부를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
SET UNIQUE ON | OFF  
```  
  
## <a name="arguments"></a>인수  
 ON  
 인덱스 파일에 중복 인덱스 키 값이 있는 레코드를 포함 하지 않았음을 지정 합니다. 인덱스 파일에 원래 인덱스 키 값을 가진 첫 번째 레코드에만 포함 됩니다.  
  
 OFF  
 (기본값)입니다. 중복 인덱스 키 값을 가진 레코드 인덱스 파일에 포함 되어야 함을 지정 합니다.  
  
## <a name="remarks"></a>주의  
 인덱스 파일 인덱스 다시 작성을 발급 하는 경우 고유 설정 설정을 유지 합니다. 자세한 내용은 참조 [인덱스](../../odbc/microsoft/index-command.md)합니다.