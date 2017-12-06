---
title: bcp_collen | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: native-client-odbc-extensions-bulk-copy-functions
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: reference
apiname: bcp_collen
apilocation: sqlncli11.dll
apitype: DLLExport
helpviewer_keywords: bcp_collen function
ms.assetid: faaf1f7a-81f2-4852-a178-56602c33673a
caps.latest.revision: "30"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: f759ddc3c65bfce8094dde221432d0af9e678f7a
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="bcpcollen"></a>bcp_collen
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  현재 대량 복사에 대한 프로그램 변수의 데이터 길이를 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]로 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
RETCODE bcp_collen (  
        HDBC hdbc,  
        DBINT cbData,  
        INT idxServerCol);  
```  
  
## <a name="arguments"></a>인수  
 *hdbc*  
 대량 복사가 가능한 ODBC 연결 핸들입니다.  
  
 *cbData*  
 길이 표시기나 종결자의 길이를 제외한 프로그램 변수의 데이터 길이입니다. 설정 *cbData* SQL_NULL_DATA로 NULL 값 열을 포함 하는 서버에 복사 하는 모든 행을 나타냅니다. SQL_VARLEN_DATA로 설정하면 복사되는 데이터의 길이를 확인하는 데 문자열 종결자 또는 다른 메서드가 사용됩니다. 길이 표시기와 종결자가 모두 있으면 시스템에서는 복사되는 데이터 크기가 더 작은 것이 사용됩니다.  
  
 *idxServerCol*  
 데이터가 복사되는 대상 테이블 열의 서수 위치입니다. 첫 번째 열은 1입니다. 열의 서 수 위치를 보고 [SQLColumns](../../relational-databases/native-client-odbc-api/sqlcolumns.md)합니다.  
  
## <a name="returns"></a>반환 값  
 SUCCEED 또는 FAIL  
  
## <a name="remarks"></a>주의  
 **bcp_collen** 함수를 사용 하면 데이터를 복사할 때 특정 열에 대 한 프로그램 변수의 데이터 길이 변경할 수 있습니다 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 와 [bcp_sendrow](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md)합니다.  
  
 데이터 길이 결정 하는 처음에 때 [bcp_bind](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) 호출 됩니다. 데이터 길이에 대 한 호출 간에 변경 되 면 **bcp_sendrow** 없습니다 길이 접두사 또는 종결자를 사용 하 고, 호출할 수 있습니다 **bcp_collen** 길이 다시 설정 합니다. 다음 호출 **bcp_sendrow** 설정에 대 한 호출에서 길이 사용 하 여 **bcp_collen**합니다.  
  
 호출 해야 **bcp_collen** 데이터 길이를 수정 하려는 테이블의 각 열에 대해 한 번씩입니다.  
  
## <a name="see-also"></a>관련 항목:  
 [대량 복사 함수](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/sql-server-driver-extensions-bulk-copy-functions.md)  
  
  