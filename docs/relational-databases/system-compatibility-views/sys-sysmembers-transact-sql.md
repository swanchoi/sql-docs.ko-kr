---
title: sys.sysmembers (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-compatibility-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.sysmembers_TSQL
- sysmembers
- sys.sysmembers
- sysmembers_TSQL
dev_langs: TSQL
helpviewer_keywords:
- sysmembers system table
- sys.sysmembers compatibility view
ms.assetid: ceb18341-f985-4849-ac83-21d67ab7b980
caps.latest.revision: "38"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 4579e8f7b4dfca003d4dcecdda42cb4268fcf369
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2017
---
# <a name="syssysmembers-transact-sql"></a>sys.sysmembers(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  데이터베이스 역할의 각 멤버에 대해 한 행을 포함합니다.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**memberuid**|**smallint**|역할 멤버의 사용자 ID입니다. 사용자 및 역할 수가 32,767을 초과하는 경우 오버플로되거나 NULL을 반환합니다.|  
|**groupuid**|**smallint**|역할의 사용자 ID입니다. 사용자 및 역할 수가 32,767을 초과하는 경우 오버플로되거나 NULL을 반환합니다.|  
  
## <a name="see-also"></a>관련 항목:  
 [시스템 뷰 &#40; 시스템 테이블 매핑 Transact SQL &#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [호환성 뷰&#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  