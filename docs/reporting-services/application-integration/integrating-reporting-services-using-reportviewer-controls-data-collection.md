---
title: ReportViewer 컨트롤 2016에서 데이터 수집
uthor: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.prod: reporting-services
ms.prod_service: reporting-services-native, reporting-services-sharepoint
ms.technology: application-integration
ms.topic: reference
ms.custom: ''
ms.date: 09/18/2018
ms.openlocfilehash: 52f23cd615179b774392920c84ab4370892e1dd5
ms.sourcegitcommit: 78e32562f9c1fbf2e50d3be645941d4aa457e31f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54100198"
---
# <a name="integrating-reporting-services-using-reportviewer-controls---data-collection"></a>ReportViewer 컨트롤을 사용하여 Reporting Services 통합 - 데이터 수집

고객이 제품을 사용하는 방식을 보다 잘 이해하기 위해 컨트롤에서 익명의 사용 현황 데이터가 수집됩니다. 사용 현황 데이터는 향후에 고객에게 가장 적합한 개선 방향으로 개발이 진행되도록 하는 데 도움이 됩니다.

Microsoft SQL Server 및 보고서 뷰어의 데이터 수집 및 사용 사례는 [개인정보처리방침](https://go.microsoft.com/fwlink/?LinkID=868444)에 설명되어 있습니다.

## <a name="opting-out-of-data-collection"></a>데이터 수집 옵트아웃(opt out)

사용 현황 데이터의 수집을 ```EnableTelemetry``` 속성을 통해 사용하지 않도록 설정할 수 있습니다.

```
<rsweb:ReportViewer ID="ReportViewer1" runat="server" EnableTelemetry="false">
</rsweb:ReportViewer>
```

또는 컨트롤이 렌더링되기 전에 실제로 설정할 수 있습니다.
    
```
protected void Page_Load(object sender, EventArgs e)
{
    ReportViewer1.EnableTelemetry = false;
}
```
## <a name="see-also"></a>관련 항목:

[WebForms 보고서 뷰어 컨트롤 사용](../../reporting-services/application-integration/using-the-webforms-reportviewer-control.md)  
[보고서 뷰어 컨트롤을 사용하여 Reporting Services 통합](../../reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls.md) 



