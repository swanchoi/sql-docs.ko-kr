---
title: rsModelGenerationError - Reporting Services 오류 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsModelGenerationError
ms.assetid: 3a0ad63f-87f9-4ca1-b0c2-c85fa991634a
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 5a64511c7c44a4fed583c8276b2b4abaff01ee51
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2019
ms.locfileid: "56021934"
---
# <a name="rsmodelgenerationerror---reporting-services-error"></a>rsModelGenerationError - Reporting Services 오류
    
## <a name="details"></a>설명  
  
|||  
|-|-|  
|제품 이름|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|이벤트 ID|rsRenderingError|  
|이벤트 원본|Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings|  
|구성 요소|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|메시지 텍스트|모델을 생성하는 동안 오류가 발생했습니다. (rsModelGenerationError) (ReportingServicesLibrary) %1|  
  
## <a name="explanation"></a>설명  
 보고서 모델을 생성할 수 없습니다.  [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]2005 SP1 및 이전 버전에서 이 오류는 예를 들어 두 개의 외래 키가 한 테이블 내에서 같은 열에 정의되어 있는 경우처럼 System.Data.DataSet 개체가 데이터베이스 스키마 내에서 테이블이나 관계를 처리할 수 없을 경우 주로 표시됩니다.  
  
## <a name="user-action"></a>사용자 동작  
 이러한 메시지를 표시하는 특정 원인을 확인하려면 \Microsoft SQL Server\\<SQL Server Instance\>\Reporting Services\LogFiles에 있는 보고서 서버 로그 파일을 검토하세요.  
  
## <a name="internal-only"></a>내부 전용  
  
