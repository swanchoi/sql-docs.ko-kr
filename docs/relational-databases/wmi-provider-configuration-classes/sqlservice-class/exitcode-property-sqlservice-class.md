---
title: ExitCode 속성 (SqlService 클래스) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
apiname:
- ExitCode Property (SqlService Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- ExitCode property
ms.assetid: e6b8bff2-946f-4abe-bd50-1f7bb11fdddf
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: e70e321684ac9dfd738ae45130cee2e3ded070cd
ms.sourcegitcommit: 9c6a37175296144464ffea815f371c024fce7032
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51666042"
---
# <a name="exitcode-property-sqlservice-class"></a>ExitCode 속성(SqlService 클래스)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]
  서비스를 시작하거나 중지할 때 발생하는 문제를 정의하는 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32 오류 코드를 가져오거나 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object.ExitCode [= value]  
```  
  
## <a name="parts"></a>부분  
 *object*  
 서비스를 나타내는 [SqlService 클래스](../../../relational-databases/wmi-provider-configuration-classes/sqlservice-class/sqlservice-class.md) 개체입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 종료 코드를 지정하는 **uint32** 값입니다.  
  
## <a name="remarks"></a>Remarks  
 오류가 이 클래스가 나타내는 서비스에 고유한 것이면 이 속성은 ERROR_SERVICE_SPECIFIC_ERROR(1066)로 설정됩니다. 서비스는 실행 중일 때와 정상 종료 시 이 값을 다시 NO_ERROR로 설정합니다.  
  
## <a name="see-also"></a>관련 항목  
 [서비스 시작 및 중지](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
