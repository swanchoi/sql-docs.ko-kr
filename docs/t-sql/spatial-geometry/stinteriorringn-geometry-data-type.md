---
title: "STInteriorRingN (geometry 데이터 형식) | Microsoft Docs"
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
- STInteriorRingN_TSQL
- STInteriorRingN (geometry Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- STInteriorRingN (geometry Data Type)
ms.assetid: 47310f9f-2cdb-41e0-a6da-7c3cfbf139ac
caps.latest.revision: 21
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: a973ba1a1f3092c6a973ce4db0b5188615075922
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="stinteriorringn-geometry-data-type"></a>STInteriorRingN(geometry 데이터 형식)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

지정된 된 내부 링을 반환 합니다.는 **Polygongeometry** 인스턴스.
  
## <a name="syntax"></a>구문  
  
```  
  
.STInteriorRingN ( expression )  
```  
  
## <a name="arguments"></a>인수  
 *expression*  
 이 **int** 1과 내부 링 개수 사이의 식은 **기 하 도형** 인스턴스.  
  
## <a name="return-types"></a>반환 형식  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]반환 형식: **기 하 도형**  
  
 CLR 반환 형식: **SqlGeometry**  
  
 열기 Geospatial Consortium (OGC) 입력: **LineString**  
  
## <a name="remarks"></a>주의  
 이 메서드가 반환 **null** 경우는 **geometry** 인스턴스가 다각형 않습니다. 이 메서드는 또한 throw 한 **ArgumentOutOfRangeException** 식이 링 개수 보다 큰 경우. 내부 링의 개수를 사용 하 여 반환 될 수 `STNumInteriorRing``()`합니다.  
  
## <a name="examples"></a>예  
 다음 예제에서는 한 `Polygon` 인스턴스 및 사용 하 여 `STInteriorRingN()` 으로 다각형의 내부 링을 반환 하는 **LineString**합니다.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POLYGON((0 0, 3 0, 3 3, 0 3, 0 0),(2 2, 2 1, 1 1, 1 2, 2 2))', 0);  
SELECT @g.STInteriorRingN(1).ToString();  
```  
  
## <a name="see-also"></a>관련 항목:  
 [Geometry 인스턴스의 OGC 메서드](../../t-sql/spatial-geometry/ogc-methods-on-geometry-instances.md)  
  
  

