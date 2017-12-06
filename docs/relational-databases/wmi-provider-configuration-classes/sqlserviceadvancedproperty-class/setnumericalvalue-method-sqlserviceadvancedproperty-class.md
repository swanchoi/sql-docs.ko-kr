---
title: "SetNumericalValue 메서드 (SqlServiceAdvancedProperty 클래스) | Microsoft Docs"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: wmi
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: reference
apiname: SetNumericalValue Method (SqlServiceAdvancedProperty Class)
apilocation: sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords: SetNumericalValue method
ms.assetid: 950ed1e8-0538-4db4-807c-a2c36f43cf6b
caps.latest.revision: "15"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: cc39b698d3fdc4387ec6fafda830f8da04da40f0
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="setnumericalvalue-method-sqlserviceadvancedproperty-class"></a>SetNumericalValue 메서드(SqlServiceAdvancedProperty 클래스)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]속성의 숫자 값을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object.SetNumericalValue(NumValue)  
```  
  
## <a name="parts"></a>부분  
 *개체*  
 고급 속성을 나타내는 [SqlServiceAdvancedProperty 클래스](../../../relational-databases/wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) 개체입니다.  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|Description|  
|---------------|-----------------|  
|*NumValue*|고급 속성의 값을 지정하는 **uint32** 값입니다.|  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 **uint32** 값으로, 0은 서비스가 수정되었음을 나타내고 1은 요청이 지원되지 않음을 나타내며 다른 모든 숫자는 오류를 나타냅니다.  
  
## <a name="remarks"></a>주의  
 속성을 숫자 값으로 설정하려면 속성 값 형식이 숫자여야 합니다.  
  
## <a name="see-also"></a>관련 항목:  
 [서비스 시작 및 중지](http://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  