---
title: 트랜잭션에 주석 추가(Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- annotations [Master Data Services], for transactions
ms.assetid: f5a6b2ca-56de-4e42-9da8-fba0ac3e8d92
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: bdc60f20e33a63da3819d9f920eea51fef8f1d6c
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52754595"
---
# <a name="annotate-a-transaction-master-data-services"></a>트랜잭션에 주석 추가(Master Data Services)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]에서 기록 목적으로 트랜잭션에 대한 지원 정보를 제공하려면 트랜잭션에 주석을 추가합니다.  
  
> [!NOTE]  
>  주석은 삭제할 수 없습니다.  
  
## <a name="prerequisites"></a>사전 요구 사항  
  
-   만든 트랜잭션에 주석을 추가하려면 **탐색기** 기능 영역에 대한 액세스 권한과 주석을 추가할 모델 개체에 대한 **업데이트** 이상의 사용 권한이 있어야 합니다.  
  
-   모든 사용자를 위해 트랜잭션에 주석을 추가하려면 **버전 관리** 기능 영역에 액세스할 수 있는 권한이 있어야 하며 모델 관리자여야 합니다. 자세한 내용은 [관리자&#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md)에 액세스하지 않고 그룹에서 사용자를 추가하고 제거할 수 있습니다.  
  
### <a name="to-annotate-a-transaction-in-explorer"></a>탐색기에서 트랜잭션에 주석을 추가하려면  
  
1.  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 홈 페이지의 **모델** 목록에서 모델을 선택합니다.  
  
2.  **버전** 목록에서 버전을 선택합니다.  
  
3.  **탐색기**를 클릭합니다.  
  
4.  메뉴 모음에서 **엔터티** 를 가리키고 주석을 추가할 트랜잭션을 가진 멤버를 포함하는 엔터티의 이름을 클릭합니다.  
  
5.  표에서 멤버의 행을 클릭합니다.  
  
6.  **트랜잭션 보기**를 클릭합니다.  
  
7.  **트랜잭션 보기** 대화 상자에서 주석을 추가할 트랜잭션을 클릭합니다.  
  
8.  대화 상자 아래쪽의 상자에 주석을 입력합니다.  
  
9. **주석 추가**를 클릭합니다. 주석이 **주석** 창에 표시됩니다.  
  
### <a name="to-annotate-a-transaction-in-version-management-administrators-only"></a>버전 관리에서 트랜잭션에 주석을 추가하려면(관리자에만 해당)  
  
1.  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 홈 페이지에서 **버전 관리**를 클릭합니다.  
  
2.  메뉴 모음에서 **트랜잭션**을 클릭합니다.  
  
3.  **트랜잭션** 창의 표에서 주석을 추가할 트랜잭션의 행을 클릭합니다.  
  
4.  **트랜잭션 주석** 창의 **주석** 상자에 주석을 입력합니다.  
  
5.  **확인**을 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [주석&#40;Master Data Services&#41;](../master-data-services/annotations-master-data-services.md)   
 [트랜잭션&#40;Master Data Services&#41;](../master-data-services/transactions-master-data-services.md)  
  
  
