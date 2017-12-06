---
title: "CLR 사용자 정의 집계에 대 한 요구 사항 | Microsoft Docs"
ms.custom: 
ms.date: 03/17/2017
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
- aggregate functions [CLR integration]
- user-defined types [CLR integration], user-defined aggregates
- CREATE AGGREGATE statement
- SqlUserDefinedAggregate attribute
- aggregate methods [CLR integration]
- assemblies [CLR integration], user-defined aggregate functions
- custom aggregates [CLR integration]
- user-defined functions [CLR integration]
- UDTs [CLR integration], user-defined aggregates
ms.assetid: dbf9eb5a-bd99-42f7-b275-556d0def045d
caps.latest.revision: "56"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: a46a1a0e60c7fbe667904388a4c1c8cae93ab827
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="clr-user-defined-aggregates---requirements"></a>CLR 사용자 정의 집계-요구 사항
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]필요한 집계 계약을 구현 하 고 공용 언어 런타임 (CLR) 어셈블리의 형식으로 사용자 정의 집계 함수를 등록할 수 있습니다. 이 계약은 이루어져는 **SqlUserDefinedAggregate** 특성과 집계 계약 메서드로 합니다. 집계 계약은 집계의 중간 상태를 저장 하는 메커니즘 및 메커니즘과 새 값을 누적 하는 메커니즘을 포함: **Init**, **Accumulate**,  **병합**, 및 **종료**합니다. 이러한 요구 사항을 충족할 경우에 사용자 정의 집계를 완전히 활용 할 수 있습니다 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]합니다. 이 항목의 다음 섹션에서는 사용자 정의 집계를 만드는 방법과 사용하는 방법에 대한 자세한 정보를 제공합니다. 예를 들어 참조 [Invoking CLR User-Defined 집계 함수](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregate-invoking-functions.md)합니다.  
  
## <a name="sqluserdefinedaggregate"></a>SqlUserDefinedAggregate  
 자세한 내용은 참조 [SqlUserDefinedAggregateAttribute](http://go.microsoft.com/fwlink/?LinkId=124626)합니다.  
  
## <a name="aggregation-methods"></a>집계 메서드  
 사용자 정의 집계로 등록된 클래스는 다음과 같은 인스턴스 메서드를 지원해야 합니다. 쿼리 프로세서는 이러한 메서드를 사용하여 집계를 계산합니다.  
  
|메서드|구문|Description|  
|------------|------------|-----------------|  
|**초기화**|`public void Init();`|쿼리 프로세서는 이 메서드를 사용하여 집계 계산을 초기화합니다. 이 메서드는 쿼리 프로세서가 집계하는 각 그룹에 대해 한 번씩 호출됩니다. 쿼리 프로세서는 여러 그룹의 집계를 계산할 때 집계 클래스의 동일한 인스턴스를 다시 사용할 수 있습니다. **Init** 메서드가 인스턴스의 이전 사용에서 필요에 따라 정리를 수행 하 고 새 집계 계산을 다시 시작 되도록 설정 합니다.|  
|**누적**|`public void Accumulate ( input-type value[, input-type value, ...]);`|함수의 매개 변수를 나타내는 1개 이상의 매개 변수. *input_type* 관리 되는 해야 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터 형식에 해당 하는 네이티브 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에서 지정한 데이터 형식 *input_sqltype* 에 **CREATE AGGREGATE** 문 . 자세한 내용은 참조 [CLR 매개 변수 데이터 매핑](../../relational-databases/clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md)합니다.<br /><br /> UDT(사용자 정의 형식)의 경우 input-type이 UDT 형식과 동일합니다. 쿼리 프로세서는 이 메서드를 사용하여 집계 값을 누적시킵니다. 이 메서드는 집계되는 그룹의 각 값에 대해 한 번씩 호출됩니다. 쿼리 프로세서는 항상이 호출 호출한 후에는 **Init** 집계 클래스의 특정 인스턴스에서 메서드. 이 메서드 구현은 전달되는 인수 값의 누적을 반영하도록 인스턴스 상태를 업데이트해야 합니다.|  
|**병합**|`public void Merge( udagg_class value);`|이 메서드를 사용하여 이 집계 클래스의 다른 인스턴스를 현재 인스턴스와 병합할 수 있습니다. 쿼리 프로세서는 이 메서드를 사용하여 집계의 다중 부분 계산을 병합합니다.|  
|**종료**|`public return_type Terminate();`|이 메서드는 집계 계산을 완료하고 집계 결과를 반환합니다. *return_type* 관리 되는 해야 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터 형식에 해당 하는 관리 되는 *return_sqltype* 에 지정 된는 **CREATE AGGREGATE** 문. *return_type* 사용자 정의 형식을 수도 있습니다.|  
  
### <a name="table-valued-parameters"></a>테이블 반환 매개 변수  
 프로시저 또는 함수로 전달되는 사용자 정의 테이블 형식인 TVP(테이블 반환 매개 변수)를 사용하면 여러 개의 데이터 행을 서버로 편리하게 전달할 수 있습니다. TVP는 매개 변수 배열과 유사한 기능을 제공하지만 더 유연하며 [!INCLUDE[tsql](../../includes/tsql-md.md)]과 더 밀접하게 통합됩니다. 또한 성능도 향상될 수 있습니다. TVP는 또한 서버와의 왕복 횟수를 줄이는 데 도움이 될 수 있습니다. 스칼라 매개 변수 목록과 같이 서버로 여러 개의 요청을 보내는 대신 서버에 데이터를 TVP로 보낼 수 있습니다. 사용자 정의 테이블 형식은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 프로세스에서 실행 중인 관리되는 저장 프로시저 또는 함수에 테이블 반환 매개 변수로 전달되거나 이러한 저장 프로시저 또는 함수에서 테이블 반환 매개 변수로 반환될 수 없습니다. 또한 컨텍스트 연결의 범위 내에서 TVP를 사용할 수 없습니다. 하지만 컨텍스트 연결이 아닌 연결에 사용되는 경우 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 프로세스에서 실행하는 관리되는 저장 프로시저나 함수에서 SqlClient와 함께 TVP를 사용할 수 있습니다. 이 경우 관리되는 프로시저나 함수를 실행하는 서버와 동일한 서버에 연결될 수 있습니다. Tvp에 대 한 자세한 내용은 참조 [테이블 반환 매개 변수 &#40; 데이터베이스 엔진 &#41;](../../relational-databases/tables/use-table-valued-parameters-database-engine.md)합니다.  
  
## <a name="change-history"></a>변경 내역  
  
|업데이트된 내용|  
|---------------------|  
|설명을 업데이트는 **Accumulate** 메서드의 이제 둘 이상의 매개 변수를 허용 합니다.|  
  
## <a name="see-also"></a>관련 항목:  
 [CLR 사용자 정의 형식](../../relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types.md)   
 [CLR 사용자 정의 집계 함수 호출](../../relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregate-invoking-functions.md)  
  
  