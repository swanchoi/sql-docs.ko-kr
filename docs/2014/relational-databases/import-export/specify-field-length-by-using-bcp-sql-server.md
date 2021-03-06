---
title: bcp를 사용하여 필드 길이 지정(SQL Server) | Microsoft 문서
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- native data format [SQL Server]
- default field lengths
- field length [SQL Server]
- data formats [SQL Server], field length
- bcp utility [SQL Server], field length
ms.assetid: 240f33ca-ef4a-413a-a4de-831885cb505b
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: f5ed900eae974eb768223d534e6ac43025e9718c
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48202873"
---
# <a name="specify-field-length-by-using-bcp-sql-server"></a>bcp를 사용하여 필드 길이 지정(SQL Server)
  필드 길이는 데이터를 문자 형식으로 표시하는 데 필요한 최대 문자 수를 나타냅니다. 데이터가 네이티브 형식으로 저장된 경우에는 필드 길이를 쉽게 알 수 있습니다. 예를 들어 `int` 데이터 형식의 길이는 4바이트입니다. 접두사 길이로 0을 지정한 경우는 **bcp** 명령은 필드 길이, 기본 필드 길이 및 필드 길이가 데이터 저장소에 포함 된 데이터 파일의 영향에 대해 묻는 메시지를 표시 합니다 `char` 데이터입니다.  
  
