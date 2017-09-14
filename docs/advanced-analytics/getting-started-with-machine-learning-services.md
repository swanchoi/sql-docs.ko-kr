---
title: "SQL Server의 기계 학습 시작 | Microsoft Docs"
ms.custom: 
ms.date: 08/20/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- r-services
ms.tgt_pltfrm: 
ms.topic: article
author: jeannt
ms.author: jeannt
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 09d6e887a8c64c98a1c3f68c78b07c26da6ffb76
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="getting-started-with-machine-learning-in-sql-server"></a>기계 학습에서 SQL Server 시작

Microsoft은 온-프레미스와 클라우드 모두에 대 한 기계 학습 솔루션 통합 하 고 확장 가능한 집합을 제공 합니다.

+ **통합**, SQL Server에서 Python 또는 R을 실행할 수 있기 때문입니다. 이렇게 하면 쉽게 병합 엔터프라이즈 프로세스 ETL 및 데이터와 보고 기능 엔지니어링, 모델 생성 및 평가 같은 과학 작업에 대 한 합니다.
+ **확장 가능한**때문에 병렬 처리의 주요 작업와 같은 모델 학습 및 점수 매기기 또는 데이터 과학자 수 개발 및 노트북에 솔루션을 테스트 한 다음 배포에 대 한 여러 플랫폼에 배포 합니다. 지원 되는 플랫폼 창과 Hadoop, Spark에서 SQL Server를 포함 합니다.

이 문서에서는 Microsoft 기계 학습 플랫폼에서 각 제품에 대 한 리소스에 대 한 링크를 제공 합니다.

## <a name="machine-learning-in-sql-server"></a>SQL Server에서 학습 하는 컴퓨터

+ SQL Server 2017

  Python 추가 되 고 컴퓨터 학습 솔루션의 넓은 범위에 대 한 컴퓨터 학습 Services (In-database) 지원이 반영 되도록 하려면 이름을 변경에 대 한 SQL Server 2017 CTP 2.0에서 지원으로 시작 합니다. 이제 Python 또는 R 코드를 실행할 SQL 도구를 사용 하 여 기계 학습 작업을 자동화할 수 있습니다. 또는와 SQL Server 컴퓨터를 사용 하는 여는 _계산 컨텍스트_ 원격 개발 환경에서 실행 된 작업에 대 한 합니다.

    + [SQL Server에서 Python에 대 한 아키텍처 개요](python/architecture-overview-sql-server-python.md)
    + [SQL Server R Services 또는 시스템 학습 서비스 설정](../advanced-analytics/r/set-up-sql-server-r-services-in-database.md)

+ SQL Server 2016

  SQL Server 2016 저장된 프로시저를 사용 하 여 SQL Server의 R 코드 실행을 지원 합니다. 따라서 쉽게 SQL 도구를 사용 하 여 기계 학습 작업을 자동화할 수 있습니다. 또는와 SQL Server 컴퓨터를 사용 하는 동안 원격 랩톱 또는 R 개발 환경에서 R 코드를 실행할 수는 _계산 컨텍스트_합니다.

  이러한 통합 데이터에 대 한 보안을 제공 하 고 오른쪽에 사용 되는 리소스를 분산 하 고 관리할 수

    + [Getting Started 제품 SQL Server R Services](r/getting-started-with-sql-server-r-services.md)
    + [SQL Server R Services 또는 시스템 학습 서비스 설정](../advanced-analytics/r/set-up-sql-server-r-services-in-database.md)

## <a name="microsoft-machine-learning-server-microsoft-r-server"></a>Microsoft 기계 서버 (Microsoft R Server)를 학습 합니다.

학습 작업을 분산 하 고 확장 가능한 컴퓨터를 실행 하려는 하지만 사용 하는 등 SQL Server 데이터베이스 엔진과 통합 필요 하지 않습니다는 기업 고객을 지원 하기 위해 SQL Server 2017에 Microsoft 컴퓨터 학습 서버를 설치 하는 옵션 제공 sql 계산 컨텍스트를 선택 합니다.

