---
title: HOST_NAME (Transact SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- HOST_NAME_TSQL
- HOST_NAME
dev_langs:
- TSQL
helpviewer_keywords:
- HOST_NAME function
- workstation names [SQL Server]
ms.assetid: 4b8b0705-c083-4b07-b954-c83ee73b2ebb
caps.latest.revision: 20
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 1f10245c8a84469877d9f455c2518d7b4ba48173
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="hostname-transact-sql"></a>HOST_NAME(Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  워크스테이션 이름을 반환합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
HOST_NAME ()  
```  
  
## <a name="return-types"></a>반환 형식  
 **nvarchar (128)**  
  
## <a name="remarks"></a>주의  
 시스템 함수의 매개 변수가 선택 사항이면 현재 데이터베이스, 호스트 컴퓨터, 서버 사용자 또는 데이터베이스 사용자를 가정합니다. 기본 제공 함수 다음에는 항상 괄호가 와야 합니다.  
  
 시스템 함수는 선택 목록, WHERE 절 및 식이 허용되는 모든 곳에서 사용될 수 있습니다.  
  
> [!IMPORTANT]  
>  클라이언트 응용 프로그램에서 워크스테이션 이름을 제공하므로 제공된 데이터가 정확하지 않을 수 있습니다. HOST_NAME을 보안 용도로는 사용하지 마세요.  
  
## <a name="examples"></a>예  
 다음 예에서는 `HOST_NAME()` 정의에 `DEFAULT`을 사용하는 테이블을 만들고 주문 기록 테이블에 행을 삽입하는 컴퓨터의 워크스테이션 이름을 새로 만든 테이블에 기록합니다.  
  
```  
CREATE TABLE Orders  
   (OrderID     int        PRIMARY KEY,  
    CustomerID  nchar(5)   REFERENCES Customers(CustomerID),  
    Workstation nchar(30)  NOT NULL DEFAULT HOST_NAME(),  
    OrderDate   datetime   NOT NULL,  
    ShipDate    datetime   NULL,  
    ShipperID   int        NULL REFERENCES Shippers(ShipperID));  
GO  
```  
  
## <a name="see-also"></a>관련 항목:  
 [식 &#40; Transact SQL &#41;](../../t-sql/language-elements/expressions-transact-sql.md)   
 [시스템 함수 &#40; Transact SQL &#41;](../../relational-databases/system-functions/system-functions-for-transact-sql.md)  
  
  