---
title: 암호화된 미러 데이터베이스 설정 | Microsoft Docs
ms.custom: ''
ms.date: 06/26/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- cryptography [SQL Server], database mirroring
- encryption [SQL Server], database mirroring
- database master key [SQL Server], database mirroring
- mirror database [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 7329a575-be29-46e0-abc6-1344db37920c
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 2a74adba783f1a52bdd404e11f0f747234c47f4b
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48164203"
---
# <a name="set-up-an-encrypted-mirror-database"></a>암호화된 미러 데이터베이스 설정

미러 데이터베이스의 데이터베이스 마스터 키에 대한 자동 암호 해독을 사용하려면 마스터 키를 암호화하는 데 사용한 암호를 미러 서버 인스턴스에 제공해야 합니다. [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] 및 이후 버전에는 암호를 전송하는 메커니즘이 포함됩니다. 데이터베이스 미러링을 시작하기 전에 **sp_control_dbmasterkey_password** 를 사용하여 데이터베이스 마스터 키에 대한 자격 증명을 만드세요. 미러되는 모든 데이터베이스에 대해 이 프로세스를 반복해야 합니다. 자세한 내용은 [sp_control_dbmasterkey_password&#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql)를 참조하세요.
  
> [!CAUTION]  
>  **sa** 및 기타 상위 권한 서버 보안 주체에서 액세스하지 않아야 하는 데이터베이스에 대한 장애 조치(Failover) 암호 해독은 설정하지 마십시오. 서비스 마스터 키로 키 계층을 해독할 수 없도록 데이터베이스를 구성할 수 있습니다. 이 옵션은 **sa** 또는 기타 상위 권한 서버 보안 주체에서 액세스하지 않아야 하는 정보가 포함된 데이터베이스를 위한 심층 방어로 지원됩니다. 이러한 데이터베이스에 대해 장애 조치(failover) 암호 해독을 설정하면 이러한 심층 방어가 제거되어 **sa** 및 기타 상위 권한 서버 보안 주체에서 데이터베이스를 암호 해독할 수 있습니다.  


<!-- Note: We cannot append '?view=sql-server-2016' to these, even tho in theory we might want to. -->

## <a name="see-also"></a>관련 항목

[sp_control_dbmasterkey_password &#40;TRANSACT-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql)

[CREATE MASTER KEY&#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql)

[ALTER MASTER KEY &#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/alter-master-key-transact-sql)

[암호화 계층](../../relational-databases/security/encryption/encryption-hierarchy.md)

[데이터베이스 미러링 설정&#40;SQL Server&#41;](database-mirroring-sql-server.md)

