---
title: "SMO 프로그램 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: smo
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- Visual Basic [SMO]
- Visual C# [SMO]
- programming [SMO]
- SQL Server Management Objects, programming
- SMO [SQL Server], programming
ms.assetid: 7d2f0bcf-f1ae-45b8-bc3f-7aea4fae7e45
caps.latest.revision: "34"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: cd8d9fa33596bd200816c7d2e65213646c9e8344
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="creating-smo-programs"></a>SMO 프로그램 만들기
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]일반적인 프로그래밍 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) 개체 메서드, 속성 설정 실행 및 컬렉션 조작과 같이 모든 개체를 공유 하는 공통적인 영역이 포함 됩니다.  
  
|항목|Description|  
|-----------|-----------------|  
|[SQL Server 인스턴스에 연결](../../../relational-databases/server-management-objects-smo/create-program/connecting-to-an-instance-of-sql-server.md)|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 인스턴스 연결을 설정하는 가장 기본적인 SMO 프로그램입니다. Windows 인증과 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 인증을 수행하는 방법을 보여 줍니다. [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]의 로컬 및 원격 인스턴스에 연결하는 방법을 보여 주는 예제도 포함되어 있습니다.|  
|[SQL Server 인스턴스에서 연결 끊기](../../../relational-databases/server-management-objects-smo/create-program/disconnecting-from-an-instance-of-sql-server.md)|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 인스턴스에 대한 연결을 끊는 방법을 보여 주는 프로그램입니다.|  
|[메서드 호출](../../../relational-databases/server-management-objects-smo/create-program/calling-methods.md)|이 섹션에서는 일반적인 메서드 호출 방법을 설명합니다. 매개 변수를 사용하는 방법과 <xref:System.Data.DataTable> 개체에 반환된 데이터 테이블을 처리하는 방법을 보여 줍니다. 개체 생성자를 호출 하는 방법 및 호출 하는 방법의 예도 포함 되어는 **복제** 메서드.|  
|[속성 설정 - SMO](../../../relational-databases/server-management-objects-smo/create-program/setting-properties-smo.md)|이 섹션에서는 여러 가지 유형의 속성을 설정하는 방법을 설명합니다. 개체 속성을 설정하고 얻는 방법을 보여 주며, 개체가 생성될 때 개체 속성을 설정하는 예와 개체의 모든 속성을 대상으로 반복을 수행하는 방법도 포함되어 있습니다.|  
|[컬렉션 사용](../../../relational-databases/server-management-objects-smo/create-program/using-collections.md)|개체 컬렉션에 사용되는 기법에 대해 설명하는 여러 프로그램이 포함되어 있습니다. 컬렉션을 사용하여 개체를 참조하는 방법을 보여 줍니다. 컬렉션의 멤버를 대상으로 반복을 수행하는 방법에 대한 예도 포함되어 있습니다.|  
|[SMO 이벤트 처리](../../../relational-databases/server-management-objects-smo/create-program/handling-smo-events.md)|이 섹션에서는 SMO에서 이벤트를 설정하고 처리하는 방법을 설명합니다. 이벤트 처리기를 설정하는 방법과 이벤트 구독을 설정하는 방법에 대한 예가 포함되어 있습니다.|  
|[SMO 예외 처리](../../../relational-databases/server-management-objects-smo/create-program/handling-smo-exceptions.md)|이 섹션에서는 SMO에서 예외를 트래핑하는 방법을 설명합니다. 예외를 포착하는 방법과 내부 예외를 표시하는 방법에 대한 예가 포함되어 있습니다.|  
|[데이터 형식 작업](../../../relational-databases/server-management-objects-smo/create-program/working-with-data-types.md)|이 섹션에서는 여러 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 데이터 형식을 사용하는 방법에 대해 설명합니다. 개체 생성자의 사양으로 데이터 형식을 구성하는 방법을 설명합니다. 기본 생성자를 사용하여 데이터 형식을 만드는 방법에 대한 예도 포함되어 있습니다.|  
|[트랜잭션 사용](../../../relational-databases/server-management-objects-smo/create-program/using-transactions.md)|이 섹션에서는 SMO 프로그램에서 트랜잭션 처리를 구현하는 방법을 설명합니다. SMO 프로그램에서 트랜잭션을 사용하는 방법에 대한 예가 포함되어 있습니다.|  
|[캡처 모드 사용](../../../relational-databases/server-management-objects-smo/create-program/using-capture-mode.md)|이 섹션에서는 SMO 프로그램의 출력을 기록하는 방법을 설명합니다. 예에서는 SMO 프로그램을 나중에 실행하기 위해 [!INCLUDE[tsql](../../../includes/tsql-md.md)] 인스턴스에 전송된 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 문으로 기록합니다.|  
  
  