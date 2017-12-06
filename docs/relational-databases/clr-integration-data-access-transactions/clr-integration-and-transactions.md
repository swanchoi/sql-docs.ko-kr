---
title: "CLR 통합 및 트랜잭션 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: clr
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- ADO.NET [CLR integration]
- common language runtime [SQL Server], ADO.NET
- managed code [SQL Server], transactions
- common language runtime [SQL Server], transactions
- System.Transactions namespace
- transactions [CLR integration]
ms.assetid: 381d206e-06e2-48d0-8206-295fcf06ac98
caps.latest.revision: "19"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 91af8f269dce39e8e707c570aba606f743b1a7e6
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="clr-integration-and-transactions"></a>CLR 통합 및 트랜잭션
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]**System.Transactions** 네임 스페이스는 ADO.NET와 완전히 통합 하는 트랜잭션 프레임 워크를 제공 하 고 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 공용 언어 런타임 (CLR) 통합 합니다. **System.Transactions** 와 ADO.NET 함께 작동 하는 관리 되는 응용 프로그램에서 로컬 및 분산 트랜잭션의 사용을 단순화 하 고, 확장 합니다.  
  
> [!NOTE]  
>  CLR UDP(사용자 정의 프로시저)는 해당 프로시저가 실행되는 서버에 대한 연결(루프백 연결)을 설정할 수 없으며 동일한 트랜잭션에 참여할 수도 없습니다. 이러한 작업을 시도하면 연결 시도가 차단되고 제어가 다시 UDP로 전달되지 않습니다. 이 경우 UDP에서 시간 초과 오류(메시지 1206)가 발생합니다.  
  
 트랜잭션 및 .NET Framework에 대한 자세한 내용은 .NET Framework SDK의 "트랜잭션 수행" 및 "트랜잭션 이용"을 참조하십시오.  
  
## <a name="in-this-section"></a>섹션 내용  
 [트랜잭션 승격](../../relational-databases/clr-integration-data-access-transactions/transaction-promotion.md)  
 트랜잭션을 승격하는 기능과 이 기능을 사용하는 방법에 대해 설명합니다.  
  
 [현재 트랜잭션 액세스](../../relational-databases/clr-integration-data-access-transactions/accessing-the-current-transaction.md)  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 현재 in-process으로 실행 중인 트랜잭션에 액세스하는 방법에 대해 설명합니다.  
  
 [System.Transactions 사용](../../relational-databases/clr-integration-data-access-transactions/using-system-transactions.md)  
 사용 하는 방법에 설명 된 **System.Transactions** 관리 되는 응용 프로그램에서 응용 프로그램 프로그래밍 인터페이스 (API).  
  
 [트랜잭션 수명](../../relational-databases/clr-integration-data-access-transactions/transaction-lifetimes.md)  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] 저장 프로시저에서 시작된 트랜잭션과 CLR 응용 프로그램에서 시작된 트랜잭션의 수명 차이에 대해 설명합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [CLR 데이터베이스 개체에서 데이터 액세스](../../relational-databases/clr-integration/data-access/data-access-from-clr-database-objects.md)  
  
  