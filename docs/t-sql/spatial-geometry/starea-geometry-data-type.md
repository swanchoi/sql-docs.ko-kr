---
title: STArea(geometry 데이터 형식) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- STArea (geometry Data Type)
- STArea_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- STArea (geometry Data Type)
ms.assetid: a7dd6083-c649-4ac3-885d-1234e0db62f1
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 1e5ecf4856cc0fd2e17e56c876cf40d0bb1db9b9
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47719605"
---
# <a name="starea-geometry-data-type"></a>STArea(geometry 데이터 형식)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

  **geometry** 인스턴스의 전체 표면을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
.STArea ( )  
```  
  
## <a name="return-types"></a>반환 형식  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 반환 형식: **float**  
  
 CLR 반환 형식: **SqlDouble**  
  
## <a name="remarks"></a>Remarks  
 `STArea()`는 **geometry** 인스턴스가 0 및 1차원 도형만 포함하거나 비어 있으면 0을 반환합니다. **geometry** 인스턴스가 초기화되지 않은 경우 `STArea()`는 **NULL**을 반환합니다.  
  
## <a name="examples"></a>예  
  
### <a name="a-computing-the-area-of-a-polygon-instance"></a>1. Polygon 인스턴스의 면적 계산  
 다음 예에서는 `Polygon``geometry` 인스턴스를 만들고 다각형의 면적을 계산합니다.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POLYGON((0 0, 3 0, 3 3, 0 3, 0 0),(2 2, 2 1, 1 1, 1 2, 2 2))', 0);  
SELECT @g.STArea();  
```  
  
### <a name="b-computing-the-area-of-a-curvepolygon-instance"></a>2. CurvePolygon 인스턴스의 면적 계산  
 다음 예에서는 `CurvePolygon` 인스턴스의 면적을 계산합니다.  
  
```
 DECLARE @g geometry;  
 SET @g = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 2, 2 0, 4 2, 4 2, 0 2))');  
 SELECT @g.STArea() AS Area;
 ```  
  
## <a name="see-also"></a>참고 항목  
 [geometry 인스턴스의 OGC 메서드](../../t-sql/spatial-geometry/ogc-methods-on-geometry-instances.md)  
  
  