SQL Server 2016의 Microsoft R Server를 설치 하는 옵션을 사용 합니다.
  
  + [Introducing Microsoft R Server](https://msdn.microsoft.com/microsoft-r/rserver)(Microsoft R Server 소개)
  
또한 MSDN에서 사용할 수 있는 플랫폼별 설치 관리자를 통해 R Server를 설치할 수 있습니다.

  + [R Server for Windows](https://msdn.microsoft.com/microsoft-r/rserver-install-windows)(Windows용 R Server)
  + [R 서버 Linux 용](https://msdn.microsoft.com/microsoft-r/rserver-install-linux-server)
  + [Hadoop에 대 한 R 서버](https://msdn.microsoft.com/microsoft-r/rserver-install-hadoop)

> [!IMPORTANT]
> R 서버를 사용 하 여 Python을 실행 하려는 경우 사용할 최신 버전을 설치 해야 **컴퓨터 학습 서버**, SQL Server 2017 설치를 사용할 때만 사용할 수:
> 
>    + [Microsoft R Server 또는 서버를 학습 하는 컴퓨터 설정](../advanced-analytics/r/create-a-standalone-r-server.md)

## <a name="related-products"></a>관련된 제품

+ [데이터 과학 클라이언트 설정](../advanced-analytics/r/set-up-a-data-science-client.md)

  이미 설치한 경우 서버 제품을 학습 하는 컴퓨터 중 하나를이 문서에서는 개발 및 도구 및 필요한 라이브러리를 비롯 하 여 솔루션을 테스트 하는 별도 컴퓨터를 설정 하는 방법에 대 한 정보를 제공 합니다.

+ [데이터 과학 가상 컴퓨터](../advanced-analytics/r/provision-the-r-server-only-sql-server-2016-enterprise-vm-on-azure.md)

  이 전체 기계 학습 Azure Marketplace의 솔루션을 가져와 학습 하는 컴퓨터에 항목을 빠르게 시작. SQL Server, Microsoft 컴퓨터 학습 서버 및 모든 개발 도구 (자주 축소 되어 "DSVM") 데이터 과학 가상 컴퓨터에 포함 되어 있습니다.
  
  데이터 과학 가상 컴퓨터 (DSVM)의 최신 버전의 Windows 10 사용자 지정 가능한 정리 모양을 제공할 Windows 2016 미리 보기 버전에서 실행 됩니다. 미리 구성 된 NVIDIA 드라이버, CUDA 도구 키트 8.0 및 GPU 작업을 위해 NVIDIA cuDNN 라이브러리가 함께 제공 됩니다.

## <a name="resources-for-learning"></a>학습을 위한 리소스

+ [컴퓨터 학습 자습서](../advanced-analytics/tutorials/machine-learning-services-tutorials.md)

  시작 하려면 SQL Server 2017 및 SQL Server 2017을 사용 하 여 컴퓨터 학습 솔루션에 대 한 학습 모든 리소스의 목록을 찾습니다.

### <a name="r-tutorials"></a>R 자습서

+ [SQL Server R 자습서](../advanced-analytics/tutorials/sql-server-r-tutorials.md)

   SQL Server에서 R을 실행할 만들고 원격 계산 컨텍스트를 사용 하거나 SQL Server를 사용 하 여 R에서 시뮬레이션을 수행 하는 방법에 알아봅니다.
   
   R IDE를 열지 않고도 SQL Server Management Studio에서 완벽 한 R 솔루션을 실행할 수 있도록 "제공 된 모든 코드" 자습서가 포함 되어!

+ [R과 ScaleR 25 간단한 함수에서 탐색](https://docs.microsoft.com/r-server/r/tutorial-r-to-revoscaler)

   R을 처음 사용하세요? Microsoft R (또는 RevoScaleR) 표준 R을 비교 하는 방법을 있는지 궁금 하십니까? R 서버에 대 한 이러한 빠른 시작을 참조 하십시오.

### <a name="python-tutorials"></a>Python 자습서

+ [SQL Server Python 자습서](../advanced-analytics/tutorials/sql-server-r-tutorials.md)

  Python SQL Server에서 실행 하는 방법에 알아봅니다. Python을 사용 하 여 모델을 작성 하 고 SQL Server 데이터 점수를 사용 합니다.

   SQL 개발자에 대 한 종단 간 솔루션을 Python SQL Server Management Studio에서 실행 해야 하는 모든 코드를 제공 합니다.

+ [게시 및 Python 코드를 사용 합니다.](../advanced-analytics/python/publish-consume-python-code.md)

  이 연습에서는 모델을 학습 서버 컴퓨터를 사용 하 여 웹 서비스에 배포 하는 데 필요한 모든 코드가 포함 되어 있습니다.

### <a name="product-samples-with-code"></a>코드와 제품 예제

SQL Server 개발 팀에서 이러한 솔루션, Python 또는 R에서 실행 하 고 기계 학습 비즈니스 응용 프로그램과 통합 하기 위한 일반적인 시나리오를 보여 줍니다.

+ [Build an intelligent app with SQL Server and R](https://microsoft.github.io/sql-ml-tutorials/R/rentalprediction)

+ [SQL Server 및 Python을 사용 하 여 지능형 앱 빌드](https://microsoft.github.io/sql-ml-tutorials/python/rentalprediction/)

### <a name="data-science-solution-templates"></a>데이터 과학 솔루션 템플릿

Microsoft 데이터 과학 팀에서 솔루션 템플릿을 특정 산업 또는 시나리오에 맞게 조정 된 완전 한 샘플 솔루션을 나타냅니다. 빠르고, 솔루션을 구현 하려면 또는 모범 사례를 보여 주기 위한 빌딩 블록 역할을 하는 것은. 각 서식 파일 예제 데이터 및 사용자 지정 가능한 코드를 포함합니다.

+ [솔루션 템플릿](../advanced-analytics/tutorials/data-science-scenarios-and-solution-templates.md)

## <a name="next-steps"></a>다음 단계

[SQL Server 컴퓨터 학습 서비스 시작](../advanced-analytics/r/getting-started-with-sql-server-r-services.md)

[서버를 학습 하는 Microsoft 컴퓨터 시작](../advanced-analytics/r/getting-started-with-microsoft-r-server-standalone.md)