## <a name="the-bcp-prompt-for-field-length"></a>필드 길이에 대한 bcp 프롬프트  
 대화형 **bcp** 명령에 **in** 또는 **out** 옵션이 포함된 경우 서식 파일 스위치(**-f**) 또는 데이터 형식 스위치(**-n**, **-c**, **-w** 또는 **-N**)가 없으면 다음과 같이 각 데이터 필드의 필드 길이를 지정하라는 메시지가 표시됩니다.  
  
 `Enter length of field <field_name> [<default>]:`  
  
 컨텍스트에서 이 메시지가 표시되는 예제를 보려면 [bcp를 사용하여 데이터 형식을 호환 가능하도록 지정&#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md)을 참조하세요.  
  
> [!NOTE]  
>  **bcp** 명령의 모든 필드를 대화형으로 지정하면 명령에서 비 XML 서식 파일의 각 필드에 대한 응답을 저장하라는 메시지를 표시합니다. 비 XML 서식 파일에 대한 자세한 내용은 [비 XML 서식 파일&#40;SQL Server&#41;](xml-format-files-sql-server.md)을 참조하세요.  
  
 **bcp** 명령에서 필드 길이 입력 메시지를 표시하는지 여부는 다음과 같은 몇 가지 요인에 따라 결정됩니다.  
  
-   고정 길이가 아닌 데이터 형식을 복사하며 접두사 길이 0을 지정하는 경우 **bcp** 에서 필드 길이를 입력하라는 메시지가 표시됩니다.  
  
-   **bcp** 는 문자 형식 이외의 데이터를 문자 데이터로 변환하는 경우 데이터를 저장할 수 있을 만큼 큰 기본 필드 길이를 제시합니다.  
  
-   파일 스토리지 유형이 문자 형식이 아니면 **bcp** 명령은 필드 길이 입력 메시지를 표시하지 않습니다. 데이터는 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 네이티브 데이터 표현(네이티브 형식)으로 저장됩니다.  
  
## <a name="using-default-field-lengths"></a>기본 필드 길이 사용  
 일반적으로는 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 의 권장 사항에 따라 **bcp**에서 제시하는 필드 길이의 기본값을 사용하는 것이 좋습니다. 문자 모드 데이터 파일을 만들 때 기본 필드 길이를 사용하면 데이터가 잘리지 않으며 숫자 오버플로 오류도 발생하지 않습니다.  
  
 필드 길이를 잘못 지정하면 문제가 발생할 수 있습니다. 예를 들어 숫자 데이터를 복사할 때 이 데이터의 필드 길이가 너무 짧으면 **bcp** 유틸리티는 오버플로 메시지를 표시하며 데이터를 복사하지 않습니다. 또한 내보내면 `datetime` 데이터 26 바이트 미만 문자열에는 필드 길이 지정 합니다 **bcp** 유틸리티 오류 메시지 없이 데이터를 자릅니다.  
  
> [!IMPORTANT]  
>  기본 크기 옵션을 사용하면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에서는 전체 문자열을 읽습니다. 그러나 기본 필드 길이를 사용해도 "예기치 않은 파일의 끝입니다."라는 오류가 발생할 수도 있습니다. 일반적으로이 오류가 발생 하면를 `money` 하 고 `datetime` 예상된 된 필드의 일부만 데이터 파일에서 발생 하는 경우 데이터 형식 예를 들어 경우는 `datetime` 값 *mm*/*dd*  / *yy* 시간 구성 요소 없이 지정 된 이며, 따라서 예상된 24 자 길이 보다 짧은 `datetime` 값 `char` 형식입니다. 이런 유형의 오류를 방지하려면 필드 종결자 또는 고정 길이 데이터 필드를 사용하거나 다른 값을 지정하여 기본 필드 길이를 변경합니다.  
  
### <a name="default-field-lengths-for-character-file-storage"></a>문자 파일 스토리지의 기본 필드 길이  
 다음 표에서는 문자 파일 스토리지 유형으로 저장할 데이터의 기본 필드 길이를 나열합니다. Null 허용 데이터의 길이는 Null이 아닌 데이터와 같습니다.  
  
|데이터 형식|기본 길이(문자)|  
|---------------|-----------------------------------|  
|`char`|열에 정의된 길이|  
|`varchar`|열에 정의된 길이|  
|`nchar`|열에 정의된 길이의 2배|  
|`nvarchar`|열에 정의된 길이의 2배|  
|`Text`|0|  
|`ntext`|0|  
|`bit`|1|  
|`binary`|열에 정의된 길이의 2배에 1을 더한 값|  
|`varbinary`|열에 정의된 길이의 2배에 1을 더한 값|  
|`image`|0|  
|`datetime`|24|  
|`smalldatetime`|24|  
|`float`|30|  
|`real`|30|  
|`int`|12|  
|`bigint`|19|  
|`smallint`|7|  
|`tinyint`|5|  
|`money`|30|  
|`smallmoney`|30|  
|`decimal`|41*|  
|`numeric`|41*|  
|`uniqueidentifier`|37|  
|`timestamp`|17|  
|`varchar(max)`|0|  
|`varbinary(max)`|0|  
|`nvarchar(max)`|0|  
|UDT|UDT(사용자 정의 용어) 열의 길이|  
|XML|0|  
  
 \*에 대 한 자세한 내용은 합니다 `decimal` 및 `numeric` 데이터 형식 참조 [decimal 및 numeric &#40;TRANSACT-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).  
  
> [!NOTE]  
>  `tinyint` 형식의 열은 0부터 255까지의 값을 가질 수 있으며 해당 범위의 수를 나타내는 데 필요한 최대 문자 수는 3개입니다(100부터 255까지를 표현).  
  
### <a name="default-field-lengths-for-native-file-storage"></a>네이티브 File Storage의 기본 필드 길이  
 다음 표에서는 네이티브 파일 스토리지 유형으로 저장할 데이터의 기본 필드 길이를 나열합니다. Null 허용 데이터의 길이는 Null이 아닌 데이터와 같으며 문자 데이터는 항상 문자 형식으로 저장됩니다.  
  
|데이터 형식|기본 길이(문자)|  
|---------------|-----------------------------------|  
|`bit`|1|  
|`binary`|열에 정의된 길이|  
|`varbinary`|열에 정의된 길이|  
|`image`|0|  
|`datetime`|8|  
|`smalldatetime`|4|  
|`float`|8|  
|`real`|4|  
|`int`|4|  
|`bigint`|8|  
|`smallint`|2|  
|`tinyint`|1|  
|`money`|8|  
|`smallmoney`|4|  
|`decimal` <sup>1</sup>|<sup>*</sup>|  
|`numeric` <sup>1</sup>|<sup>*</sup>|  
|`uniqueidentifier`|16|  
|`timestamp`|8|  
  
 <sup>1</sup> 에 대 한 자세한 내용은 합니다 `decimal` 및 `numeric` 데이터 형식을 참조 하십시오 [decimal 및 numeric &#40;Transact SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).  
  
 앞의 모든 경우에서 나중에 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 로 다시 로드할 데이터 파일을 만들어 최소한의 스토리지 공간을 유지하려면 기본 파일 스토리지 유형의 길이 접두사와 기본 필드 길이를 사용합니다.  
  
## <a name="see-also"></a>관련 항목  
 [bcp 유틸리티](../../tools/bcp-utility.md)   
 [데이터 형식&#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql)   
 [필드 및 행 종결자 지정&#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md)   
 [bcp를 사용하여 데이터 파일에 접두사 길이 지정&#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)   
 [bcp를 사용하여 파일 저장 유형 지정&#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md)   
 [대량 가져오기 수행 중 Null 유지 또는 기본값 사용&#40;SQL Server&#41;](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
  
