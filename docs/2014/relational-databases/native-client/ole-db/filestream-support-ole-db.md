---
title: FILESTREAM 지원 (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB [FILESTREAM support]
- FILESTREAM [SQL Server], OLE DB
ms.assetid: c2bd3dfd-6103-43d1-859e-8ed8d19c58d3
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: ad6aa7b55906e68dba6615140ef2c6afcc3efaa5
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48067793"
---
# <a name="filestream-support-ole-db"></a>FILESTREAM 지원(OLE DB)
  부터는 [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] 고 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0 OLE DB에 향상 된 FILESTREAM 기능이 지원 됩니다. 이 기능에 대 한 자세한 내용은 참조 하세요. [FILESTREAM 지원](../features/filestream-support.md)합니다. 샘플을 보려면 [Filestream 및 OLE DB](../../native-client-ole-db-how-to/filestream/filestream-and-ole-db.md)합니다.  
  
 2GB보다 큰 `varbinary(max)` 값을 보내고 받기 위해 응용 프로그램에서는 매개 변수와 결과 바인딩에 `DBTYPE_IUNKNOWN`을 사용합니다. 매개 변수에 대 한 공급자 ISequentialStream 및 ISequentialStream을 반환 하는 결과 iunknown:: Queryinterface를 호출 해야 합니다.  
  
 OLE DB에 대 한 관련 ISequentialStream 값 검사에 완화 될 예정입니다. 때 *wType* 됩니다 `DBTYPE_IUNKNOWN` 에 `DBBINDING` 구조체 길이 검사 수 생략 하거나 사용 하지 않도록 설정 `DBPART_LENGTH` 에서 *dwPart* 또는 (오프셋 데이터의길이설정하여*obLength* 데이터 버퍼에서)를 ~ 0입니다. 이렇게 하면 공급자는 값의 길이를 검사하지 않고 스트림을 통해 사용할 수 있는 모든 데이터를 요청하고 반환합니다. 이러한 변경 사항은 모든 LOB(큰 개체) 형식과 XML에 적용되지만, 이는 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] 이상의 서버에 연결된 경우에만 해당됩니다. 이 기능은 개발자에게 더 나은 융통성을 제공할 뿐만 아니라 기존 응용 프로그램 및 하위 서버를 위한 일관성과 이전 버전과의 호환성을 유지할 수 있게 도와줍니다.  
  
 이 변경 irowset:: Getdata, icommand:: Execute, 및 irowsetfastload:: Insertrow 주로 데이터를 전송 하는 모든 인터페이스에 적용 합니다.  
  
## <a name="see-also"></a>관련 항목  
 [SQL Server Native Client 프로그래밍](../sql-server-native-client-programming.md)  
  
  
