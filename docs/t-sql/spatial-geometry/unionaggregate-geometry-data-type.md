---
title: UnionAggregate (geometry 데이터 형식) | Microsoft Docs
ms.custom: ''
ms.date: 08/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- UnionAggregate method (geometry)
ms.assetid: dc7929cc-55ca-4a2c-a4b9-f5452f95bde8
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 0544c554394cd69fe505a0596f653af29e637ebc
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47777091"
---
# <a name="unionaggregate-geometry-data-type"></a>UnionAggregate(geometry 데이터 형식)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

geometry 개체 집합에서 통합 연산을 수행합니다.
  
## <a name="syntax"></a>구문  
  
```  
  
UnionAggregate ( geometry_operand )  
```  
  
## <a name="arguments"></a>인수  
 *geometry_operand*  
 통합 연산을 수행할 **geometry** 개체 집합을 보관하는 **geometry** 형식 테이블 열입니다.  
  
## <a name="return-types"></a>반환 형식  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 반환 형식: **geometry**  
  
## <a name="exceptions"></a>예외  
 유효하지 않은 입력 값이 있는 경우 `FormatException`을 발생시킵니다. [STIsValid &#40;geometry 데이터 형식&#41;](../../t-sql/spatial-geometry/stisvalid-geometry-data-type.md) 참조  
  
## <a name="remarks"></a>Remarks  
 이 메서드는 입력이 비어 있거나 입력에 다른 SRID가 있는 경우 **null**을 반환합니다. [Spatial Reference Identifier&#40;SRIDs&#41;](../../relational-databases/spatial/spatial-reference-identifiers-srids.md) 참조  
  
 이 메서드는 **null** 입력을 무시합니다.  
  
> [!NOTE]  
>  이 메서드는 모든 입력 값이 **null**인 경우 **null**을 반환합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 테이블 변수에 있는 **geometry** 개체 집합의 합집합을 반환합니다.  
 ```
 -- Setup table variable for UnionAggregate example 
 DECLARE @Geom TABLE 
 ( 
 shape geometry, 
 shapeType nvarchar(50) 
 ); 
 INSERT INTO @Geom(shape,shapeType) 
 VALUES('CURVEPOLYGON(CIRCULARSTRING(2 3, 4 1, 6 3, 4 5, 2 3))', 'Circle'), 
 ('POLYGON((1 1, 4 1, 4 5, 1 5, 1 1))', 'Rectangle'); 
 -- Perform UnionAggregate on @Geom.shape column 
 SELECT geometry::UnionAggregate(shape).ToString() 
 FROM @Geom;
``` 
  
## <a name="see-also"></a>참고 항목  
 [확장 정적 기하 도형 메서드](../../t-sql/spatial-geometry/extended-static-geometry-methods.md)  
  
  

