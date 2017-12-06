---
title: "주석이 추가 된 XDR 스키마를 해당 XSD 스키마 (SQLXML 4.0) 변환 | Microsoft Docs"
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: sqlxml
ms.reviewer: 
ms.suite: sql
ms.technology: dbe-xml
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- annotated XDR schemas, converting schemas
- annotated XSD schemas, converting schemas
- XDR to XSD Converter tool [SQLXML]
- XDR schemas [SQLXML], converting
- converting annotated schemas
- mapping schema [SQLXML], conversions
- XSD schemas [SQLXML], converting schemas
ms.assetid: 151c94a8-66d3-4c46-a5ff-a22df456940a
caps.latest.revision: "23"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 4b6cd74088191677cd6483174b296266273a6b33
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="converting-annotated-xdr-schemas-to-equivalent-xsd-schemas-sqlxml-40"></a>주석이 추가된 XDR 스키마를 해당 XSD 스키마로 변환(SQLXML 4.0)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]XML XSD (스키마 정의) 언어는 Xml-data Reduced (XDR) 스키마 정의 언어에 대 한 후속 합니다. [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0에서는 새로 XSD를 지원하므로 XSD를 사용하여 주석이 추가된 새 스키마를 만들 수 있습니다. SQLXML 4.0에는 기존의 주석이 추가된 XDR 스키마를 해당하는 XSD 스키마로 변환하는 데 도움을 주기 위한 XDR-XSD 변환기 도구가 포함되어 있습니다.  
  
> [!IMPORTANT]  
>  주석이 추가된 스키마를 SQLXML 4.0에서 사용하기 위해 XSD로 변환하려는 경우에만 이 도구를 사용합니다. 이 도구는 범용 XDR-XSD 변환 도구가 아닙니다. 따라서 변환된 XSD 스키마를 다른 환경에서 사용할 경우 원래 XDR 스키마와 동일하게 동작하지 않을 수도 있습니다.  
  
 입력 XDR 파일에서 XML 선언 내에 인코딩을 지정하는 경우 이것이 생성되는 XSD 출력 파일의 인코딩이 될 수 있습니다.  
  
 변환기 도구(Cvtschema.exe)는 Program Files\SQLXML 4.0\bin 폴더에 설치되며 명령 프롬프트에서 실행됩니다.  
  
 일반 구문은 다음과 같습니다.  
  
```  
cvtschema XDRFileName, [-y], [-w] [-?]  
```  
  
 각 항목이 나타내는 의미는 다음과 같습니다.  
  
 XDRFileName  
 XSD로 변환될 XDR 파일의 이름입니다. 이 도구는 입력 XDR 파일을 읽어 들이고 현재 디렉터리에 XSD 출력 파일을 생성합니다. 입력 파일의 확장명이 .xdr 또는 .xml인 경우 생성되는 출력 XDR 파일은 이름은 같지만 확장명은 .xsd입니다. 입력된 파일 이름 확장명은.xml 또는.xdr (또는 확장명은 누락 된 경우) 이외의 다른 출력 파일 이름이 같은 만들어지고 입력된 파일 이름에.xsd 확장명이 추가 됩니다. 예를 들어 입력 XDR 파일 이름이 SampleFile.abc인 경우 결과 XSD는 SampleFile.abc.xsd로 저장됩니다.  
  
 -y  
 (옵션) 기존 XSD 파일을 변환기 도구에서 생성되는 XSD 파일로 덮어씁니다. 이 플래그를 지정하지 않으면 도구에서는 기존 XSD 파일을 덮어쓸지 여부를 지정하라는 메시지를 표시하고 출력 파일 이름을 변경할 수 있는 옵션을 제공합니다.  
  
 -w  
 (옵션) 도구의 변환 프로세스에서 생성된 심각하지 않은 경고를 반환합니다. 기본적으로 심각한 오류에 대한 메시지만 표시됩니다.  
  
 -?  
 지정할 수 있는 옵션의 목록을 반환 **cvtschema**, 설명이 있습니다.  
  
## <a name="see-also"></a>관련 항목:  
 [XSD 데이터 형식을 XPath 데이터 형식 &#40;에 매핑 SQLXML 4.0 &#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-using/mapping-xsd-data-types-to-xpath-data-types-sqlxml-4-0.md)   
 [XSD 주석 &#40; SQLXML 4.0 &#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-using/xsd-annotations-sqlxml-4-0.md)  
  
  