---
title: 일반 연결 및 컨텍스트 연결 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: a1dead02-be88-4b16-8cb2-db1284856764
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: f4255e17f7cd76cf402c10d84b015a1324d7d6f1
ms.sourcegitcommit: 2429fbcdb751211313bd655a4825ffb33354bda3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "52534220"
---
# <a name="regular-vs-context-connections"></a>일반 연결 및 컨텍스트 연결
  원격 서버에 연결할 때는 컨텍스트 연결 대신 항상 일반 연결을 사용하십시오. 컨텍스트 연결은 대개 저장 프로시저나 함수가 실행 중인 동일한 서버에 연결해야 하는 경우 사용합니다. 컨텍스트 연결을 사용하면 동일한 트랜잭션 공간에서 실행되므로 다시 인증할 필요가 없다는 장점이 있습니다.  
  
 또한 성능이 향상되고 리소스 사용량이 줄어드는 이점도 있습니다. 컨텍스트 연결은 프로세스 전용 연결 이므로 TRANSACT-SQL 문을 보내고 결과 받을 네트워크 프로토콜 및 전송 계층을 무시 하 여 "직접" 서버 연결 수입니다. 인증 프로세스도 무시됩니다. 다음 그림에서는 `SqlClient` 관리 공급자의 주요 구성 요소와 함께 일반 연결을 사용할 때와 컨텍스트 연결을 사용할 때 다양한 구성 요소가 서로 어떻게 상호 작용하는지 보여 줍니다.  
  
 ![컨텍스트 및 일반 연결의 코드 경로입니다. ](../../../database-engine/dev-guide/media/clrintdataaccess.gif "코드 컨텍스트 및 일반 연결에 대 한 경로입니다.")  
  
 컨텍스트 연결은 보다 짧은 코드 경로를 따르고 관련되는 구성 요소가 적으므로 일반 연결보다 빠르게 서버로 요청을 보내고 결과를 받을 수 있습니다. 서버의 쿼리 실행 시간은 컨텍스트 연결을 사용할 때와 일반 연결을 사용할 때 모두 같습니다.  
  
 동일한 서버에 대해 별도의 일반 연결을 열어야 하는 경우도 있습니다. 예를 들어에 설명 된 컨텍스트 연결을 사용 하 여 특정 제한 사항이 [일반 및 컨텍스트 연결에 대 한 제한](context-connections-and-regular-connections-restrictions.md)합니다.  
  
## <a name="see-also"></a>관련 항목  
 [컨텍스트 연결](context-connection.md)  
  
  
