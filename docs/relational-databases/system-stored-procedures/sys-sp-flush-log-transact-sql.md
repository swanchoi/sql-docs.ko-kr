---
title: sys.sp_flush_log (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
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
- sp_flush_log_TSQL
- sys.sp_flush_log
- sys.sp_flush_log_TSQL
- sp_flush_log
dev_langs: TSQL
helpviewer_keywords: sys.sp_flush_log
ms.assetid: 75cc9f52-3b1f-4754-b1e7-ce0dd3323bc9
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c7085d93310e0f2b5e4f4523fa96ba66b3eaadc7
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2017
---
# <a name="sysspflushlog-transact-sql"></a>sys.sp_flush_log(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  현재 데이터베이스의 트랜잭션 로그를 디스크에 플러시하여 이전에 커밋한 지연된 내구성이 있는 트랜잭션이 모두 강화됩니다.  
  
 성능상의 이점 때문에 지연된 트랜잭션 내구성을 사용하도록 선택하지만 서버 충돌이나 장애 조치(Failover) 시 손실되는 데이터 양에 대한 보장 한도도 필요한 경우 정기적으로 `sys.sp_flush_log`를 실행하십시오. 예를 들어, 손실되는 데이터를 x초 이하로 제한하려는 경우 x초마다 `sp_flush_log`를 실행합니다.  
  
 `sys.sp_flush_log`를 실행하면 이전에 커밋한 지연된 내구성이 있는 트랜잭션이 모두 영구적이 됩니다. 개념 항목을 참조 [트랜잭션 내구성 제어](../../relational-databases/logs/control-transaction-durability.md) 자세한 정보에 대 한 합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```tsql  
  
sys.sp_flush_log  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="return-code-values"></a>반환 코드 값  
 반환 코드 1은 성공을 의미합니다.  다른 값은 실패를 의미합니다.  
  
## <a name="result-sets"></a>결과 집합  
 없음  
  
## <a name="sample-code"></a>예제 코드  
  
```tsql  
.  
EXECUTE sys.sp_flush_log  
  
```  
  
  