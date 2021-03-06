---
title: mssqlctl 클러스터 참조
titleSuffix: SQL Server big data clusters
description: Mssqlctl 클러스터 명령에 대 한 참조 문서입니다.
author: rothja
ms.author: jroth
manager: craigg
ms.date: 02/28/2019
ms.topic: reference
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: e4e54ac3c7206ad8a6592c8cfe0b45d9ea4b8fd8
ms.sourcegitcommit: 2de5446fbc57787f18a907dd5deb02a7831ec07d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58860474"
---
# <a name="mssqlctl-cluster"></a>mssqlctl 클러스터

[!INCLUDE[tsql-appliesto-ssver15-xxxx-xxxx-xxx](../includes/tsql-appliesto-ssver15-xxxx-xxxx-xxx.md)]

다음 문서에 대 한 참조를 제공 합니다 **클러스터** 명령에 **mssqlctl** 도구입니다. 다른 방법에 대 한 자세한 내용은 **mssqlctl** 명령 참조 [mssqlctl 참조](reference-mssqlctl.md)합니다.

## <a id="commands"></a> 명령

|||
|---|---|
| [만들기](#create) | 클러스터를 만듭니다. |
| [삭제](#delete) | 클러스터를 삭제 합니다. |
| [config](reference-mssqlctl-cluster-config.md) | 클러스터 구성 명령입니다. |
| [디버그](reference-mssqlctl-cluster-debug.md) | 명령을 디버그 합니다. |

## <a id="create"></a> mssqlctl 클러스터 만들기

클러스터를 만듭니다.

```
mssqlctl cluster create
   --name
   --accept-eula
```

### <a name="parameters"></a>매개 변수

| 매개 변수 | Description |
|---|---|
| **--name -n** | Kubernetes 네임 스페이스에 대해 사용 되는 클러스터 이름입니다. |
| **--accept-eula -e** | 사용 약관 수락 하 시겠습니까? \[yes/no\].  허용 되는 값: 아니요, 예입니다. 필수 사항입니다. |

## <a id="delete"></a> mssqlctl 클러스터 삭제

클러스터를 삭제 합니다.

```
mssqlctl cluster delete
   --name
   [--force]
```

### <a name="parameters"></a>매개 변수

| 매개 변수 | Description |
|---|---|
| **--name -n** | Kubernetes 네임 스페이스에 대해 사용 되는 클러스터 이름입니다. 필수 사항입니다. |
| **--force -f** | 강제 삭제 클러스터입니다. |

## <a name="next-steps"></a>다음 단계

다른 방법에 대 한 자세한 내용은 **mssqlctl** 명령 참조 [mssqlctl 참조](reference-mssqlctl.md)합니다. 설치 하는 방법에 대 한 자세한 합니다 **mssqlctl** 도구를 참조 하십시오 [SQL Server 2019 빅 데이터 클러스터를 관리 하는 mssqlctl 설치](deploy-install-mssqlctl.md)합니다.