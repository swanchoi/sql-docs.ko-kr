---
title: 잠금 및 데이터베이스 (XMLA)를 잠금 해제 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- locking [XML for Analysis]
- XML for Analysis, locking
- XMLA, locking
- unlocking objects
ms.assetid: 451afa58-ce03-4ecc-8dd3-9e7e8559b5f1
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: e1f518f846a6e0bb87f858d7a5798eb9a7e9c8d0
ms.sourcegitcommit: 7fe14c61083684dc576d88377e32e2fc315b7107
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2018
ms.locfileid: "50146278"
---
# <a name="locking-and-unlocking-databases-xmla"></a>데이터베이스 잠금 및 잠금 해제(XMLA)
  잠금 및 각각 사용 하는 데이터베이스 잠금 해제, [잠금을](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/lock-element-xmla) 및 [잠금 해제](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/lock-element-xmla) xml for Analysis (XMLA) 명령입니다. 일반적으로 다른 XMLA 명령은 실행 중 해당 명령을 수행하는 데 필요할 경우 자동으로 개체를 잠그거나 잠금 해제합니다. 수 명시적으로 잠그거나 잠금을 해제할 데이터베이스와 같은 단일 트랜잭션 내에서 여러 명령을 수행 하는 [일괄 처리](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/batch-element-xmla) 다른 응용 프로그램에서 데이터베이스에 쓰기 트랜잭션을 커밋하지 못하게 하는 동안 명령입니다.  
  
## <a name="locking-databases"></a>데이터베이스 잠금  
 `Lock` 명령은 현재 활성 트랜잭션 컨텍스트 내에서 공유되거나 배타적으로 사용되는 개체를 잠급니다. 개체가 잠겨 있으면 잠금을 해제할 때까지 트랜잭션을 커밋할 수 없습니다. [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 두 가지 유형의 잠금, 공유 잠금과 배타적 잠금을 지원합니다. 지 원하는 잠금 유형에 대 한 자세한 내용은 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]를 참조 하세요 [Mode 요소 &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/mode-element-xmla)합니다.  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]는 데이터베이스 잠금만 허용합니다. [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) 요소는 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 데이터베이스에 대한 개체 참조를 포함해야 합니다. `Object` 요소를 지정하지 않거나 `Object` 요소가 데이터베이스 이외의 개체를 참조하면 오류가 발생합니다.  
  
> [!IMPORTANT]  
>  데이터베이스 관리자 또는 서버 관리자만 명시적으로 `Lock` 명령을 실행할 수 있습니다.  
  
 다른 명령을 실행하면 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 데이터베이스에서 `Lock` 명령이 암시적으로 실행됩니다. 데이터베이스의 데이터 또는 메타데이터를 읽는 작업(예: [Discover](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) 명령을 실행하는 [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) 메서드 또는 [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) 메서드)을 수행하면 데이터베이스에서 암시적으로 공유 잠금이 실행됩니다. 개체의 데이터 또는 메타 데이터 변경을 커밋하는 트랜잭션을 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 데이터베이스와 같은 `Execute` 실행 하는 메서드는 [Alter](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) 명령에 암시적으로 데이터베이스에 대 한 배타적 잠금을입니다.  
  
## <a name="unlocking-objects"></a>개체 잠금 해제  
 `Unlock` 명령은 현재 활성 트랜잭션 컨텍스트 내에서 설정된 잠금을 제거합니다.  
  
> [!IMPORTANT]  
>  데이터베이스 관리자 또는 서버 관리자만 명시적으로 `Unlock` 명령을 실행할 수 있습니다.  
  
 모든 잠금은 현재 트랜잭션의 컨텍스트에 유지됩니다. 현재 트랜잭션이 커밋 또는 롤백되면 해당 트랜잭션 내에 정의된 모든 잠금이 자동으로 해제됩니다.  
  
## <a name="see-also"></a>관련 항목  
 [요소를 잠급니다 &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/lock-element-xmla)   
 [요소 잠금 해제 &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/lock-element-xmla)   
 [Analysis Services에서 XMLA를 사용하여 개발](developing-with-xmla-in-analysis-services.md)  
  
  
