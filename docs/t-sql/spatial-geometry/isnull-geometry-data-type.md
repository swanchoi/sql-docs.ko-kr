---
title: IsNull(geometry 데이터 형식) | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- IsNull (geometry Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- IsNull (geometry Data Type)
ms.assetid: f95813a5-26c0-48aa-bfb8-56d2a0980788
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 4b861d170316dbc9d66c7f8e7954910438031f1b
ms.sourcegitcommit: 032273bfbc240fe22ac6c1f6601a14a6d99573f7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2019
ms.locfileid: "55513803"
---
# <a name="isnull-geometry-data-type"></a>IsNull(geometry 데이터 형식)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

**geometry** 인스턴스의 형식은 Null입니다. 인스턴스가 Null이 아니면 0을 반환합니다.
  
## <a name="syntax"></a>구문  
  
```  
.IsNull  
```  
  
## <a name="return-types"></a>반환 형식  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 형식: **bit**  
  
 CLR 형식: **SqlBoolean**  
  
## <a name="remarks"></a>Remarks  
 `IsNull`을 사용하여 **geometry** 인스턴스가 Null인지 여부를 테스트할 수 있습니다. `IsNull`은 인스턴스가 Null이 아니면 0을 반환하고, Null이면 Null을 반환합니다.  
  
 이 메서드는 주로 SQL Server 인프라에서 사용되지만 인스턴스가 Null인지 여부를 테스트하는 데 `IsNull`을 사용하는 것은 좋지 않습니다.  
  

## <a name="see-also"></a>참고 항목  
 [geometry 인스턴스의 확장 메서드](../../t-sql/spatial-geometry/extended-methods-on-geometry-instances.md)  
  
  

