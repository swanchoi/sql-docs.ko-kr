---
title: "뷰 (TRANSACT-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: system-information-schema-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VIEWS_TSQL
- VIEWS
dev_langs: TSQL
helpviewer_keywords:
- VIEWS view
- INFORMATION_SCHEMA.VIEWS view
ms.assetid: 6119bc94-0b22-45d4-a34b-967afd810a9d
caps.latest.revision: "39"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 6fdfae119d9ed1c214c745de30f019588f47e1a2
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="views-transact-sql"></a>VIEWS(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  현재 데이터베이스에서 현재 사용자가 액세스할 수 있는 각 뷰당 하나의 행을 반환합니다.  
  
 이러한 뷰에서 정보를 검색 하려면의 정규화 된 이름을 지정 **INFORMATION_SCHEMA.** *view_name*합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**TABLE_CATALOG**|**nvarchar (**128**)**|뷰 한정자입니다.|  
|**TABLE_SCHEMA**|**nvarchar (**128**)**|뷰가 포함된 스키마의 이름입니다.<br /><br /> **\*\*중요 한 \* \***  개체의 스키마를 확인 하려면 INFORMATION_SCHEMA 뷰를 사용 하지 마십시오. 개체의 스키마를 확인하는 신뢰할 수 있는 유일한 방법은 sys.objects 카탈로그 뷰를 쿼리하는 것입니다.|  
|**TABLE_NAME**|**nvarchar (**128**)**|뷰 이름입니다.|  
|**VIEW_DEFINITION**|**nvarchar (**4000**)**|정의의 길이 보다 큰 경우 **nvarchar (**4000**)**,이 열은 NULL입니다. 그렇지 않으면 이 열은 뷰 정의 텍스트입니다.|  
|**CHECK_OPTION**|**varchar (**7**)**|WITH CHECK OPTION의 유형입니다. 원래 뷰를 WITH CHECK OPTION으로 만든 경우에는 CASCADE입니다. 그렇지 않으면 NONE이 반환됩니다.|  
|**IS_UPDATABLE**|**varchar (**2**)**|뷰를 업데이트할 수 있는지 여부를 지정합니다. 항상 NO를 반환합니다.|  
  
## <a name="see-also"></a>관련 항목:  
 [시스템 뷰 &#40; Transact SQL &#41;](http://msdn.microsoft.com/library/35a6161d-7f43-4e00-bcd3-3091f2015e90)   
 [정보 스키마 뷰 &#40; Transact SQL &#41;](~/relational-databases/system-information-schema-views/system-information-schema-views-transact-sql.md)   
 [sys.sql_modules&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-sql-modules-transact-sql.md)   
 [sys.views&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-views-transact-sql.md)  
  
  