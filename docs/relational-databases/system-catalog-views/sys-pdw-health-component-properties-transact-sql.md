---
title: sys.pdw_health_component_properties (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: pdw
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66999c0c-dc43-4327-99fb-8366f465e69d
caps.latest.revision: "7"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 66fb48b26de19aca26c9edb41af4cb31b8f0f01b
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="syspdwhealthcomponentproperties-transact-sql"></a>sys.pdw_health_component_properties (Transact SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md.md)]

  장치를 설명 하는 속성을 저장 합니다. 장치 상태 표시 되는 일부 속성 및 일부 속성은 장치 자체에 대해 설명 합니다.  
  
|열 이름|데이터 형식|Description|범위|  
|-----------------|---------------|-----------------|-----------|  
|property_id|**int**|구성 요소 속성의 고유 식별자입니다.<br /><br /> 속성 id와 component_id이이 보기에 대 한 키를 형성 합니다.|NOT  NULL|  
|component_id|**int**|구성 요소의 ID입니다. 참조 [sys.pdw_health_components &#40; Transact SQL &#41; ](../../relational-databases/system-catalog-views/sys-pdw-health-components-transact-sql.md).<br /><br /> 속성 id와 component_id이이 보기에 대 한 키를 형성 합니다.|NOT  NULL|  
|property_name|**nvarchar(255)**|속성의 이름입니다.|NOT  NULL|  
|physical_name|**nvarchar (32)**|제조업체에서 정의 된 속성 이름입니다.|NOT  NULL|  
|is_key|**bit**|장치 인스턴스가 고유한 지 여부를 결정 합니다.|NOT  NULL<br /><br /> 0-장치 인스턴스는 고유 합니다.<br /><br /> 1-장치 인스턴스 고유 하지 않습니다.|  
  
## <a name="see-also"></a>관련 항목:  
 [SQL 데이터 웨어하우스 및 병렬 데이터 웨어하우스 카탈로그 뷰](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)  
  
  