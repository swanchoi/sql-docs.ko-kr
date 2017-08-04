---
title: "Docker에서 SQL Server 2017에 대 한 구성 옵션 | Microsoft Docs"
description: "및 SQL Server 2017 컨테이너 이미지 Docker에서 상호 작용에 사용 하 여 다양 한 방법을 탐색 합니다. 여기에 영구 데이터 파일을 복사 하 고 문제를 해결 합니다."
author: rothja
ms.author: jroth
manager: jhubbard
ms.date: 07/17/2017
ms.topic: article
ms.prod: sql-linux
ms.technology: database-engine
ms.assetid: 82737f18-f5d6-4dce-a255-688889fdde69
ms.custom: H1Hack27Feb2017
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: f87c28e4d2ba7689d422ccf2f1a903765a39f27a
ms.contentlocale: ko-kr
ms.lasthandoff: 08/02/2017

---
# <a name="configure-sql-server-2017-container-images-on-docker"></a>Docker에서 SQL Server 2017 컨테이너 이미지를 구성 합니다.

이 항목에서는 구성 및 사용 하는 방법에 설명 된 [mssql-서버-linux 컨테이너 이미지](https://hub.docker.com/r/microsoft/mssql-server-linux/) Docker가 있는 합니다. 이 이미지는 Ubuntu 16.04에 따라 Linux에서 실행 중인 SQL Server 구성 됩니다. Mac/Windows 용 Docker 엔진 1.8 + linux 또는 Docker에서 사용할 수 있습니다.

> [!NOTE]
> 이 항목 mssql-서버-linux 이미지를 사용 하 여에 특별히 중점을 둡니다. Windows 이미지 적용 되지 않는 있지만에서 항목에 대 한 자세히 알아볼 수 있습니다는 [mssql-서버-windows Docker 허브 페이지](https://hub.docker.com/r/microsoft/mssql-server-windows/)합니다.

## <a name="pull-and-run-the-container-image"></a>컨테이너 이미지를 실행 하 고 끌어오기

끌어오고 SQL Server 2017에 대 한 Docker 컨테이너 이미지를 실행 하는 데 다음 빠른 시작 자습서의 필수 구성 요소 및 단계를 따르십시오.

- [Docker가 있는 SQL Server 2017 컨테이너 이미지를 실행 합니다.](quickstart-install-connect-docker.md)

이 구성 항목 추가 연결 및 아래 섹션에 사용 시나리오를 제공합니다.

## <a name="connect-and-query"></a>연결 및 쿼리

연결 하 고 컨테이너는 컨테이너 외부에서 또는 내에서 SQL Server에 쿼리할 수는 컨테이너입니다. 다음 섹션에서는 두 시나리오를 설명 합니다. 

### <a name="tools-outside-the-container"></a>컨테이너 외부 도구

SQL 연결을 지 원하는 모든 외부 Linux, Windows 또는 macOS 도구에서 Docker 컴퓨터에 SQL Server 인스턴스에 연결할 수 있습니다. 몇 가지 일반적인 도구는 다음과 같습니다.

- [sqlcmd](sql-server-linux-setup-tools.md)
- [Visual Studio 코드](sql-server-linux-develop-use-vscode.md)
- [Windows에서 SQL Server Management Studio (SSMS)](sql-server-linux-develop-use-ssms.md)

다음 예제에서는 **sqlcmd** Docker 컨테이너에서 실행 되는 SQL Server에 연결 합니다. 연결 문자열에 IP 주소는 컨테이너를 실행 하 여 호스트 컴퓨터의 IP 주소입니다.

```bash
sqlcmd -S 10.3.2.4 -U SA -P '<YourPassword>'
```

```PowerShell
sqlcmd -S 10.3.2.4 -U SA -P "<YourPassword>"
```

기본 되지 않은 호스트 포트 매핑한 **1433**, 연결 문자열에 해당 포트를 추가 합니다. 예를 들어 지정한 `-p 1400:1433` 에 프로그램 `docker run` 명령, 다음으로 명시적으로 연결 1400 포트를 지정 합니다.

```bash
sqlcmd -S 10.3.2.4,1400 -U SA -P '<YourPassword>'
```

```PowerShell
sqlcmd -S 10.3.2.4,1400 -U SA -P "<YourPassword>"
```

### <a name="tools-inside-the-container"></a>컨테이너 내에서 도구

SQL Server 2017 CTP 2.0 부터는 [SQL Server 명령줄 도구](sql-server-linux-setup-tools.md) 컨테이너 이미지에 포함 됩니다. 대화형 명령 프롬프트를 사용 하 여 이미지에 연결 하는 경우 도구를 로컬로 실행할 수 있습니다.

1. 사용 하 여는 `docker exec -it` 는 대화형 bash 셸의 실행 중인 컨테이너 내 시작 명령입니다. 다음 예에서 `e69e056c702d` 컨테이너 ID입니다.

    ```bash
    docker exec -it e69e056c702d "bash"
    ```

    > [!TIP]
    > 항상 전체 컨테이너 id를 지정할 필요가 없습니다. 고유 하 게 식별 필요한 만큼의 문자를 지정 해야 합니다. 이 예제에서 사용 하기에 충분 한 않을 수도 것 `e6` 또는 `e69` 전체 id 대신 합니다.

2. 한 번, 컨테이너 내부 연결 로컬로 sqlcmd 합니다. Note 해당 sqlcmd 아니므로 기본적으로 경로에 전체 경로 지정 해야 합니다.

    ```bash
    /opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P '<YourPassword>'
    ```

3. Sqlcmd를 통해 완료 되 면 입력 `exit`합니다.

4. 대화형 명령 프롬프트로 완료 되 면 입력 `exit`합니다. 컨테이너에서 대화형 bash 셸의 종료 한 후 실행 계속 합니다.

## <a name="run-multiple-sql-server-containers"></a>여러 SQL Server 컨테이너를 실행 합니다.

Docker 같은 호스트 컴퓨터에서 여러 SQL Server 컨테이너를 실행 하는 방법을 제공 합니다. 동일한 호스트에서 SQL Server의 여러 인스턴스를 필요로 하는 시나리오에 대 한 접근 방식입니다. 각 컨테이너는 다른 포트에서 자체를 노출 해야 합니다.

다음 예제에서는 두 개의 SQL Server 컨테이너를 만들고 포트에서는 이러한 **1401** 및 **1402** 호스트 컴퓨터에 있습니다.

```bash
docker run -e 'ACCEPT_EULA=Y' -e 'MSSQL_SA_PASSWORD=<YourStrong!Passw0rd>' --cap-add SYS_PTRACE -p 1401:1433 -d microsoft/mssql-server-linux
docker run -e 'ACCEPT_EULA=Y' -e 'MSSQL_SA_PASSWORD=<YourStrong!Passw0rd>' --cap-add SYS_PTRACE -p 1402:1433 -d microsoft/mssql-server-linux
```

```PowerShell
docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=<YourStrong!Passw0rd>" --cap-add SYS_PTRACE -p 1401:1433 -d microsoft/mssql-server-linux
docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=<YourStrong!Passw0rd>" --cap-add SYS_PTRACE -p 1402:1433 -d microsoft/mssql-server-linux
```

이제 별도 컨테이너에서 실행 중인 SQL Server의 인스턴스 두 개가 있습니다. 클라이언트는 컨테이너에 대 한 Docker 호스트와 포트 번호의 IP 주소를 사용 하 여 각 SQL Server 인스턴스에 연결할 수 있습니다.

```bash
sqlcmd -S 10.3.2.4,1401 -U SA -P '<YourPassword>'
sqlcmd -S 10.3.2.4,1402 -U SA -P '<YourPassword>'
```

```PowerShell
sqlcmd -S 10.3.2.4,1401 -U SA -P "<YourPassword>"
sqlcmd -S 10.3.2.4,1402 -U SA -P "<YourPassword>"
```

## <a id="persist"></a>데이터 유지

SQL Server 구성 변경 및 데이터베이스 파일에에서 유지 되는 컨테이너와 컨테이너를 다시 시작 하는 경우에 `docker stop` 및 `docker start`합니다. 그러나 사용 하 여 컨테이너를 제거 하는 경우 `docker rm`, 컨테이너의 모든 내용이 삭제 되 SQL Server 및 데이터베이스를 포함 합니다. 다음 섹션에서는 사용 하는 방법에 설명 **데이터 볼륨** 관련된 컨테이너 삭제 한 경우에 데이터베이스 파일을 유지 하도록 합니다.

> [!IMPORTANT]
> 이 SQL Server에 대 한 Docker에서 지 속성 데이터를 이해 하는 중요 합니다. 이 섹션의 설명에서는 외에도 Docker의 설명서를 참조 [Docker 컨테이너의 데이터를 관리 하는 방법](https://docs.docker.com/engine/tutorials/dockervolumes/)합니다.

### <a name="mount-a-host-directory-as-data-volume"></a>데이터 볼륨으로 호스트 디렉터리 탑재

첫 번째 옵션은 호스트에 디렉터리를 컨테이너의 데이터 볼륨으로 탑재 합니다. 이 위해 사용 하 여는 `docker run` 명령에 `-v <host directory>:/var/opt/mssql` 플래그입니다. 따라서 데이터를 컨테이너 실행 간에 복원할 수 있습니다.

```bash
docker run -e 'ACCEPT_EULA=Y' -e 'MSSQL_SA_PASSWORD=<YourStrong!Passw0rd>' --cap-add SYS_PTRACE -p 1433:1433 -v <host directory>:/var/opt/mssql -d microsoft/mssql-server-linux
```

```PowerShell
docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=<YourStrong!Passw0rd>" --cap-add SYS_PTRACE -p 1433:1433 -v <host directory>:/var/opt/mssql -d microsoft/mssql-server-linux
```

또한이 기술을 공유 하 고 Docker 외부 호스트에서 파일을 볼 수 있습니다.

> [!IMPORTANT]
> 이 이번에는 Mac에서 Linux 이미지에서 SQL Server와 함께 Docker에 대 한 호스트 볼륨 매핑이 지원 되지 않습니다. 데이터 볼륨 컨테이너를 대신 사용 합니다. 이 제한은 관련 된 `/var/opt/msql` 디렉터리입니다. 탑재 디렉터리 작동에서 읽는 중입니다. 예를 들어-v를 사용 하 여 Mac의 호스트 디렉터리 탑재 하 고 호스트에 있는.bak 파일에서 백업 복원 수 있습니다.

### <a name="use-data-volume-containers"></a>데이터 볼륨 컨테이너를 사용 하 여

두 번째 방법은 데이터 볼륨 컨테이너를 사용 하는 것입니다. 사용 하 여 호스트 디렉터리 대신 볼륨 이름을 지정 하 여 데이터 볼륨 컨테이너를 만들 수는 `-v` 매개 변수입니다. 다음 예제에서는 공유 데이터 볼륨 v **sqlvolume**합니다.

```bash
docker run -e 'ACCEPT_EULA=Y' -e 'MSSQL_SA_PASSWORD=<YourStrong!Passw0rd>' --cap-add SYS_PTRACE -p 1433:1433 -v sqlvolume:/var/opt/mssql -d microsoft/mssql-server-linux
```

```PowerShell
docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=<YourStrong!Passw0rd>" --cap-add SYS_PTRACE -p 1433:1433 -v sqlvolume:/var/opt/mssql -d microsoft/mssql-server-linux
```

> [!NOTE]
> 이전 버전의 Docker run 명령에 암시적으로 데이터 볼륨을 만드는이 방법을 작동 하지 않습니다. 이 경우 Docker 설명서에 설명 된 명시적 단계를 사용 하 여 [만들기 및 데이터 볼륨 컨테이너를 탑재](https://docs.docker.com/engine/tutorials/dockervolumes/#creating-and-mounting-a-data-volume-container)합니다.

중지 하 고이 컨테이너를 제거 하는 경우에 데이터 볼륨을 유지 합니다. 사용 하 여 볼 수는 `docker volume ls` 명령입니다.

```bash
docker volume ls
```

볼륨 이름이 같은 다른 컨테이너 다음 만들면 새 컨테이너의 볼륨에 포함 된 동일한 SQL Server 데이터를 사용 합니다.

데이터 볼륨 컨테이너를 제거 하려면 사용 된 `docker volume rm` 명령입니다.

> [!WARNING]
> 컨테이너의 모든 SQL Server 데이터는 데이터 볼륨 컨테이너를 삭제 하면 *영구적으로* 삭제 합니다.

### <a name="backup-and-restore"></a>백업 및 복원
이러한 컨테이너 기술 외에도 표준 SQL Server 백업을 사용 하 고 복원 기술 수도 있습니다. 데이터를 보호 하거나 데이터를 다른 SQL Server 인스턴스로 이동 하려면 백업 파일을 사용할 수 있습니다. 자세한 내용은 참조 [Linux에서 SQL Server 데이터베이스 백업 및 복원](sql-server-linux-backup-and-restore-database.md)합니다.

> [!WARNING]
> 백업을 만들면를 만들거나 컨테이너의 외부 백업 파일을 복사 해야 합니다. 그렇지 않으면 컨테이너 제거 되는 경우 백업 파일이 삭제 됩니다.

## <a name="execute-commands-in-a-container"></a>컨테이너에서 명령 실행

실행 중인 컨테이너를 설정한 경우에 터미널 호스트에서 컨테이너 내에서 명령을 실행할 수 있습니다.

실행 하는 컨테이너 ID를 얻으려면:

```bash
docker ps
```

실행 하는 컨테이너에 터미널는 bash를 시작 합니다.

```bash
docker exec -ti <Container ID> /bin/bash
```

이제 터미널 컨테이너 내에서 실행 중인 것으로 명령을 실행할 수 있습니다. 완료 되 면 입력 `exit`합니다. 대화형 명령 세션에서이 종료 하지만 컨테이너는 계속 실행 합니다.

## <a name="copy-files-from-a-container"></a>컨테이너에서 파일 복사

컨테이너에서 파일을 복사 하려면 다음 명령을 사용 합니다.

```bash
docker cp <Container ID>:<Container path> <host path>
```

**예:**

```bash
docker cp d6b75213ef80:/var/opt/mssql/log/errorlog /tmp/errorlog
```

```PowerShell
docker cp d6b75213ef80:/var/opt/mssql/log/errorlog C:\Temp\errorlog
```

컨테이너에 파일을 복사 하려면 다음 명령을 사용 합니다.

```bash
docker cp <Host path> <Container ID>:<Container path>
```

**예:**

```bash
docker cp /tmp/mydb.mdf d6b75213ef80:/var/opt/mssql/data
```

```PowerShell
docker cp C:\Temp\mydb.mdf d6b75213ef80:/var/opt/mssql/data
```

## <a name="upgrade-sql-server-in-containers"></a>컨테이너에서 SQL Server 업그레이드

Docker가 있는 컨테이너 이미지를 업그레이드 하려면 레지스트리에서 최신 버전을 꺼냅니다. 사용 하 여 `docker pull` 명령:

```bash
docker pull microsoft/mssql-server-linux:latest
```

SQL Server 이미지를 만든 모든 새 컨테이너를 업데이트 하지만 모든 실행 중인 컨테이너의 SQL Server를 업데이트 하지 않습니다. 이 위해 새 컨테이너를 최신 SQL Server 컨테이너 이미지를 만들고 해야 해당 새 컨테이너에 데이터를 마이그레이션할 합니다.

1. 먼저 중 하나를 사용 하 고 있는지를 확인는 [데이터 지 속성 방법](#persist) 기존 SQL Server 컨테이너에 대 한 합니다.

2. 사용 하 여 SQL Server 컨테이너를 중지는 `docker stop` 명령입니다.

3. 사용 하 여 새 SQL Server 컨테이너 만들기 `docker run` 매핑된 호스트 디렉터리 또는 데이터 볼륨 컨테이너를 지정 합니다. 이제 새 컨테이너는 기존 SQL Server 데이터와 새 버전의 SQL Server를 사용합니다.

4. 데이터베이스와 새 컨테이너의에서 데이터를 확인 합니다.

5. 그러면 이전 컨테이너와 필요에 따라 제거 `docker rm`합니다.

## <a id="troubleshooting"></a>문제 해결

다음 섹션에서는 컨테이너에서 SQL Server를 실행 하기 위한 문제 해결 제안 사항을 제공 합니다.

### <a name="docker-command-errors"></a>Docker 명령 오류

에 대 한 오류가 발생할 경우 `docker` 명령 docker 서비스를 실행 중인지 확인 및 승격 된 권한으로 실행 하려고 합니다.

예를 들어 linux에서 오류가 발생할 수 있습니다는 다음 실행 하는 경우 `docker` 명령:

```
Cannot connect to the Docker daemon. Is the docker daemon running on this host?
```

Linux에이 오류를 발생 한 경우 앞에서 동일한 명령을 실행 해 `sudo`합니다. 실패할 경우 docker 서비스가 실행 되 고 필요에 따라 시작을 확인 합니다.

```bash
sudo systemctl status docker
sudo systemctl start docker
```

Windows에서는 시작 하는 PowerShell 또는 관리자 권한으로 명령 프롬프트 프로그램을 확인 합니다.

### <a name="sql-server-container-startup-errors"></a>SQL Server 컨테이너 시작 오류

SQL Server 컨테이너 실행이 실패 하면 다음 테스트 하세요.

- 와 같은 오류가 발생할 경우 **' 네트워크 브리지에서 CONTAINER_NAME 끝점을 만들지 못했습니다. 프록시를 시작 하지 못했습니다: 수신 대기 tcp 0.0.0.0:1433 바인딩할: 이미 사용 중인 주소입니다.'** , 컨테이너 포트 1433은 이미 사용 하는 포트를 매핑하려면 하려고 합니다. 이 호스트 컴퓨터에서 로컬로 SQL Server를 실행 하는 경우에 발생할 수 있습니다. 두 SQL Server 컨테이너를 시작 하 고 모두 동일한 호스트 포트 매핑을 시도 하는 경우에 발생할 수 있습니다. 사용 하 여 이런 경우는 `-p` 컨테이너 포트 1433 포트를 다른 호스트를 매핑하려면 매개 변수입니다. 예를 들어 

    ```bash
    docker run -e 'ACCEPT_EULA=Y' -e 'MSSQL_SA_PASSWORD=<YourStrong!Passw0rd>' --cap-add SYS_PTRACE -p 1400:1433 -d microsoft/mssql-server-linux`.
    ```

    ```PowerShell
    docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=<YourStrong!Passw0rd>" --cap-add SYS_PTRACE -p 1400:1433 -d microsoft/mssql-server-linux`.
    ```

- 컨테이너에서 모든 오류 메시지 인지를 확인 합니다.

    ```bash
    docker logs e69e056c702d
    ```

- 에 지정 된 최소 메모리 및 디스크 요구 사항을 충족 하는지 확인 해야는 [요구 사항](#requirements) 이 항목의 섹션입니다.

- 모든 컨테이너 관리 소프트웨어를 사용 하는 경우 루트로 실행 중인 컨테이너 프로세스를 지원 하는지 확인 합니다. Sqlservr 프로세스 컨테이너의 루트로 실행합니다.

- 검토는 [SQL Server 설치 프로그램 및 오류 로그](#errorlogs)합니다.

### <a name="sql-server-connection-failures"></a>SQL Server 연결 실패

사용자 컨테이너에서 실행 되는 SQL Server 인스턴스에 연결할 수 없는 경우에 다음 테스트 하십시오.

- SQL Server 컨테이너 확인 하 여 실행 중인지 확인 하십시오는 **상태** 의 열은 `docker ps -a` 출력 합니다. 그렇지 않은 경우 사용 하 여 `docker start <Container ID>` 시작 되려고 합니다.

- 기본이 아닌 호스트 포트 (1433)에 매핑되는 경우 연결 문자열에 포트를 지정 했는지 확인 합니다. 에 포트 매핑을 확인할 수 있습니다는 **포트** 의 열은 `docker ps -a` 출력 합니다. 예를 들어 다음 명령을 실행 sqlcmd 1401 포트에서 수신 대기 하는 컨테이너에 연결 합니다.

    ```bash
    sqlcmd -S 10.3.2.4,1401 -U SA -P '<YourPassword>'
    ```

    ```PowerShell
    sqlcmd -S 10.3.2.4,1401 -U SA -P "<YourPassword>"
    ```

- 사용 하는 경우 `docker run` 기존 매핑된 데이터 볼륨 또는 볼륨 컨테이너 데이터를 SQL Server의 값을 무시 `MSSQL_SA_PASSWORD`합니다. 대신, 데이터 볼륨 또는 데이터 볼륨 컨테이너에 있는 SQL Server 데이터로 미리 구성 된 SA 사용자 암호가 사용 됩니다. 에 연결 하는 데이터와 관련 된 SA 암호를 사용 하 고 있는지 확인 합니다.

- 검토는 [SQL Server 설치 프로그램 및 오류 로그](#errorlogs)합니다.

### <a name="sql-server-availability-groups"></a>SQL Server 가용성 그룹

Docker을 SQL Server 가용성 그룹을 사용 하는 경우 두 개의 추가 요구 사항이 있습니다.

- (기본값 5022) 복제 통신에 사용 되는 포트를 매핑하십시오. 예를 들어 지정 `-p 5022:5022` 의 일환으로 프로그램 `docker run` 명령입니다.

- 사용 하 여 컨테이너 호스트 이름을 명시적으로 설정 된 `-h YOURHOSTNAME` 의 매개 변수는 `docker run` 명령입니다. 가용성 그룹을 구성할 때이 호스트 이름이 사용 됩니다. 사용 하 여 지정 하지 않으면 `-h`, 기본적으로 컨테이너 id입니다.

### <a id="errorlogs"></a>SQL Server 설치 프로그램 및 오류 로그

SQL Server 설치 프로그램을 살펴볼 수 있습니다 및 오류 로그 **/var/opt/mssql/log**합니다. 컨테이너를 실행 하지 않는 경우에 먼저 컨테이너를 시작 합니다. 다음 명령 프롬프트를 대화형을 사용 하 여 로그를 검사 합니다.

```bash
docker start e69e056c702d
docker exec -it e69e056c702d "bash"
```

컨테이너 안에 bash 세션에서 다음 명령을 실행 합니다.

```bash
cd /var/opt/mssql/log
cat setup*.log
cat errorlog
```

> [!TIP]
> 호스트 디렉터리 탑재 **/var/opt/mssql** 컨테이너를 만들 때을 대신 참조는 **로그** 호스트에 매핑된 경로에 하위 디렉터리입니다.

## <a name="next-steps"></a>다음 단계

Docker에 SQL Server 2017 컨테이너 이미지를 통해 이동 하 여 시작 된 [빠른 시작 자습서](quickstart-install-connect-docker.md)합니다.

참고:는 [mssql docker GitHub 리포지토리](https://github.com/Microsoft/mssql-docker) 리소스, 피드백 및 알려진된 문제에 대 한 합니다.
