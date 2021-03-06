---
title: 백업 압축 구성(SQL Server) | Microsoft 문서
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 430905eb-d218-458c-bd48-aeee6fbb7446
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: bcfc0dea167b972f4e463333ab6851b038a284ed
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48062810"
---
# <a name="configure-backup-compression-sql-server"></a>백업 압축 구성(SQL Server)
  설치 시 백업 압축은 기본적으로 설정되지 않습니다. 백업 압축의 기본 동작은 **백업 압축 기본값** 옵션 서버 수준 구성 옵션에 의해 정의됩니다. 그러나 단일 백업을 만들거나 일련의 일상적인 백업을 예약할 때 서버 수준 기본값을 재정의할 수 있습니다. 서버 수준 기본값을 변경하려면 [백업 압축 기본값 서버 구성 옵션 보기 또는 구성](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)을 참조하세요.  
  
## <a name="override-the-backup-compression-default"></a>백업 압축 기본값 재정의  
 단일 백업, 백업 작업 또는 로그 전달 구성에 대한 백업 압축 동작을 변경할 수 있습니다.  
  
-   **[!INCLUDE[tsql](../../includes/tsql-md.md)]**  
  
     백업을 만들 때 서버 백업 압축 기본값을 재정의하려면 [BACKUP](/sql/t-sql/statements/backup-transact-sql) 문에서 WITH NO_COMPRESSION 또는 WITH COMPRESSION을 사용합니다.  
  
     로그 전달 구성의 경우 [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql)[sp_change_log_shipping_primary_database&#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-log-shipping-primary-database-transact-sql)를 사용하여 로그 백업의 백업 압축 동작을 제어할 수 있습니다.  
  
-   **[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**  
  
     [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스에 대한 백업 압축 기본 옵션을 보거나 구성하는 방법은 [백업 압축 기본값 서버 구성 옵션 보기 또는 구성](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)을 참조하세요.  
  
     다음 대화 상자에서 **백업 압축** 또는 **백업 압축 안 함** 을 지정하여 백업을 만들 때 서버 백업 압축 기본값을 재정의할 수 있습니다.  
  
    -   [데이터베이스 백업(옵션 페이지)](back-up-database-backup-options-page.md)  
  
         데이터베이스를 백업할 때 개별 데이터베이스, 파일 또는 로그 백업에 대한 백업 압축을 제어할 수 있습니다.  
  
    -   [유지 관리 계획 마법사 사용](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
         유지 관리 계획 마법사를 사용하면 예약하는 각 전체 또는 차등 데이터베이스 백업이나 로그 백업의 압축을 제어할 수 있습니다.  
  
    -   Integration Services(SSIS) [데이터베이스 백업 태스크](../../integration-services/control-flow/back-up-database-task.md)  
  
         단일 데이터베이스나 여러 데이터베이스를 백업하기 위한 패키지를 만들 때 백업 압축 동작을 제어할 수 있습니다.  
  
    -   [로그 전달 트랜잭션 로그 백업 설정](../databases/log-shipping-transaction-log-backup-settings.md)  
  
         로그 백업의 백업 압축 동작을 제어할 수 있습니다.  
  
  
## <a name="see-also"></a>관련 항목  
 [백업 압축&#40;SQL Server&#41;](backup-compression-sql-server.md)  
  
  
