---
title: sys.views (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- views_TSQL
- views
- sys.views_TSQL
- sys.views
dev_langs: TSQL
helpviewer_keywords: sys.views catalog view
ms.assetid: f8a8ea39-5a09-4662-801e-b43519467def
caps.latest.revision: "28"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 99f0d003eb304a88f4a2fa656b5ed4e658b1b040
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="sysviews-transact-sql"></a>sys.views(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  포함 하는 각 보기 개체에 대 한 행 **sys.objects.type** = V.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**\<열을 상속 >**||이 뷰가 상속 하는 열 목록은 참조 [sys.objects&#40; Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md)|  
|**is_replicated**|**bit**|1 = 뷰가 복제됩니다.|  
|**has_replication_filter**|**bit**|1 = 뷰에 복제 필터가 있습니다.|  
|**has_opaque_metadata**|**bit**|1 = 뷰에 VIEW_METADATA 옵션이 지정되었습니다. 자세한 내용은 [CREATE VIEW&#40;Transact-SQL&#41;](../../t-sql/statements/create-view-transact-sql.md)를 참조하세요.|  
|**has_unchecked_assembly_data**|**bit**|1 = 뷰는 마지막 ALTER ASSEMBLY 중에 해당 정의가 변경된 어셈블리에 의존하는 데이터를 포함합니다. 다음 번에 DBCC CHECKDB 또는 DBCC CHECKTABLE이 성공적으로 수행된 후에 0으로 다시 설정합니다.|  
|**with_check_option**|**bit**|1 = 뷰 정의에 WITH CHECK OPTION이 지정되었습니다.|  
|**is_date_correlation_view**|**bit**|1 = datetime 열 간 상관 관계 정보를 저장하기 위한 뷰가 시스템에서 자동으로 생성됩니다. DATE_CORRELATION_OPTIMIZATION을 ON으로 설정하여 이 뷰를 생성하도록 설정했습니다.|  
  
## <a name="permissions"></a>Permissions  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 자세한 내용은 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)을 참조하세요.  
  
## <a name="see-also"></a>관련 항목:  
 [개체 카탈로그 뷰 &#40; Transact SQL &#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [카탈로그 뷰&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [ALTER assembly&#40; Transact SQL &#41;](../../t-sql/statements/alter-assembly-transact-sql.md)   
 [DBCC CHECKDB&#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-checkdb-transact-sql.md)   
 [DBCC CHECKTABLE&#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-checktable-transact-sql.md)   
 [SQL Server 시스템 카탈로그 쿼리 FAQ](../../relational-databases/system-catalog-views/querying-the-sql-server-system-catalog-faq.md)  
  
  