---
title: "기능 &#39; CLR 통합의 새로운 s | Microsoft Docs"
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: clr
ms.reviewer: 
ms.suite: sql
ms.custom: 
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 871fcccd-b726-4b13-9f95-d02b4b39d8ab
caps.latest.revision: "7"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 787552c5a10579e90a0ab62e9105172f989357f5
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="clr-integration---what39s-new"></a>CLR 통합 기능 &#39; 새로운
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]다음은 CLR 통합에 대 한 새로운 기능 [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]:  
  
-   CLR 버전 4에서는 CLR 데이터베이스 개체가 더 이상 손상된 상태 예외를 catch하지 않습니다. 이러한 예외는 이제 CLR 통합 호스팅 계층에서 catch됩니다. 이러한 예외 수 코드 특성을 설정 하 여 여전히 CLR 데이터베이스 구성 요소에 의해 발생 하는 수 ([\<legacyCorruptedStateExceptionsPolicy > 요소](http://go.microsoft.com/fwlink/?LinkId=204954)). 그러나 손상된 상태 예외가 발생할 때 결과를 신뢰할 수 없으므로 이 방법은 사용하지 않는 것이 좋습니다.  
  
-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]의 엄격한 보안 요구 사항으로 인해 CLR 데이터베이스 구성 요소가 CLR 버전 2.0에 정의된 코드 액세스 보안 모델을 계속해서 사용합니다.  
  
-   Clr 버전 4에 형식 오류가 **System.TimeSpan** 값이 생성 됩니다는 **System.FormatExceptions**합니다. 이전에 형식 오류가 clr 버전 4는 **System.TimeSpan** 값 무시 되었습니다. Clr 버전 4 이전의 동작에 의존 하는 데이터베이스 응용 프로그램이 데이터베이스 호환성 수준으로 실행 됩니다 (**ALTER DATABASE 호환성 수준**) 100이 하입니다. 자세한 내용은 참조 [< TimeSpan_LegacyFormatMode > 요소](http://go.microsoft.com/fwlink/?LinkId=205109)합니다.  
  
-   CLR 버전 4는 유니코드 5.1을 지원하므로 일부 악센트 표시 및 기호가 관련된 정렬 작업이 개선됩니다. 응용 프로그램이 레거시 정렬 동작에 의존하는 경우에는 호환성 문제가 발생할 수 있습니다. 레거시 정렬을 데이터베이스 호환성 수준을 사용 하도록 설정 하려면 (**ALTER DATABASE 호환성 수준**) 100 이하로 설정 해야 합니다. 이를 지원하기 위해 [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]에서는 .NET Framework 4 디렉터리(C:\Windows\Microsoft.NET\Framework\v4.0.30319)에 sort00001000.dll을 설치합니다. 자세한 내용은 참조 [ \<CompatSortNLSVersion > 요소](http://go.microsoft.com/fwlink/?LinkId=205110)합니다.  
  
-   다음과 같은 열에 추가 된 [sys.dm_clr_appdomains](../../relational-databases/system-dynamic-management-views/sys-dm-clr-appdomains-transact-sql.md): **total_processor_time_ms**, **total_allocated_memory_kb**, 및 **survived_ memory_kb**합니다.  
  
  