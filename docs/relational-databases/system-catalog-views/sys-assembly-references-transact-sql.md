---
title: sys.assembly_references (TRANSACT-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- assembly_references
- sys.assembly_references_TSQL
- assembly_references_TSQL
- sys.assembly_references
dev_langs:
- TSQL
helpviewer_keywords:
- sys.assembly_references catalog view
ms.assetid: 50a5ed42-2d5b-4a11-a0d2-9a02241b078d
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: c14010d0472d8ed72418c30d7b6c34af1fc9dc65
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47626003"
---
# <a name="sysassemblyreferences-transact-sql"></a>sys.assembly_references(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  하나가 다른 하나를 직접 참조하는 각 쌍의 어셈블리당 한 개의 행을 포함합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**assembly_id**|**int**|이 참조가 속한 어셈블리의 ID입니다.|  
|**referenced_assembly_id**|**int**|참조되는 어셈블리의 ID입니다.|  
  
## <a name="permissions"></a>사용 권한  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 자세한 내용은 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)을 참조하세요.  
  
## <a name="see-also"></a>관련 항목  
 [CLR 어셈블리 카탈로그 뷰 &#40;TRANSACT-SQL&#41;](../../relational-databases/system-catalog-views/clr-assembly-catalog-views-transact-sql.md)   
 [카탈로그 뷰&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [ASSEMBLYPROPERTY &#40;TRANSACT-SQL&#41;](../../t-sql/functions/assemblyproperty-transact-sql.md)  
  
  
