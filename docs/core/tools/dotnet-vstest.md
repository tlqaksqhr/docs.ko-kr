---
title: "dotnet vstest 명령 - .NET Core CLI"
description: "dotnet vtest 명령은 프로젝트와 모든 종속성을 빌드합니다."
author: guardrex
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: f2ad875430b2dc7f0ffbadfb9a39dd83854557cb
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="dotnet-vstest"></a>dotnet vstest

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet-vstest` - 지정한 파일에서 테스트를 실행합니다.

## <a name="synopsis"></a>개요

`dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]`

## <a name="description"></a>설명

`dotnet-vstest` 명령은 `VSTest.Console` 명령줄 응용 프로그램을 실행하여 자동화된 단위 및 코딩된 UI 응용 프로그램 테스트를 실행합니다.

## <a name="arguments"></a>인수

`TEST_FILE_NAMES`

지정한 어셈블리에서 테스트를 실행합니다. 여러 테스트 어셈블리 이름을 공백으로 구분합니다.

## <a name="options"></a>옵션

`--Settings|/Settings:<Settings File>`

테스트를 실행할 때 사용할 설정입니다.

`--Tests|/Tests:<Test Names>`

제공된 값과 같은 이름의 테스트를 실행합니다. 여러 값을 쉼표로 구분합니다.

`--TestAdapterPath|/TestAdapterPath`

테스트 실행에서 지정된 경로(있는 경우)의 사용자 지정 테스트 어댑터를 사용합니다.

`--Platform|/Platform:<Platform type>`

테스트를 실행하는 데 사용되는 대상 플랫폼 아키텍처입니다. 유효한 값은 `x86`, `x64` 및 `ARM`입니다.

`--Framework|/Framework:<Framework Version>`

테스트 실행에 사용되는 대상 .NET Framework 버전입니다. 유효한 값의 예로 `.NETFramework,Version=v4.6`, `.NETCoreApp,Version=v1.0` 등이 있습니다. 지원되는 기타 값에는 `Framework35`, `Framework40`, `Framework45` 및 `FrameworkCore10`이 있습니다.

`--Parallel|/Parallel`

테스트를 병렬로 실행합니다. 기본적으로 컴퓨터의 사용 가능한 모든 코어를 사용할 수 있습니다. 설정 파일을 사용하여 명시적인 코어 수를 설정합니다.

`--TestCaseFilter|/TestCaseFilter:<Expression>`

지정된 식과 일치하는 테스트를 실행합니다. `<Expression>`은 `<property>Operator<value>[|&<Expression>]` 형식입니다. 여기서 Operator는 `=`, `!=` 또는 `~` 중 하나입니다.  연산자 `~`는 '포함' 의미 체계를 가지며 `DisplayName`과 같은 문자열 속성에 적용됩니다. 하위 식을 그룹으로 묶는 데 괄호 `()`를 사용합니다.

`-?|--Help|/?|/Help`

명령에 대한 간단한 도움말을 출력합니다.

`--logger|/logger:<Logger Uri/FriendlyName>`

테스트 결과에 대해 로거를 지정합니다.  

* Team Foundation Server에 테스트 결과를 게시하려면 `TfsPublisher` 로거 공급자를 사용합니다.

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* Visual Studio 테스트 결과 파일(TRX)에 결과를 기록하려면 `trx` 로거 공급자를 사용합니다. 이 스위치는 지정된 로그 파일 이름을 사용하여 테스트 결과 디렉터리에 파일을 만듭니다. `LogFileName`이 제공되지 않으면 테스트 결과를 포함할 고유한 파일 이름이 만들어집니다.

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

지정된 테스트 컨테이너에서 검색된 테스트를 나열합니다.

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

현재 프로세스를 시작하는 일을 담당하는 부모 프로세스의 프로세스 ID입니다.

`--Port|/Port:<Port>`

소켓 연결 및 이벤트 메시지를 받기 위한 포트를 지정합니다.

`--Diag|/Diag:<Path to log file>`

테스트 플랫폼에 대한 자세한 정보 로그를 사용하도록 설정합니다. 로그는 제공된 파일에 기록됩니다.

`args`

어댑터에 전달될 추가 인수를 지정합니다. 인수는 `<n>=<v>` 형식의 이름-값 쌍으로 지정됩니다. 여기서 `<n>`은 인수 이름이고 `<v>`는 인수 값입니다. 여러 개의 인수를 구분하려면 공백을 사용합니다.

## <a name="examples"></a>예제

`mytestproject.dll`에서 테스트를 실행합니다.

`dotnet vstest mytestproject.dll`

사용자 지정 이름으로 사용자 지정 폴더로 내보내 `mytestproject.dll`에서 테스트를 실행합니다.

`dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path`

`mytestproject.dll` 및 `myothertestproject.exe`에서 테스트를 실행합니다.

`dotnet vstest mytestproject.dll myothertestproject.exe`

`TestMethod1` 테스트를 실행합니다.

`dotnet vstest /Tests:TestMethod1`

`TestMethod1` 및 `TestMethod2` 테스트를 실행합니다.

`dotnet vstest /Tests:TestMethod1,TestMethod2`

