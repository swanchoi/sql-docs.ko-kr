---
title: 일정 데이터 새로 고침 (SharePoint 용 PowerPivot) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
helpviewer_keywords:
- unattended data refresh [Analysis Services with SharePoint]
- scheduled data refresh [Analysis Services with SharePoint]
- data refresh [Analysis Services with SharePoint]
ms.assetid: 8571208f-6aae-4058-83c6-9f916f5e2f9b
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 58764334a6ee1902a09941e9fc9bb9723e517cdf
ms.sourcegitcommit: 334cae1925fa5ac6c140e0b2c38c844c477e3ffb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/13/2018
ms.locfileid: "53363845"
---
# <a name="schedule-a-data-refresh-powerpivot-for-sharepoint"></a>데이터 새로 고침 예약(SharePoint용 PowerPivot)
  SharePoint 사이트에 게시한 Excel 통합 문서 내의 PowerPivot 데이터가 자동으로 업데이트되도록 데이터 새로 고침을 예약할 수 있습니다.  
  
 **[!INCLUDE[applies](../includes/applies-md.md)]**  SharePoint 2010  
  
 **항목 내용**  
  
 [필수 구성 요소](#prereq)  
  
 [데이터 새로 고침 개요](#intro)  
  
 [사용 및 일정 데이터 새로 고침](#drenablesched)  
  
 [데이터 새로 고침 확인](#drverify)  
  
> [!NOTE]  
>  PowerPivot 데이터 새로 고침은 SharePoint 팜에서 Analysis Services 서버 인스턴스에 의해 수행되며, Excel 서비스에서 제공되는 데이터 새로 고침 기능과는 관련이 없습니다. PowePivot 데이터 새로 고침 예약 기능은 PowerPivot 데이터 이외의 데이터는 새로 고치지 않습니다.  
  
##  <a name="prereq"></a> 필수 구성 요소  
 데이터 새로 고침 일정을 만들려면 통합 문서에 대해 참가 수준의 이상의 권한이 있어야 합니다.  
  
 데이터 새로 고침 중에 액세스하는 외부 데이터 원본을 사용할 수 있어야 하며 일정에서 지정하는 자격 증명에는 그러한 데이터 원본에 대한 액세스 권한이 있어야 합니다. 예약된 데이터 새로 고침을 실행하려면 네트워크 연결을 통해 액세스할 수 있는 데이터 원본 위치가 필요합니다(예: 워크스테이션의 로컬 폴더가 아닌 네트워크 파일 공유).  
  
 데이터 원본은 Office 문서 또는 Access 데이터베이스일 수 없습니다. Office에서는 Office 데이터 연결 구성 요소를 서버 환경에서 사용하는 것을 지원하지 않습니다. 통합 문서에 이러한 원본의 데이터가 포함되어 있으면 데이터 새로 고침 일정의 데이터 원본 목록에서 해당 원본을 제거해야 합니다.  
  
 통합 문서는 [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] 버전이어야 합니다. 이전 릴리스의 PowerPivot for Excel에서 만든 통합 문서를 사용하는 경우에는 데이터베이스를 최신 버전으로 업그레이드해야 데이터 새로 고침을 예약할 수 있습니다.  
  
 새로 고침 작업이 완료되는 시점에 통합 문서가 체크 인되어 있어야 합니다. 통합 문서에 대한 잠금은 새로 고침이 시작될 때가 아니라 파일 저장 시 데이터 새로 고침이 끝날 때 파일에 설정됩니다.  
  
> [!NOTE]  
>  데이터 새로 고침을 진행하는 동안에는 서버에서 통합 문서를 잠그지 않습니다. 그러나 업데이트된 파일을 체크 인하기 위해 데이터 새로 고침이 끝날 때는 파일을 잠급니다. 이때 파일이 다른 사용자에게 체크 아웃된 경우에는 새로 고쳐진 데이터가 삭제됩니다. 이와 마찬가지로 파일이 체크 인되었지만 데이터 새로 고침을 시작할 때 서버에서 검색한 복사본과 크게 다른 경우 새로 고쳐진 데이터가 삭제됩니다.  
  
##  <a name="intro"></a> 데이터 새로 고침 개요  
 Excel 통합 문서의 PowerPivot 데이터는 원격 서버나 네트워크 파일 공유에서 액세스하는 외부 데이터베이스 또는 데이터 파일을 비롯한 여러 외부 데이터 원본에서 제공될 수 있습니다. 연결된 데이터 원본이나 외부 데이터 원본에서 가져온 데이터가 포함된 PowerPivot 통합 문서의 경우 데이터 새로 고침을 구성하여 해당 원본에서 업데이트된 데이터를 자동으로 가져오도록 예약할 수 있습니다.  
  
 외부 데이터 원본은 PowerPivot 클라이언트 애플리케이션을 사용하여 원래 데이터를 통합 문서로 가져올 때 지정한 포함된 연결 문자열, URL 또는 UNC 경로를 통해 액세스됩니다. PowerPivot 통합 문서에 저장되는 원래 연결 정보가 다음 데이터 새로 고침 작업에 다시 사용됩니다. 데이터 원본에 연결하는 데 사용되는 자격 증명은 덮어쓸 수 있지만 데이터 새로 고침용으로 사용되는 연결 문자열은 덮어쓸 수 없으며 기존 연결 정보만 사용됩니다.  
  
 각 통합 문서에 대해 하나의 데이터 새로 고침 일정 페이지가 있으며 모든 일정 정보는 이 페이지에 지정됩니다. 일반적으로 통합 문서를 작성한 사람이 일정을 정의합니다.  
  
 일정 소유자는 다음 작업을 수행할 수 있습니다.  
  
-   기본 일정을 정의합니다. 기본 일정은 데이터 원본 수준에서 정의된 일정이 없을 경우 사용되는 일정입니다.  
  
-   데이터 새로 고침을 실행하는 데 사용되는 자격 증명을 지정합니다.  
  
-   새로 고침 작업에 포함할 데이터 원본을 선택합니다.  
  
-   필요에 따라 데이터 새로 고침 중 쿼리되는 각 데이터 원본에 대해 인라인, 개별 일정 및 자격 증명을 지정할 수도 있습니다. 각 데이터 원본은 독립적으로 새로 고칠 수 있습니다. 모든 데이터 원본에 대해 사용자 지정 일정을 만들면 기본 일정이 무시됩니다.  
  
 개별 데이터 원본에 대한 세분화된 일정을 만들면 새로 고침 일정을 외부 데이터 원본의 변동에 맞출 수 있습니다. 예를 들어 외부 데이터 원본에 하루 동안 생성된 트랜잭션 데이터가 포함되는 경우 해당 데이터 원본에 대한 개별 데이터 새로 고침 일정을 만들어 매일 밤 업데이트된 정보를 가져올 수 있습니다.  
  
##  <a name="drenablesched"></a> 사용 및 일정 데이터 새로 고침  
 다음 지침에 따라 SharePoint 라이브러리에 게시되는 Excel 통합 문서 내의 PowerPivot 데이터에 대한 데이터 새로 고침 일정을 예약할 수 있습니다.  
  
1.  통합 문서가 포함된 라이브러리에서 통합 문서를 선택한 다음 아래쪽 화살표를 클릭하여 명령 목록을 표시합니다.  
  
2.  **PowerPivot 데이터 새로 고침 관리**를 클릭합니다. 데이터 새로 고침 일정이 이미 정의되어 있는 경우 데이터 새로 고침 기록 보기 페이지가 대신 표시됩니다. **데이터 새로 고침 구성** 을 클릭하여 일정 정의 페이지를 열 수 있습니다.  
  
3.  일정 정의 페이지에서 **사용** 확인란을 선택합니다.  
  
4.  일정 세부 정보에서 일정 유형을 지정하고 세부 정보를 지정합니다. 이 단계에서는 기본 일정을 만듭니다.  
  
    > [!IMPORTANT]  
    >  반드시 **가능한 빨리 새로 고치십시오.** 확인란을 선택하십시오. 그러면 이 통합 문서에 데이터 새로 고침이 작동하는지 확인할 수 있습니다. 일정을 저장한 후 데이터 새로 고침이 시작될 때까지 최대 1분이 걸릴 수 있습니다.  
  
5.  가장 빠른 시작 시간에서 다음 중 하나를 선택합니다.  
  
    1.  **업무 시간 이후** 는 데이터베이스 서버에 업무 시간 중에 생성된 현재 데이터가 포함되는 시점인 업무 시간 이후의 처리 시간을 지정합니다.  
  
    2.  **가장 빠른 특정 시작 시간** 은 데이터 새로 고침 요청이 프로세스 큐에 추가되는 가장 빠른 날짜의 시간과 분입니다. 15분 간격으로 지정할 수 있습니다. 이 설정은 이후 날짜뿐만 아니라 현재 날짜에도 적용됩니다. 예를 들어 오전 6시 30분을 값으로 지정하는 경우, 현재 시간이 오후 4시 30분이면 오후 4시 30분이 오전 6시 30분 이후이기 때문에 새로 고침 요청이 현재 날짜에 큐에 추가됩니다.  
  
     가장 빠른 시작 시간은 요청이 프로세스 큐에 추가되는 시간을 정의합니다. 실제 처리는 서버에 데이터 처리를 시작할 충분한 리소스가 있을 때 수행됩니다. 실제 처리 시간은 처리가 완료된 후에 데이터 새로 고침 기록에 기록됩니다.  
  
6.  서버에서 처리할 수 있는 한 빨리 데이터 새로 고침을 실행하려면 **가능한 빨리 새로 고치십시오.** 확인란을 선택합니다. 데이터 새로 고침 작업의 결과가 성공적이면 데이터 원본을 사용할 수 있으며 사용 권한과 서버 구성이 올바르게 설정된 것입니다.  
  
7.  전자 메일 알림에서 처리 오류가 발생할 경우에 알림을 받을 사람의 전자 메일 주소를 입력합니다.  
  
8.  자격 증명에서 데이터 새로 고침 작업을 실행하는 데 사용되는 계정을 지정합니다. 이 계정은 통합 문서를 열어 데이터를 새로 고칠 수 있도록 통합 문서에 대한 참가 권한을 갖고 있어야 합니다. 이 계정은 Windows 도메인 사용자 계정이어야 합니다. 대부분의 경우 이 계정은 데이터를 새로 고치는 동안 사용되는 외부 데이터 원본에 대한 읽기 권한도 갖고 있어야 합니다. 특히 Windows 인증 사용 옵션을 사용하여 데이터를 원래 가져온 경우 현재 사용자의 Windows 자격 증명을 사용하도록 연결 문자열이 만들어집니다. 현재 사용자가 데이터 새로 고침 계정인 경우 데이터 새로 고침이 성공하려면 해당 계정이 외부 데이터 원본에 대한 읽기 권한을 갖고 있어야 합니다. 다음 옵션 중 하나를 선택합니다.  
  
    1.  PowerPivot 무인 데이터 새로 고침 계정을 사용하여 데이터 새로 고침 작업을 처리하려면 **관리자가 구성한 데이터 새로 고침 계정 사용** 을 선택합니다.  
  
    2.  사용자 이름과 암호를 입력하려면 **다음 Windows 사용자 자격 증명을 사용하여 연결** 을 선택합니다. domain\user 형식으로 계정 정보를 입력합니다.  
  
    3.  사용하려는 이전에 저장된 자격 증명이 포함된 대상 애플리케이션의 ID를 알고 있는 경우 **보안 저장소 서비스에 저장된 자격 증명을 사용하여 연결** 을 선택합니다.  
  
     이러한 옵션에 대 한 자세한 내용은 참조 하세요. [PowerPivot 데이터 새로 고침을 위한 저장 된 자격 증명 구성 &#40;SharePoint 용 PowerPivot&#41; ](configure-stored-credentials-data-refresh-powerpivot-sharepoint.md) 하 고 [PowerPivot 무인 데이터 새로 고침 계정 구성 &#40;PowerPivot for SharePoint&#41;](configure-unattended-data-refresh-account-powerpivot-sharepoint.md)합니다.  
  
9. 데이터 원본에서 데이터 새로 고침 수행 시 원래 데이터 원본을 모두 다시 쿼리하려는 경우 **모든 데이터 원본** 확인란을 선택합니다.  
  
     이 옵션을 선택하면 통합 문서에 데이터를 제공하는 데이터 원본이 추가 또는 제거되어 데이터 원본 목록이 시간이 지남에 따라 바뀌는 경우에도 PowerPivot 데이터를 제공하는 외부 데이터 원본이 자동으로 새로 고침에 포함됩니다.  
  
     포함할 데이터 원본을 수동으로 선택하려면 **모든 데이터 원본** 확인란의 선택을 취소합니다. 나중에 새 데이터 원본을 추가하여 통합 문서를 수정하는 경우 일정의 데이터 원본 목록도 업데이트해야 합니다. 그렇지 않으면 최신 데이터 원본이 새로 고침 작업에 포함되지 않습니다.  
  
     통합 문서에 대해 PowerPivot 데이터 새로 고침 관리 페이지를 열면 선택할 수 있는 데이터 원본 목록이 PowerPivot 통합 문서에서 검색됩니다.  
  
     다음 조건을 만족하는 데이터 원본만 선택하십시오.  
  
    -   데이터 원본을 데이터 새로 고침이 수행될 때와 명시된 위치에서 사용할 수 있어야 합니다. 원래 데이터 원본이 통합 문서를 작성한 사용자의 로컬 디스크 드라이브에 있을 경우 데이터 새로 고침 작업에서 해당 데이터 원본을 제외하거나 네트워크 연결을 통해 액세스할 수 있는 위치에 해당 데이터 원본을 게시할 방법을 찾아야 합니다. 데이터 원본을 네트워크 위치로 이동한 경우에는 [!INCLUDE[ssGeminiClient](../includes/ssgeminiclient-md.md)]에서 통합 문서를 열고 데이터 원본 연결 정보를 업데이트해야 합니다. PowerPivot 통합 문서에 저장되어 있는 연결 정보를 다시 설정하기 위해 이 작업이 필요합니다.  
  
    -   PowerPivot 통합 문서에 포함되어 있거나 일정에 지정된 자격 증명 정보를 사용하여 데이터 원본에 액세스해야 합니다. 포함된 자격 증명 정보는 PowerPivot for Excel을 사용하여 데이터를 가져올 때 PowerPivot 통합 문서에 저장됩니다. 포함된 자격 증명 정보는 SSPI=IntegratedSecurity 또는 SSPI=TrustedConnection인 경우가 많습니다. 이는 현재 사용자의 자격 증명을 사용하여 데이터 원본에 연결함을 의미합니다. 데이터 새로 고침 일정에서 자격 증명 정보를 재정의하려는 경우 미리 정의된 저장된 자격 증명을 지정할 수 있습니다. 자세한 내용은 [PowerPivot 데이터 새로 고침을 위한 저장 된 자격 증명 구성 &#40;SharePoint 용 PowerPivot&#41;](configure-stored-credentials-data-refresh-powerpivot-sharepoint.md)합니다.  
  
    -   지정한 모든 데이터 원본에 대해 데이터 새로 고침이 성공해야 합니다. 그렇지 않으면 새로 고친 데이터가 무시되고 마지막으로 저장한 통합 문서 버전이 남게 됩니다. 확신할 수 없는 데이터 원본은 제외합니다.  
  
    -   데이터 새로 고침이 통합 문서의 다른 데이터를 무효화하지 않아야 합니다. 데이터의 하위 집합을 새로 고칠 때 최신 데이터가 다른 기간의 정적 데이터와 함께 집계된 후에도 통합 문서가 유효한지 확인하는 것이 중요합니다. 통합 문서 작성자는 데이터 종속성을 알고 있어야 하며 데이터 새로 고침이 통합 문서 자체에 적합한지 확인해야 합니다.  
  
10. 선택적으로 특정 데이터 원본에 대한 개별 일정을 정의할 수 있습니다. 원래 데이터 원본이 일정에 따라 자체적으로 업데이트되는 경우 개별 일정이 유용합니다. 예를 들어 PowerPivot 데이터 원본에서 매주 월요일 오전 2시에 새로 고쳐지는 데이터 마트의 데이터를 사용하는 경우 데이터 마트에서 매주 월요일 오전 4시에 새로 고쳐진 데이터를 검색하도록 인라인 일정을 정의할 수 있습니다.  
  
11. **확인** 을 클릭하여 일정을 저장합니다.  
  
##  <a name="drverify"></a> 데이터 새로 고침 확인  
 데이터 새로 고침을 확인하는 가장 좋은 방법은 데이터 새로 고침을 즉시 실행한 다음 기록 페이지를 검토하여 성공적으로 완료되었는지 확인하는 것입니다. 일정에서 **가능한 빨리 새로 고치십시오.** 확인란을 선택하면 데이터 새로 고침이 작동한다는 확인이 제공됩니다.  
  
 통합 문서의 데이터 새로 고침 기록 페이지에서 데이터 새로 고침 작업에 대한 현재 및 이전 레코드를 볼 수 있습니다. 이 페이지는 통합 문서에 대해 데이터 새로 고침을 예약한 경우에만 표시됩니다. 데이터 새로 고침 일정이 없는 경우 일정 정의 페이지가 대신 표시됩니다.  
  
 데이터 새로 고침 기록을 보려면 참가 권한 이상의 권한이 있어야 합니다.  
  
1.  SharePoint 사이트에서 PowerPivot 통합 문서가 포함된 라이브러리를 엽니다.  
  
     SharePoint 라이브러리에서 PowerPivot 데이터가 있는 통합 문서를 식별하는 시각적 표시는 없습니다. 새로 고칠 수 있는 PowerPivot 데이터가 포함된 통합 문서를 미리 알고 있어야 합니다.  
  
2.  문서를 선택한 다음 오른쪽에 표시되는 아래쪽 화살표를 클릭합니다.  
  
3.  **PowerPivot 데이터 새로 고침 관리**를 선택합니다.  
  
 최근 데이터 새로 고침 작업 상태를 비롯하여 현재 Excel 통합 문서의 PowerPivot 데이터에 대한 모든 새로 고침 작업의 전체 레코드를 보여 주는 기록 페이지가 표시됩니다.  
  
 경우에 따라 지정한 시간과 다른 실제 처리 시간이 표시될 수 있습니다. 이러한 현상은 서버에 처리 부하가 많은 경우 발생합니다. 처리 부하가 많으면 [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] 서비스 인스턴스는 데이터 새로 고침을 시작하기 전에 시스템 리소스가 충분히 확보될 때까지 기다립니다.  
  
 새로 고침 작업이 완료되는 시점에 통합 문서가 체크 인되어 있어야 합니다. 이때 통합 문서가 새로 고친 데이터와 함께 저장됩니다. 파일이 체크 아웃되어 있는 경우 다음 예약된 시간까지 데이터 새로 고침을 건너뜁니다.  
  
 새로 고침 작업에 실패했다거나 새로 고침 작업이 취소되었다는 예기치 않은 상태 메시지가 표시되는 경우 사용 권한 및 서버 가용성을 확인하여 문제를 조사할 수 있습니다.  
  
 데이터 새로 고침 문제 해결에 대한 도움말은 TechNet WIKI의 PowerPivot 데이터 새로 고침 문제 해결 페이지를 검토하십시오. 자세한 내용은 이 항목에서 [PowerPivot 데이터 새로 고침 문제 해결](https://go.microsoft.com/fwlink/?LinkId=251594)을 참조하십시오.  
  
> [!NOTE]  
>  SharePoint 관리자가 중앙 관리의 PowerPivot 관리 대시보드에서 통합 데이터 새로 고침 보고서를 검토하여 데이터 새로 고침 문제를 해결할 수 있도록 도와 줍니다. 자세한 내용은 [PowerPivot Management Dashboard and Usage Data](power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data.md)을 참조하세요.  
  
## <a name="see-also"></a>관련 항목  
 [SharePoint 2010에서 PowerPivot 데이터 새로 고침](powerpivot-data-refresh-with-sharepoint-2010.md)   
 [데이터 새로 고침 기록 보기 &#40;SharePoint 용 PowerPivot&#41;](power-pivot-sharepoint/view-data-refresh-history-power-pivot-for-sharepoint.md)   
 [PowerPivot 데이터 새로 고침에 대 한 저장 된 자격 증명 구성 &#40;SharePoint 용 PowerPivot&#41;](configure-stored-credentials-data-refresh-powerpivot-sharepoint.md)  
  
  
