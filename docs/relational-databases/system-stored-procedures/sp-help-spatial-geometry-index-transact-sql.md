---
title: sp_help_spatial_geometry_index (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_help_spatial_geometry_index
- sp_help_spatial_geometry_index_TSQL
dev_langs: TSQL
helpviewer_keywords: sp_help_spatial_geometry_index procedure
ms.assetid: f1bcefb1-09c8-4b49-8c51-5d471065849f
caps.latest.revision: "13"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: b91735734ed05f6132dbebb7ca7eaf5a26f703fa
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2017
---
# <a name="sphelpspatialgeometryindex-transact-sql"></a>sp_help_spatial_geometry_index(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  에 대 한 이름 및 지정된 된 속성 집합에 대 한 값을 반환는 **geometry** 공간 인덱스입니다. 결과는 테이블 형식으로 반환됩니다. 인덱스의 핵심 속성 집합만 반환하거나 인덱스의 속성을 모두 반환하도록 선택할 수 있습니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_help_spatial_geometry_index [ @tabname =] 'tabname'   
     [ , [ @indexname = ] 'indexname' ]   
     [ , [ @verboseoutput = ] 'verboseoutput'   
     [ , [ @query_sample = ] 'query_sample']   
```  
  
## <a name="arguments"></a>인수  
 참조 [인수 및 공간 인덱스의 속성에 대 한 저장 프로시저](../../relational-databases/system-stored-procedures/spatial-index-stored-procedures-arguments-and-properties.md)합니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 참조 [인수 및 공간 인덱스의 속성에 대 한 저장 프로시저](../../relational-databases/system-stored-procedures/spatial-index-stored-procedures-arguments-and-properties.md)합니다.  
  
## <a name="permissions"></a>Permissions  
 사용자가 이 프로시저에 액세스하려면 PUBLIC 역할을 할당받아야 합니다. 서버 및 개체에 대한 READ ACCESS 권한이 필요합니다.  
  
## <a name="remarks"></a>주의  
 NULL 값이 포함된 속성은 반환 집합에 포함되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `sp_help_spatial_geometry_index` 공간 인덱스를 조사 하려면 **SIndx_SpatialTable_geometry_col2** 테이블에 정의 된 **geometry_col** 지정된 쿼리 샘플에 대 한  **@qs** . 이 예에서는 지정된 인덱스의 핵심 속성만 반환합니다.  
  
```  
declare @qs geometry  
        ='POLYGON((-90.0 -180.0, -90.0 180.0, 90.0 180.0, 90.0 -180.0, -90.0 -180.0))';  
exec sp_help_spatial_geometry_index 'geometry_col', 'SIndx_SpatialTable_geometry_col2', 0, @qs;  
```  
  
## <a name="see-also"></a>관련 항목:  
 [공간 인덱스 저장 프로시저](http://msdn.microsoft.com/library/1be0f34e-3d5a-4a1f-9299-bd482362ec7a)   
 [sp_help_spatial_geometry_index_xml](../../relational-databases/system-stored-procedures/sp-help-spatial-geometry-index-xml-transact-sql.md)   
 [공간 인덱스 개요](../../relational-databases/spatial/spatial-indexes-overview.md)   
 [공간 데이터&#40;SQL Server&#41;](../../relational-databases/spatial/spatial-data-sql-server.md)  
  
  