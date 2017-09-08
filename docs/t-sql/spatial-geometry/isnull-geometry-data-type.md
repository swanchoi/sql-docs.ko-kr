---
title: "IsNull (geometry 데이터 형식) | Microsoft Docs"
ms.custom: 
ms.date: 08/03/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- IsNull (geometry Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- IsNull (geometry Data Type)
ms.assetid: f95813a5-26c0-48aa-bfb8-56d2a0980788
caps.latest.revision: 13
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 9136a2caf43fea8d5cccd90d8dba85d815511afe
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="isnull-geometry-data-type"></a>IsNull(geometry 데이터 형식)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

유형의 **geometry** 인스턴스가 null입니다. 인스턴스가 Null이 아니면 0을 반환합니다.
  
## <a name="syntax"></a>구문  
  
```  
  
.IsNull  
```  
  
## <a name="return-types"></a>반환 형식  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]형식: **비트**  
  
 CLR 형식: **SqlBoolean**  
  
## <a name="remarks"></a>주의  
 `IsNull`테스트에 사용할 수 있는지 여부를 **geometry** 인스턴스가 null입니다. 이 속성은 인스턴스가 Null이 아니면 0을 반환하고 인스턴스가 Null이면 Null을 반환하므로 결과가 다소 혼동스러울 수 있습니다.  
  
 이 메서드는 주로 SQL Server 인프라에서 사용되지만 인스턴스가 Null인지 여부를 테스트하는 데 `IsNull`을 사용하는 것은 좋지 않습니다.  
  
## <a name="examples"></a>예  
  
## <a name="see-also"></a>관련 항목:  
 [Geometry 인스턴스의 확장된 메서드](../../t-sql/spatial-geometry/extended-methods-on-geometry-instances.md)  
  
  

