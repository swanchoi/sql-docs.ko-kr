---
title: CSDLBI 개념 | Microsoft Docs
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 486bbe240656bb2719ad4ce8f1ec51b226bec30b
ms.sourcegitcommit: 7fe14c61083684dc576d88377e32e2fc315b7107
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2018
ms.locfileid: "50146268"
---
# <a name="csdlbi-concepts"></a>CSDLBI 개념
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  CSDLBI(BI 포함 개념 스키마 정의 언어) 주석은 엔터티 데이터 프레임워크를 기반으로 하며, 별도의 데이터 집합을 프로그래밍 방식으로 액세스, 쿼리 또는 내보낼 수 있도록 하여 데이터를 나타내기 위한 추상화입니다. CSDLBI는 풍부한 데이터 기반 보고 및 응용 프로그램을 지원하기 때문에 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]를 사용하여 만든 데이터 모델을 나타내는 데 사용됩니다.  
  
 이 단원에서는 CSDLBI 표현이 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 데이터 모델(테이블 형식 및 다차원)에 매핑되는 방법을 설명하고 각 모델 유형의 예를 보여 줍니다.  
  
 이러한 개념을 설명하는 데 사용하는 예는 Codeplex에서 제공하는 AdventureWorks 예제 데이터베이스를 통해 얻을 수 있습니다. 샘플에 대 한 자세한 내용은 참조 하세요. [SQL Server에 대 한 Adventure Works 샘플](http://go.microsoft.com/fwlink/?linkID=220093)합니다.  
  
## <a name="structure-of-a-tabular-model-in-csdlbi"></a>CSDLBI의 테이블 형식 모델 구조  
 보고서 모델과 해당 데이터를 설명하는 CSDLBI 문서는 xsd 문으로 시작하여 모델에 대한 정의로 이어집니다.  
  
 모델은 다음과 같은 주요 엔터티, 연결 및 속성이 포함된 네임스페이스입니다.  
  
-   합니다 **EntityContainer** 모델에서 테이블을 나열 합니다.  
  
-   각 테이블은으로 나열 됩니다는 **EntityContainer** 으로 **EntitySet**합니다.  
  
-   두 테이블 간의 각 관계 라고는 **AssociationSet** 는 관계 끝점과 관계 역할을 정의 합니다.  
  
-   합니다 **EntityType** 요소가 테이블 및 열 정렬에 대 한 속성을 포함 하 여에 대 한 추가 정보를 제공할 목적으로 표시 하는 BISM 확장 됩니다.  
  
-   합니다 **측정값** 요소는 모델에서 사용할 수 있는 계산을 정의 합니다. 특수 표시 특성을 사용 하 여 새 집합을 추가 하 여 측정값을 KPI로 전환할 수 있습니다 **KPI** 요소입니다.  
  
-   별도의 큐브 뷰 표현은 없습니다. 하지만 사용 하 여 플래그가 지정 된 CSDL에는 큐브 뷰에 포함 되지 않은 테이블과 열을 **Hidden** 특성입니다.  
  
### <a name="entities-entitysets-and-entitytypes"></a>Entities, EntitySets 및 EntityTypes  
 엔터티 데이터 프레임워크에서 엔터티의 개념은 데이터 모델의 열과 테이블을 나타내도록 확장되었습니다. 다음 발췌문 목록을 **EntitySet** 요소에 단순 포함 된 테이블이 세 개만 모델입니다.  
  
```  
<EntityContainer Name="SimpleModel">  
<EntitySet Name="DimCustomer"EntityType="SimpleModel.DimCustomer">  
     <bi:EntitySet />  
   </EntitySet>  
<EntitySet Name="DimDate" EntityType="SimpleModel.DimDate">  
     <bi:EntitySet />  
   </EntitySet>  
<EntitySet Name="DimGeography" EntityType="SimpleModel.DimGeography">  
     <bi:EntitySet />  
   </EntitySet> />  
  
```  
  
 합니다 **EntitySet** 열 또는 테이블의 데이터에 대 한 정보가 없습니다. 열과 해당 속성에 대한 자세한 설명은 EntityType 요소에 제공됩니다.  
  
 합니다 **EntitySet** 등 및 키 열, 데이터 형식 및 null 허용 여부, 정렬 동작 열의 길이 정의 하는 속성의 컬렉션을 포함 하는 각 엔터티 (테이블)에 대 한 요소입니다. 예를 들어 다음 CSDL 발췌 구문에서는 Customer 테이블에 있는 세 개의 열을 설명합니다. 첫 번째 열은 모델에 내부적으로 사용되며 숨겨진 특수한 열입니다.  
  
```  
<EntityType Name="Customer">  
  <Key>  
     <PropertyRef Name="RowNumber" />  
  </Key>  
    <Property Name="RowNumber" Type="Int64" Nullable="false">  
     <bi:Property Hidden="true" Contents="RowNumber"  
       Stability="RowNumber" />  
    </Property>  
    <Property Name="CustomerKey" Type="Int64" Nullable="false">  
      <bi:Property />  
    </Property>  
     <Property Name="FirstName" Type="String" MaxLength="Max" FixedLength="false">  
       <bi:Property />  
      </Property>  
  
```  
  
 생성 되는 CSDLBI 문서 크기를 제한 하려면 엔터티의 두 번 이상 나타나는 속성이 지정 되므로 기존 속성에 대 한 참조로 속성에 대 한 한 번만 나열 되어야 합니다 **EntityType**합니다. 클라이언트 응용 프로그램을 찾아 속성의 값을 가져올 수는 **EntityType** 일치 하는 **은 originentitytype과**합니다.  
  
### <a name="relationships"></a>관계  
 엔터티 데이터 프레임 워크에서 관계로 정의 되며 *연결* 엔터티 간의 합니다.  
  
 연결에는 항상 테이블의 필드나 열을 각각 가리키는 두 개의 끝이 있습니다. 따라서 관계의 끝점이 다를 경우 두 테이블 사이의 관계가 여러 가지일 수 있습니다. 역할 이름이 연결의 끝점에 지정되고, 데이터 모델의 컨텍스트에서 연결이 사용되는 방법을 나타냅니다. 역할 이름을 예로 들 수 있습니다 **ShipTo**고객 id는 Orders 테이블에 관련 된 고객 ID에 적용 된 경우.  
  
 모델의 CSDLBI 표현을 엔터티 측면의 서로 매핑되는 방식을 결정 하는 연결 특성도 포함 된 *복합성* 연결 합니다. 복합성은 테이블 간 관계 끝점의 특성이나 열이 관계의 한 편에 있는지 아니면 여러 편에 있는지 나타냅니다. 일 대 일 관계에 대한 별도의 값은 없습니다. CSDLBI 주석은 복합성 0(엔터티가 어디에도 연결되지 않음)이나 0..1(일 대 일 관계 또는 일 대 다 관계)을 지원합니다.  
  
 다음 예제에서는 DateAlternateKey 열에서 조인된 Date 테이블과 ProductInventory 테이블 간 관계에 대한 CSDLBI 출력을 나타냅니다. 있음을 기본적으로의 이름 합니다 **AssociationSet** 관계에 관련 된 열의 정규화 된 이름입니다. 그러나 모델을 설계할 때 다른 이름 형식을 사용하도록 이 동작을 변경할 수 있습니다.  
  
```  
<AssociationSet Name="ProductInventory_Date_DateKey" Association="Model.ProductInventory_Date_DateKey">  
              <End EntitySet="ProductInventory" />  
              <End EntitySet="Date" />  
              <bi:AssociationSet />  
            </AssociationSet>  
  
```  
  
### <a name="visualization-and-navigation-properties"></a>시각화 및 탐색 속성  
 CSDLBI 주석의 중요한 부분은 보고 계층에서 프레젠테이션을 정의하고 엔터티 간의 관계를 탐색하기 위한 속성입니다. 대개 데이터 모델을 만들 때는 클라이언트 응용 프로그램이 표시 순서와 그 밖의 세부 정보를 지정한다고 간주하므로 데이터 순서 지정 및 그룹화 방법 제어나 기본값 지정을 중요하게 여기지 않아도 됩니다. 그러나 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 테이블 형식 모델은 [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] 보고 클라이언트와의 통합을 위해 디자인되었으며 보고서 디자인 화면에서 데이터 모델의 엔터티를 표시하도록 지원하는 속성과 특성을 포함합니다.  
  
 시각화를 위한 확장에는 숫자 데이터와 함께 사용할 기본 집계를 지정하거나, 텍스트 필드가 이미지 URL을 가리키도록 지시하거나, 현재 필드를 정렬하는 데 사용되는 필드를 지정하기 위한 특성이 포함됩니다.  
  
### <a name="name-properties-and-naming-conventions"></a>이름 속성 및 명명 규칙  
 CSDLBI 스키마는 키로 사용할 수 있는 고유 이름과 식별자를 각 엔터티에 제공합니다. 또한 일부 엔터티는 표시용으로 사용되는 캡션과 엔터티가 사용되는 위치에 따라 달라지는 컨텍스트 이름을 가질 수 있습니다.  
  
 합니다 **설명서** 요소는 비즈니스 사용자가 데이터의 의미를 이해 하는 데는 엔터티에 대 한 설명을 제공 하기 위해 보고서 디자이너에 대 한 기회를 제공 합니다. 일부 엔터티는 또한 하나 이상의 허용 **주석** 또는 클라이언트 응용 프로그램에서 소비에 대 한 추가 메타 데이터를 제공 하는 특성입니다.  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 도구로 모델을 생성하는 경우 개체를 위해 만든 이름은 개체 이름 지정과 이름의 고유성을 위해 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 규칙을 따릅니다. 그러나 CSDLBI는 C# 식별자에 대한 명명 규칙을 준수해야 하는 EDF(엔터티 데이터 프레임워크)를 기반으로 하기 때문에 서버에서 모델의 CSDLBI 출력을 만들 때 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 스키마에서 사용하는 이름을 가져와서 EDF 요구 사항에 맞는 새 개체 이름을 자동으로 만듭니다. 다음 표에서는 새 이름을 생성하기 위한 작업에 대해 설명합니다.  
  
|규칙|작업|  
|----------|------------|  
|금지된 문자가 없습니다.|금지된 문자는 밑줄로 대체됩니다.|  
|이름은 고유해야 합니다.|두 문자열이 같으면 밑줄과 숫자를 추가하여 문자열 하나를 고유하게 만듭니다.|  
  
> [!WARNING]  
>  캡션과 한정자는 번역되며 둘 중 하나는 지정한 언어로 표시될 수 있습니다. 즉, 한정자와 이름 또는 한정자와 캡션이 연결된 경우 문자열이 서로 다른 두 언어로 표시될 수 있습니다.  
  
## <a name="additions-to-support-multidimensional-models"></a>다차원 모델을 지원하기 위한 추가 기능  
 CSDLBI 주석 버전 1.0은 테이블 형식의 모델만 지원했습니다. 버전 1.1에서는 기존 BI 개발 도구를 사용하여 만든 다차원 모델(OLAP 큐브)에 대한 지원이 추가되었습니다. 따라서 다차원 모델에 대한 XML 요청을 실행하여 보고에 사용할 모델의 CSDLBI 정의를 받을 수 있습니다.  
  
 **: 큐브의** SQL Server [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 테이블 형식 데이터베이스에는 모델이 하나만 포함 될 수 있습니다. 반면에 각 다차원 데이터베이스에는 여러 개의 큐브가 포함될 수 있으며 각 데이터베이스는 기본 큐브와 연결됩니다. 따라서 다차원 서버에 대해 XML 요청을 실행할 때는 큐브를 지정해야 하며, 그러지 않으면 기본 큐브에 대한 XML이 반환됩니다.  
  
 그 점을 제외하면 큐브 표현은 테이블 형식의 모델 데이터베이스와 매우 비슷합니다. 큐브 이름과 큐브는 테이블 형식 데이터베이스와 데이터베이스 ID에 해당합니다.  
  
 **크기:** 차원 열과 속성이 있는 엔터티 (테이블)로 CSDLBI에 표시 됩니다. 큐브 뷰에 포함 되지 않았더라도 모델에 포함 된 차원으로 표시 된 CSDL 출력에 표시 됩니다 **Hidden**합니다.  
  
 **큐브 뷰:** 클라이언트는 개별 큐브 뷰에 대 한 CSDL을 요청할 수 있습니다. 자세한 내용은 [DISCOVER_CSDL_METADATA 행 집합](https://docs.microsoft.com/bi-reference/schema-rowsets/xml/discover-csdl-metadata-rowset)합니다.  
  
 **계층:** 계층 지원 되며 수준 집합으로 CSDLBI에서 표시 합니다.  
  
 **멤버:** 지원 기본 멤버를 추가한 있고 기본값은 CSDLBI 출력에 자동으로 추가 됩니다.  
  
 **계산된 멤버:** 다차원 모델의 자식에 대 한 계산된 멤버를 지원 **모든** 에서는 단일 실제 멤버가 있는 합니다.  
  
 **차원 특성:** 의 CSDLBI 출력을 차원 특성은 지원 하 고 자동으로 집계할 수 없는 표시 합니다.  
  
 **Kpi:** CSDLBI 버전 1.1에서 Kpi 된 지원 되지만 표현이 변경 되었습니다. 예전에는 KPI가 측정값의 속성이었습니다. 버전 1.1에서는 KPI 요소를 측정값에 추가할 수 있습니다.  
  
 **새 속성:** DirectQuery 모델을 지 원하는 특성이 추가 되었습니다.  
  
 **제한 사항:** 셀 보안은 지원 되지 않습니다.  
  
## <a name="see-also"></a>관련 항목  
 [비즈니스 인텔리전스에 대한 CSDL 주석&#40;CSDLBI&#41;](https://docs.microsoft.com/bi-reference/csdl/csdl-annotations-for-business-intelligence-csdlbi)  
  
  
