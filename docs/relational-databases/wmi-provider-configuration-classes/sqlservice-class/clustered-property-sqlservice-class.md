---
title: "Clustered 속성 (SqlService 클래스) | Microsoft Docs"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: wmi
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: reference
apiname: Clustered Property (SqlService Class)
apilocation: sqlmgmproviderxpsp2up.mof
helpviewer_keywords: Clustered property
ms.assetid: f714e7f5-c2db-45c6-9536-6ca2cb5b42aa
caps.latest.revision: "35"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 5f86c229aa422a01f02af4f94fbff5526fb27a04
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="clustered-property-sqlservice-class"></a>Clustered 속성(SqlService 클래스)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]서비스가 클러스터형된 인스턴스에 속하는지 여부를 지정 하는 부울 속성 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object.Clustered [= value]  
```  
  
## <a name="parts"></a>부분  
 *개체*  
 서비스를 나타내는 [SqlService 클래스](../../../relational-databases/wmi-provider-configuration-classes/sqlservice-class/sqlservice-class.md) 개체입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 서비스가 클러스터형 인스턴스에 참여하는지 여부를 지정하는 부울 값입니다. **true** 는 서비스가 클러스터형 인스턴스에 참여함을 나타내고 **false** 는 서비스가 클러스터형 인스턴스에 참여하지 않음을 나타냅니다.  
  
## <a name="remarks"></a>주의  
  
## <a name="see-also"></a>관련 항목:  
 [서비스 시작 및 중지](http://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  