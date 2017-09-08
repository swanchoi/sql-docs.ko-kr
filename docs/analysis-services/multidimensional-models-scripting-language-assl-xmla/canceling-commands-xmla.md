---
title: "명령 취소 (XMLA) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- connections [XML for Analysis]
- associated connections [XML for Analysis]
- XML for Analysis, canceling
- associated sessions [XML for Analysis]
- canceling connections
- canceling commands
- canceling sessions
- SPID
- XMLA, canceling
- server process IDs [XML for Analysis]
- sessions [XML for Analysis]
ms.assetid: b59f8197-c33d-4e65-9022-848ccba540f5
caps.latest.revision: 12
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: e74ce7bd5b03aa84b6c6580342504148a62a68bf
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="canceling-commands-xmla"></a>명령 취소(XMLA)
  명령을 실행 하는 사용자의 관리 권한에 따라는 [취소](../../analysis-services/xmla/xml-elements-commands/cancel-element-xmla.md) Analysis (XMLA) 세션, 세션, 연결, 서버 프로세스 또는 연관된 된 세션이 명령을 취소할 수에 대 한 xml에서 명령 또는 연결입니다.  
  
## <a name="canceling-commands"></a>명령 취소  
 사용자는 보내어 현재 명시적 세션의 컨텍스트 내에서 현재 실행 중인 명령을 취소할 수 있습니다는 **취소** 명령에 지정 된 속성이 없습니다.  
  
> [!NOTE]  
>  암시적 세션에서 실행 중인 명령은 사용자가 취소할 수 없습니다.  
  
### <a name="canceling-batch-commands"></a>Batch 명령 취소  
 사용자가 취소 한 **일괄 처리** 명령을 선택한 다음 내에서 아직 실행 되는 나머지 모든 명령에서 **일괄 처리** 명령이 취소 됩니다. 경우는 **일괄 처리** 명령이 트랜잭션인, 하기 전에 실행 된 모든 명령은 **취소** 명령 실행 롤백됩니다.  
  
## <a name="canceling-sessions"></a>세션 취소  
 에 명시적 세션의 세션 식별자를 지정 하 여는 [SessionID](../../analysis-services/xmla/xml-elements-properties/sessionid-element-xmla.md) 의 속성은 **취소** 데이터베이스 관리자나 서버 관리자는 세션을 취소할 수 있습니다를 포함 하 여는 현재 실행 중인 명령입니다. 데이터베이스 관리자는 자신이 관리 권한을 가지고 있는 데이터베이스에 대한 세션만을 취소할 수 있습니다.  
  
 데이터베이스 관리자는 DISCOVER_SESSIONS 스키마 행 집합을 검색하여 지정된 데이터베이스의 활성 세션을 검색할 수 있습니다. DISCOVER_SESSIONS 스키마 행 집합을 검색 하려면 데이터베이스 관리자가 사용 하 여 XMLA **Discover** 메서드는 SESSION_CURRENT_DATABASE제한열에대한적절한데이터베이스식별자를지정하고[제한](../../analysis-services/xmla/xml-elements-properties/restrictions-element-xmla.md) 의 속성은 **Discover** 메서드.  
  
## <a name="canceling-connections"></a>연결 취소  
 에 연결 식별자를 지정 하 여는 [ConnectionID](../../analysis-services/xmla/xml-elements-properties/connectionid-element-xmla.md) 의 속성은 **취소** 서버 관리자의 모든 연결 모두를 포함 하 여 지정된 된 연결 된 세션을 취소할 수 있습니다 명령을 실행 하 고 연결을 취소 합니다.  
  
> [!NOTE]  
>  경우 인스턴스의 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 찾아 인스턴스 연결을 취소할 수 없습니다 데이터 펌프가 여러 세션 HTTP 연결을 제공 하는 동안 때와 같은 연결을 통해 연결 된 세션을 취소할 수 없습니다. 실행 하는 동안 이런이 경우가 발생 하는 경우는 **취소** 명령, 오류가 발생 합니다.  
  
 서버 관리자에 대 한 활성 연결을 검색할 수는 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA를 사용 하 여 DISCOVER_CONNECTIONS 스키마 행 집합을 검색 하 여 인스턴스 **Discover** 메서드.  
  
## <a name="canceling-server-processes"></a>서버 프로세스 취소  
 서버 프로세스 식별자 (SPID)를 지정 하 여는 [SPID](../../analysis-services/xmla/xml-elements-properties/spid-element-xmla.md) 의 속성은 **취소** 서버 관리자에 지정된 된 SPID에 연관 된 명령을 취소할 수 있습니다.  
  
## <a name="canceling-associated-sessions-and-connections"></a>연관된 세션 및 연결 취소  
 설정할 수 있습니다는 [CancelAssociated](../../analysis-services/xmla/xml-elements-properties/cancelassociated-element-xmla.md) 속성을 true로 연결, 세션 및 연결 된 연결, 세션 또는 SPID에 지정 된 명령을 취소 하는 **취소** 명령입니다.  
  
## <a name="see-also"></a>관련 항목:  
 [방법 &#40; 검색 XMLA &#41;](../../analysis-services/xmla/xml-elements-methods-discover.md)   
 [Analysis Services에서 XMLA를 사용 하 여 개발](../../analysis-services/multidimensional-models-scripting-language-assl-xmla/developing-with-xmla-in-analysis-services.md)  
  
  