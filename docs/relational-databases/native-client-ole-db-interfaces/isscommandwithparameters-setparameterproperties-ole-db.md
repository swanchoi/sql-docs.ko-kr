---
title: 'Isscommandwithparameters:: Setparameterproperties (OLE DB) | Microsoft Docs'
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: native-client-ole-db-interfaces
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: reference
apiname: ISSCommandWithParameters::SetParameterProperties (OLE DB)
apitype: COM
helpviewer_keywords: SetParameterProperties method
ms.assetid: 4cd0281a-a2a0-43df-8e46-eb478b64cb4b
caps.latest.revision: "31"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 458b169c41ebf5e209e178bd9db67b9e04503ff7
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="isscommandwithparameterssetparameterproperties-ole-db"></a>ISSCommandWithParameters::SetParameterProperties(OLE DB)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  매개 변수별 서수로 매개 변수 속성을 설정하거나, SSPARAMPROPS 구조의 배열을 지정하여 대량 매개 변수 속성을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
HRESULT SetParameterProperties(  
      DB_UPARAMS cParams,   
      SSPARAMPROPS rgParamProperties[]);  
```  
  
## <a name="arguments"></a>인수  
 *cParams*[in]  
 SSPARAMPROPS 수가 구조체에 *rgParamProperties* 배열입니다. 이 숫자 0 바이트인 경우 **isscommandwithparameters:: Setparameterproperties** 명령에 매개 변수 지정 했을 수 있는 모든 속성을 삭제 합니다.  
  
 *rgParamProperties*[in]  
 설정할 SSPARAMPROPS 구조의 배열입니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 **isscommandwithparameters:: Setparameterproperties** 메서드는 핵심 OLE DB 동일한 오류 코드 반환 **icommandproperties:: Setproperties** 메서드.  
  
## <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 매개 변수 속성 설정이 허용 되는 매개 변수에서 서 수로 단일 **isscommandwithparameters:: Setparameterproperties** 속성 배열에서 SSPARAMPROPS 빌드된 한 번씩 호출 합니다.  
  
 **SetParameterInfo** 메서드를 호출 하기 전에 호출 해야는 **isscommandwithparameters:: Setparameterproperties** 메서드. `SetParameterProperties(0, NULL)`를 호출하면 지정한 모든 매개 변수 속성이 지워지지만 `SetParameterInfo(0,NULL,NULL)`를 호출하면 매개 변수와 관련이 있을 수 있는 모든 속성을 비롯하여 모든 매개 변수 정보가 지워집니다.  
  
 호출 **isscommandwithparameters:: Setparameterproperties** 형식이 있는 매개 변수에 대 한 속성을 지정 하려면 DBTYPE_XML or DBTYPE_UDT 반환 DB_E_ERRORSOCCURRED 또는 DB_S_ERRORSOCCURRED 및 기호는  *dwStatus* 되 해당 매개 변수에 대해 SSPARAMPROPS에 포함 된 모든 Dbprop의 필드입니다. DB_E_ERRORSOCCURRED 또는 DB_S_ERRORSOCCURRED가 참조하는 매개 변수를 검색하기 위해 SSPARAMPROPS에 포함된 각 DBPROPSET의 DBPROP 배열을 이동해야 합니다.  
  
 경우 **isscommandwithparameters:: Setparameterproperties** 와 매개 변수 정보가 아직 설정 하지 않은 매개 변수 속성을 지정 하기 위해 호출 **SetParameterInfo**, 공급자 E_ 반환 다음 오류 메시지와 함께 알 수 없는:  
  
 먼저 SetParameterInfo 메서드를 호출해야만 지정한 매개 변수에 대해 SetParameterProperties 메서드를 호출할 수 있습니다. 매개 변수 속성을 설정하기 전에 매개 변수 정보를 설정해야 합니다.  
  
 경우에 대 한 호출 **isscommandwithparameters:: Setparameterproperties** 위치 매개 변수 정보 설정 된 일부 매개 변수 및 위치 매개 변수 정보 설정 되지 않은에 있는 dwStatus 속성이 일부 매개 변수가 포함 된 SSPARAMPROPS 속성 집합의 DBPROPSET DBSTATUS_NOTSET로 반환 됩니다.  
  
 SSPARAMPROPS 구조는 다음과 같이 정의됩니다.  
  
 `struct SSPARAMPROPS {`  
  
 `DBORDINAL iOrdinal;`  
  
 `ULONG cPropertySets;`  
  
 `DBPROPSET *rgPropertySets;`  
  
 `};`  
  
 부터는 데이터베이스 엔진의 향상 된 [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] isscommandwithparameters:: Setparameterproperties 예상된 결과 대 한 보다 정확한 설명의 얻을를 허용 합니다. 이전 버전의 isscommandwithparameters:: Setparameterproperties 반환 하는 값에서 다를 수 있습니다 이러한 보다 정확한 결과 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]합니다. 자세한 내용은 참조 [메타 데이터 검색](../../relational-databases/native-client/features/metadata-discovery.md)합니다.  
  
|멤버|Description|  
|------------|-----------------|  
|*iOrdinal*|전달된 매개 변수의 서수입니다.|  
|*cPropertySets*|DBPROPSET 수가 구조체에 *rgPropertySets*합니다.|  
|*rgPropertySets*|DBPROPSET 구조의 배열을 반환할 메모리에 대한 포인터입니다.|  
  
## <a name="see-also"></a>관련 항목:  
 [ISSCommandWithParameters &#40; OLE db&#41;](../../relational-databases/native-client-ole-db-interfaces/isscommandwithparameters-ole-db.md)  
  
  