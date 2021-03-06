---
title: bcp_done | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
apiname:
- bcp_done
apilocation:
- sqlncli11.dll
apitype: DLLExport
helpviewer_keywords:
- bcp_done function
ms.assetid: e59b3f16-5b59-40da-880f-f3edf657d1ee
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: a7393b4900b2942ef67f28fc6ecd9cbf3eee5d54
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47818711"
---
# <a name="bcpdone"></a>bcp_done
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bcp_sendrow [로 수행된 프로그램 변수에서](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md)로의 대량 복사를 끝냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
DBINT bcp_done (  
    HDBC hdbc);  
```  
  
## <a name="arguments"></a>인수  
 *hdbc*  
 대량 복사가 가능한 ODBC 연결 핸들입니다.  
  
## <a name="returns"></a>반환 값  
 [bcp_batch](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-batch.md) 를 마지막으로 호출한 후 영구적으로 저장된 행의 수입니다. 오류가 발생하는 경우에는 -1입니다.  
  
## <a name="remarks"></a>Remarks  
 **bcp_sendrow** 또는 [bcp_moretext](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md) 를 마지막으로 호출한 후 [bcp_done](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-moretext.md)을 호출합니다. 모든 데이터가 복사된 후 **bcp_done** 이 호출되지 않으면 오류가 발생합니다.  
  
## <a name="see-also"></a>관련 항목  
 [대량 복사 함수](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
