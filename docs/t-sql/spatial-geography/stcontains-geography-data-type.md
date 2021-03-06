---
title: STContains(geography 데이터 형식) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- STContains method (geography)
ms.assetid: b10e8f0a-2926-449a-82ea-be42543420ca
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 9fa8502097b203be8ea6a94f13ebc3eb136e1640
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47824101"
---
# <a name="stcontains--geography-data-type"></a>STContains(geography 데이터 형식)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

  공간적인 **geography** 인스턴스 호출이 메서드로 전달된 **geography** 인스턴스를 포함하는지 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
.STContains ( other_geography )  
```  
  
## <a name="arguments"></a>인수  
 *other_geography*  
 `STContains()`가 호출되는 인스턴스와 비교할 다른 **geography** 인스턴스입니다.  
  
## <a name="return-types"></a>반환 형식  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 반환 형식: **bit**  
  
 CLR 반환 형식: **SqlBoolean**  
  
## <a name="remarks"></a>Remarks  
 공간적으로 **geography** 인스턴스 호출이 인스턴스가 메서드에 전달된 **geography** 인스턴스를 포함할 경우 1을 반환하고, 그렇지 않으면 0을 반환합니다. 두 **geography** 인스턴스의 SRID가 같지 않을 경우 **null**을 반환합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 `STContains()`를 사용하여 두 `geography` 인스턴스를 테스트하여 첫 번째 인스턴스가 두 번째 인스턴스를 포함하는지 확인합니다.  
  
```  
DECLARE @g geography;  
DECLARE @h geography;  
SET @g = geography::Parse('CURVEPOLYGON (COMPOUNDCURVE (CIRCULARSTRING (-122.200928 47.454094, -122.810669 47.00648, -122.942505 46.687131, -121.14624 45.786679, -119.119263 46.183634), (-119.119263 46.183634, -119.273071 47.107523, -120.640869 47.569114, -122.200928 47.454094)))');  
SET @h = geography::Parse('POINT(-121.703796 46.893985)');  
```  
  
 `SELECT @g.STContains(@h);`  
  
  
