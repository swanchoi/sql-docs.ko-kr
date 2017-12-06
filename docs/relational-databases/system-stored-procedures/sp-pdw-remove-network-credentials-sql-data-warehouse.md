---
title: "sp_pdw_remove_network_credentials (SQL 데이터 웨어하우스) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: 
ms.prod_service: sql-data-warehouse, pdw
ms.reviewer: 
ms.service: sql-data-warehouse
ms.component: system-stored-procedures
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: TSQL
ms.assetid: c12696a2-5939-402b-9866-8a837ca4c0a3
caps.latest.revision: "9"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 30f35803c804b6e895bf5287cb864c9cc979f013
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="sppdwremovenetworkcredentials-sql-data-warehouse"></a>sp_pdw_remove_network_credentials (SQL 데이터 웨어하우스)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  그러면 제거에 저장 된 네트워크 자격 증명 [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] 네트워크 파일 공유에 액세스할 수 있습니다. 예를 들어이 저장된 프로시저를 사용 하 여에 대 한 권한을 제거 하려면 [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] 를 백업 및 복원 사용자 네트워크 내에 상주 하는 서버 작업을 수행 합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [TRANSACT-SQL 구문 표기 규칙 &#40; Transact SQL &#41;](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
sp_pdw_remove_network_credentials 'target_server_name'  
```  
  
## <a name="arguments"></a>인수  
 '*target_server_name*'  
 대상 서버 호스트 이름 또는 IP 주소를 지정합니다. 이 서버에 액세스할 자격 증명에서 제거할 [!INCLUDE[ssSDW](../../includes/sssdw-md.md)]합니다. 이것은 변경 하거나 팀에서 관리 되는 실제 대상 서버에 사용 권한을 제거 합니다.  
  
 *target_server_name* nvarchar(337)로 정의 됩니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 1(실패)  
  
## <a name="permissions"></a>Permissions  
 필요한 **ALTER SERVER STATE** 권한.  
  
## <a name="error-handling"></a>오류 처리  
 컨트롤 노드 및 모든 계산 노드에 하지 못하면 자격 증명을 제거 하는 경우 오류가 발생 합니다.  
  
## <a name="general-remarks"></a>일반적인 주의 사항  
 이 저장된 프로시저에 대 한 NetworkService 계정에서 네트워크 자격 증명을 제거 [!INCLUDE[ssSDW](../../includes/sssdw-md.md)]합니다. SMP의 각 인스턴스를 실행 하는 NetworkService 계정 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 제어 노드 및 계산 노드에 있습니다. 예를 들어 백업 작업이 실행 될 때는 제어 노드에 각 계산 노드가 사용 됩니다는 NetworkService 계정 자격 증명 대상 서버에 액세스할 수 있습니다.  
  
## <a name="metadata"></a>메타데이터  
 모든 자격 증명을 나열 하 고 자격 증명 제거 되었는지 확인 하려면 [sys.dm_pdw_network_credentials &#40; Transact SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-network-credentials-transact-sql.md).  
  
 자격 증명을 추가 하려면 사용 [sp_pdw_add_network_credentials &#40; SQL 데이터 웨어하우스 &#41; ](../../relational-databases/system-stored-procedures/sp-pdw-add-network-credentials-sql-data-warehouse.md).  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>예: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] 및[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="a-remove-credentials-for-performing-a-database-backup"></a>1. 데이터베이스 백업을 수행 하기 위한 자격 증명 제거  
 다음 예제에서는 10.192.147.63의 IP 주소가 있는 대상 서버에 액세스 하기 위한 사용자 이름 및 암호 자격 증명을 제거 합니다.  
  
```  
EXEC sp_pdw_remove_network_credentials '10.192.147.63';  
```  
  
  
