---
title: Broker 이벤트 범주 | Microsoft 문서
ms.custom: ''
ms.date: 07/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Broker event category
- Broker event category [SQL Server]
- event classes [SQL Server], Broker event category
ms.assetid: 470dc93c-0dda-4d89-829b-937738d59b31
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 9918aca57caaef0dc460e810f5ed5ca2d1106ac3
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52784575"
---
# <a name="broker-event-category"></a>Broker 이벤트 범주
  **Broker** 이벤트 범주에는 일반적인 Service Broker 이벤트가 포함됩니다.  
  
## <a name="in-this-section"></a>섹션 내용  
  
|항목|Description|  
|-----------|-----------------|  
|[Broker:Activation 이벤트 클래스](broker-activation-event-class.md)|큐 모니터가 활성화 저장 프로시저를 시작하는 경우에 생성되는 이벤트입니다.|  
|[Broker:Connection 이벤트 클래스](broker-connection-event-class.md)|Service Broker에서 관리하는 전송 연결 상태를 보고하기 위해 생성되는 이벤트입니다.|  
|[Broker:Conversation 이벤트 클래스](broker-conversation-event-class.md)|대화 진행률을 보고하기 위해 생성되는 이벤트입니다.|  
|[Broker:Conversation Group 이벤트 클래스](broker-conversation-group-event-class.md)|데이터베이스에서 대화 그룹을 만들거나 삭제하는 경우에 생성되는 이벤트입니다.|  
|[Broker:Corrupted Message 이벤트 클래스](broker-corrupted-message-event-class.md)|데이터베이스에서 손상된 메시지를 받았음을 보고하기 위해 생성되는 이벤트입니다.|  
|[Broker:Forwarded Message Dropped 이벤트 클래스](broker-forwarded-message-dropped-event-class.md)|전달되어야 하는 Service Broker 메시지가 SQL Server에서 삭제된 경우 생성되는 이벤트입니다.|  
|[Broker:Forwarded Message Sent 이벤트 클래스](broker-forwarded-message-sent-event-class.md)|SQL Server가 Service Broker 메시지를 전달할 때 생성되는 이벤트입니다.|  
|[Broker:Message Classify 이벤트 클래스](broker-message-classify-event-class.md)|Service Broker가 메시지 라우팅을 지정하는 경우에 생성되는 이벤트입니다.|  
|[Broker:Message Drop 이벤트 클래스](broker-message-drop-event-class.md)|Service Broker가 받은 메시지를 유지할 수 없는 경우에 생성되는 이벤트입니다. 이 메시지는 이 인스턴스의 서비스로 배달되어야 합니다.|  
|[Broker:Remote Message Ack 이벤트 클래스](broker-remote-message-ack-event-class.md)|Service Broker가 메시지 승인을 보내거나 받는 경우에 생성되는 이벤트입니다.|  
  
 두 개의 보안 감사 이벤트도 Service Broker에 제공됩니다. 이러한 이벤트에 대한 자세한 내용은 [Audit Broker Login 이벤트 클래스](audit-broker-login-event-class.md) 및 [Audit Broker Conversation 이벤트 클래스](audit-broker-conversation-event-class.md)를 참조하세요.  
  
## <a name="see-also"></a>관련 항목  
 [Security Audit 이벤트 범주](https://docs.microsoft.com/bi-reference/trace-events/security-audit-event-category)  
  
  
