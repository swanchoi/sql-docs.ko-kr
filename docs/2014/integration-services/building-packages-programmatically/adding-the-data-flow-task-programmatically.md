---
title: 프로그래밍 방식으로 데이터 흐름 태스크 추가 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- adding Data Flow task
- SSIS data flow
- data flow task [Integration Services], adding
- MainPipe object
ms.assetid: 0ca03712-a82e-4aa7-949b-f869a8936ddf
author: janinezhang
ms.author: janinez
manager: craigg
ms.openlocfilehash: b72669c44e3cf95076473c207c50cbcabf54b1ee
ms.sourcegitcommit: 5a8678bf85f65be590676745a7fe4fcbcc47e83d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58378190"
---
# <a name="adding-the-data-flow-task-programmatically"></a>프로그래밍 방식으로 데이터 흐름 태스크 추가
  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]에는 개체 모델에서 <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper> 네임스페이스로 표현되는 데이터 흐름 태스크라는 태스크가 포함되어 있습니다. 데이터 흐름 태스크는 패키지 실행 도중 데이터를 변환하고 이동하는 데만 사용되는 특수한 고성능 태스크입니다. 다른 태스크와 마찬가지로 데이터 흐름 태스크도 <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> 개체에 의해 래핑되며, 런타임 엔진의 측면에서 이 태스크는 단지 패키지의 또 다른 태스크일 뿐입니다. 그러나 데이터 흐름에는 데이터 흐름 구성 요소라는 추가 개체가 있습니다. 이러한 구성 요소는 데이터를 원본에서 대상으로 이동하게 하고 때로는 변환을 통해 이동하게 하는 구성 요소입니다. 이 구성 요소는 이동 방향과 데이터 변환 방식을 모두 정의합니다. 데이터 흐름 태스크를 구성하려면 태스크에 구성 요소를 추가한 다음 이들 구성 요소를 연결하여 데이터의 흐름을 구성하고 의도한 변환을 얻어야 합니다.  
  
 데이터 흐름 태스크 내에는 3가지 유형의 구성 요소가 있습니다. **데이터 흐름 원본**, **데이터 흐름 변환**, 및 **데이터 흐름 대상**내에서 순서 대로 표시는 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 디자이너 도구 상자입니다. 이러한 유형을 보다 간단히 원본, 변환 또는 대상이라고도 합니다. 이름이 나타내듯이 데이터는 원본에서 변환을 거쳐 대상으로 이동합니다. 이는 개념을 보여 주기 위해 데이터 흐름을 극단적으로 단순화한 것이지만 데이터 흐름 태스크는 여러 원본을 처리하고 출력을 여러 대상으로 보내는 많은 변환을 서로 연결할 만큼 융통성 있고 강력합니다.  
  
 데이터 흐름 태스크는 다른 태스크가 추가되는 방식과 동일한 방식으로 패키지에 추가됩니다. 태스크를 추가한 후에는 데이터 흐름 태스크에 구성 요소를 추가하고 태스크의 구성 요소를 구성 및 연결하여 태스크를 구성합니다.  
  
## <a name="sample"></a>예제  
 다음 코드 예제에서는 패키지에 데이터 흐름 태스크를 추가하는 방법을 보여 줍니다. 이 예에는 Microsoft.SqlServer.PipelineHost, Microsoft.SqlServer.DTSPipelineWrap 및 Microsoft.SqlServer.ManagedDTS 어셈블리에 대한 참조가 필요합니다.  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      Executable e = p.Executables.Add("STOCK:PipelineTask");  
      TaskHost thMainPipe = e as TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;   
    }  
  }  
}  
```  
  
```vb  
Imports System.IO  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    Dim e As Executable = p.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As TaskHost = CType(e, TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a>외부 리소스  
 blogs.msdn.com의 블로그 항목 - [EzAPI – SQL Server 2012용으로 업데이트됨](https://go.microsoft.com/fwlink/?LinkId=243223)  
  
![Integration Services 아이콘 (작은)](../media/dts-16.gif "Integration Services 아이콘 (작은)")**Integration Services를 사용 하 여 날짜를 알림 설정**<br /> Microsoft의 최신 다운로드, 문서, 예제 및 비디오와 커뮤니티에서 선택된 솔루션을 보려면 MSDN의 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 페이지를 방문하세요.<br /><br /> [MSDN의 Integration Services 페이지 방문](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> 이러한 업데이트에 대한 자동 알림을 받으려면 해당 페이지에서 제공하는 RSS 피드를 구독하세요.  
  
## <a name="see-also"></a>관련 항목  
 [프로그래밍 방식으로 데이터 흐름 구성 요소 검색](../building-packages-programmatically/discovering-data-flow-components-programmatically.md)  
  
  
