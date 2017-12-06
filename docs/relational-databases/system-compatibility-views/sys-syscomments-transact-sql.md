---
title: sys.syscomments (Transact SQL) | Microsoft Docs
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
- sys.syscomments_TSQL
- syscomments
- syscomments_TSQL
- sys.syscomments
dev_langs: TSQL
helpviewer_keywords:
- sys.syscomments compatibility view
- syscomments system table
ms.assetid: 767dd410-6bc9-4c4a-ab0f-6d2cf6163426
caps.latest.revision: "53"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 5c9b5a5269025f6ed9c3bed493b71a6be557dc25
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2017
---
# <a name="syssyscomments-transact-sql"></a>sys.syscomments(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  데이터베이스 내의 각 뷰,  규칙,  기본값,  트리거,  CHECK  제약 조건,  DEFAULT  제약 조건 및 저장 프로시저에 대한 항목을 포함합니다. **텍스트** 열 원본 SQL 정의 문을 포함 합니다.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] 대신 sys.sql_modules를 사용하는 것이 좋습니다. 자세한 내용은 참조 [sys.sql_modules&#40; Transact SQL &#41; ](../../relational-databases/system-catalog-views/sys-sql-modules-transact-sql.md).  
  
|열 이름|데이터 형식|설명|  
|-----------------|---------------|-----------------|  
|**id**|**int**|해당 텍스트를 적용할 개체 ID입니다.|  
|**번호**|**smallint**|그룹화된 경우에 프로시저 그룹 내의 번호입니다.<br /><br /> 0  =  항목이 프로시저가 아닙니다.|  
|**열 id**|**smallint**|4,000자보다 긴 개체 정의의 행 시퀀스 번호입니다.|  
|**상태**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**ctext**|**varbinary (8000)**|SQL  정의 문의 원시 바이트입니다.|  
|**texttype**|**smallint**|0  =  사용자 제공 설명<br /><br /> 1  =  시스템 제공 설명<br /><br /> 4  =  암호화된 설명|  
|**언어**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**암호화**|**bit**|프로시저 정의가 난독 처리되었는지 여부를 나타냅니다.<br /><br /> 0  =  난독 처리되지 않음<br /><br /> 1  =  난독 처리됨<br /><br /> **\*\*중요 한 \* \***  저장된 프로시저 정의 난독 처리를 사용 하 여 CREATE PROCEDURE에 ENCRYPTION 키워드입니다.|  
|**압축**|**bit**|항상 0을 반환합니다. 이것은 프로시저가 압축되었음을 의미합니다.|  
|**text**|**nvarchar(4000)**|SQL  정의 문의 실제 텍스트입니다.<br /><br /> 디코딩된 식의 의미 체계는 원본 텍스트와 동일하지만 구문은 일치하지 않을 수 있습니다. 예를 들어 공백은 디코딩된 식에서 제거됩니다.<br /><br /> 이 [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]-호환 뷰는 현재에서 정보를 가져오고 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 구조 및 보다 많은 문자를 반환할 수 있습니다는 **nvarchar (4000)** 정의 합니다. **sp_help** 반환 **nvarchar (4000)** 텍스트 열의 데이터 형식으로 합니다. 작업할 때 **syscomments** 를 사용 하는 것이 좋습니다 **nvarchar (max)**합니다. 새로운 개발 작업에서는 사용 하지 마십시오 **syscomments**합니다.|  
  
## <a name="see-also"></a>관련 항목:  
 [시스템 뷰 &#40; 시스템 테이블 매핑 Transact SQL &#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [호환성 뷰&#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  