---
title: 다 대 다 관계 매핑(Visual Database Tools) | Microsoft 문서
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- relationships [SQL Server], many-to-many
- junction tables [SQL Server]
- many-to-many relationships [SQL Server]
- mapping many-to-many relationships [SQL Server]
- database diagrams [SQL Server], relationships
ms.assetid: 2977cf92-98b5-48b2-b0fd-8fbc7040f2b4
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: a943d0ed7cfb0932f7eec757b40fef4d8de6504c
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52775045"
---
# <a name="map-many-to-many-relationships-visual-database-tools"></a>다 대 다 관계 매핑(Visual Database Tools)
  다 대 다 관계를 사용하면 한 테이블의 각 행을 다른 테이블의 여러 행에 연결하거나 그 반대로 행을 연결할 수 있습니다. 예를 들어, 각 작가를 해당 작가의 모든 저서에 연결하고 각 도서를 모든 해당 작가에 연결하도록 `authors` 테이블과 `titles` 테이블 사이에 다 대 다 관계를 만들 수 있습니다. 각 테이블에서 일 대 다 관계를 만드는 것만으로는 모든 도서가 한 명의 작가에게만 연결되거나 모든 작가가 한 권의 책만 쓴 것으로 잘못 표시될 수 있습니다.  
  
 테이블 사이의 다 대 다 관계는 병합 테이블을 통해 데이터베이스에 적용됩니다. 병합 테이블에는 연결하려는 두 테이블의 기본 키 열이 포함됩니다. 병합 테이블의 열에 일치하도록 이러한 두 테이블 각각의 기본 키 열에서 관계를 만듭니다. pubs 데이터베이스에서 병합 테이블은 `titleauthor` 테이블입니다.  
  
### <a name="to-create-a-many-to-many-relationship-between-tables"></a>테이블 사이에 다 대 다 관계를 만들려면  
  
1.  데이터베이스 다이어그램에서 다 대 다 관계를 만들려는 두 테이블을 추가합니다.  
  
2.  다이어그램을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **새 테이블** 을 선택하여 세 번째 테이블을 만듭니다. 이 테이블이 병합 테이블로 사용됩니다.  
  
3.  **이름 선택** 대화 상자에서 시스템 할당 테이블 이름을 변경합니다. 예를 들어, `titles` 테이블과 `authors` 테이블 사이의 병합 테이블 이름으로 `titleauthors`를 지정할 수 있습니다.  
  
4.  다른 두 테이블 각각의 기본 키 열을 병합 테이블에 복사합니다. 일반적인 테이블 작업의 경우와 마찬가지로 다른 열을 이 테이블에 추가할 수 있습니다.  
  
5.  병합 테이블에서 다른 두 테이블의 기본 키 열이 모두 포함되도록 기본 키를 설정합니다. 자세한 내용은 참조 하세요 [Create Primary Keys](../../relational-databases/tables/create-primary-keys.md)합니다.  
  
6.  두 개의 각 기본 테이블과 병합 테이블 사이에 일 대 다 관계를 정의합니다. 병합 테이블은 작성된 두 관계 모두에서 "다" 쪽에 있어야 합니다. 자세한 내용은 참조 하세요 [Create Foreign Key Relationships](../../relational-databases/tables/create-foreign-key-relationships.md)합니다.  
  
    > [!NOTE]  
    >  데이터베이스 다이어그램에서 병합 테이블을 만들어도 관련 테이블의 데이터가 병합 테이블에 삽입되지는 않습니다. 테이블에 데이터를 삽입하는 방법에 대한 자세한 내용은 [결과 삽입 쿼리 만들기&#40;Visual Database Tools&#41;](visual-database-tools.md)를 참조하세요.  
  
## <a name="see-also"></a>관련 항목  
 [데이터베이스 다이어그램 작업&#40;Visual Database Tools&#41;](work-with-database-diagrams-visual-database-tools.md)  
  
  
