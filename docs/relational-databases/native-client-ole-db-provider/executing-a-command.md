---
title: "명령 실행 | Microsoft Docs"
ms.custom: 
ms.date: 03/17/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: native-client-ole-db-provider
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- commands [SQL Server Native Client]
- OLE DB, executing commands
- sessions [SQL Server Native Client]
- OLE DB extensions for XML
- SQL Server Native Client OLE DB provider, command execution
ms.assetid: bb0b3cbf-fe45-46ba-b2ec-c5a39e3c7081
caps.latest.revision: "40"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 9e37688d49155aa0d3735e1be332e41b0ae79447
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="executing-a-command"></a>명령 실행
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  소비자를 호출 하는 데이터 원본에 대 한 연결 설정 되 면는 **idbcreatesession:: Createsession** 메서드 세션을 만들 수 있습니다. 세션은 명령, 행 집합 또는 트랜잭션 팩토리로 작동합니다.  
  
 직접 작업할 개별 테이블이 나 인덱스를 요청 하는 소비자는 **IOpenRowset** 인터페이스입니다. **iopenrowset:: Openrowset** 메서드를 열고 단일 기본 테이블 또는 인덱스에서 모든 행이 포함 된 행 집합을 반환 합니다.  
  
 명령을 실행 하려면 (예: SELECT \* FROM Authors), 소비자의 요청은 **IDBCreateCommand** 인터페이스입니다. 소비자를 실행할 수는 **idbcreatecommand:: Createcommand** 명령 개체를 만들고에 대 한 요청 하는 메서드는 **ICommandText** 인터페이스입니다. **icommandtext:: Setcommandtext** 메서드를 실행 해야 하는 명령을 지정를 사용 합니다.  
  
 **Execute** 명령은 명령을 실행 하는 데 사용 됩니다. SQL 문이나 프로시저 이름은 모두 명령으로 사용할 수 있습니다. 결과 집합(행 집합) 개체를 생성하지 않는 명령도 있습니다. SELECT * FROM Authors와 같은 명령은 결과 집합을 생성합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [SQL Server Native Client OLE DB 공급자 응용 프로그램 만들기](../../relational-databases/native-client-ole-db-provider/creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  