---
title: '@@PACKET_ERRORS (Transact SQL) | Microsoft Docs'
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '@@PACKET_ERRORS'
- '@@PACKET_ERRORS_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- '@@PACKET_ERRORS function'
- number of packet errors
- packets [SQL Server], errors
- networking [SQL Server], packet errors
- connections [SQL Server], packets
ms.assetid: f7da1b80-5cbe-42fa-be71-40c6af16383a
caps.latest.revision: 31
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 612ab7e2ac7f0969263bbd21d6b875ed83bbe5e1
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="packeterrors-transact-sql"></a>@@PACKET_ERRORS (Transact SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]가 마지막으로 시작된 이후 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 연결에서 발생한 네트워크 패킷 오류 수를 반환합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
@@PACKET_ERRORS  
```  
  
## <a name="return-types"></a>반환 형식  
 **integer**  
  
## <a name="remarks"></a>주의  
 몇 가지를 포함 하는 보고서를 표시 하려면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 실행 통계, 패킷 오류를 포함 한 **sp_monitor**합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 `@@PACKET_ERRORS`를 사용하는 방법을 보여 줍니다.  
  
```  
SELECT @@PACKET_ERRORS AS 'Packet Errors';  
```  
  
 결과 집합의 예는 다음과 같습니다.  
  
```  
Packet Errors  
-------------  
0  
```  
  
## <a name="see-also"></a>관련 항목:  
 [@@PACK_RECEIVED&#40;Transact-SQL&#41;](../../t-sql/functions/pack-received-transact-sql.md)   
 [@@PACK_SENT&#40;Transact-SQL&#41;](../../t-sql/functions/pack-sent-transact-sql.md)   
 [sp_monitor &#40; Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-monitor-transact-sql.md)   
 [시스템 통계 함수 &#40; Transact SQL &#41;](../../t-sql/functions/system-statistical-functions-transact-sql.md)  
  
  