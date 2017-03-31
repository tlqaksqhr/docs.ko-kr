---
title: "Visual Studio 2017을 사용하여 Hello World 응용 프로그램 게시"
description: "Visual Studio 2017을 사용하여 Hello World 응용 프로그램 게시"
keywords: ".NET, .NET Core, .NET Core 콘솔 응용 프로그램, 게시(.NET Core), 배포(.NET Core)"
author: stevehoag
ms.author: shoag
ms.date: 10/24/2016
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a19545d3-24af-4a32-9778-cfb5ae938287
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f4a30d19e111d395088e38c4543c9dacee6105fd
ms.lasthandoff: 03/13/2017

---

# <a name="publishing-your-hello-world-application-with-visual-studio-2017"></a>Visual Studio 2017을 사용하여 Hello World 응용 프로그램 게시

[Visual Studio 2017에서 .NET Core를 사용하여 C# Hello World 응용 프로그램 빌드](with-visual-studio-2017.md)에서 Hello World 콘솔 응용 프로그램을 빌드하고 [Visual Studio 2017을 사용하여 C# Hello World 응용 프로그램 디버그](debugging-with-visual-studio-2017.md)에서 Visual Studio 디버거를 사용하여 프로그램을 테스트했습니다. 예상대로 작동하는지 확인했으므로 다른 사용자가 실행할 수 있도록 게시할 수 있습니다. 게시를 하면 응용 프로그램을 실행하는 데 필요한 파일 집합이 만들어집니다. 이 파일 집합을 대상 컴퓨터에 복사하여 배포할 수 있습니다.

응용 프로그램을 게시하고 실행하려면 

1. Visual Studio에서 릴리스 버전의 응용 프로그램을 빌드하고 있는지 확인합니다. 필요한 경우 다음 그림과 같이 도구 모음의 빌드 구성 설정을 **디버그**에서 **릴리스**로 변경합니다.

   ![이미지](media/release.jpg)

1. 콘솔 창을 엽니다. 예를 들어 Windows 작업 표시줄의 **무엇이든 물어보세요.** 텍스트 상자에 `Command Prompt`를 입력한 다음 **명령 프롬프트** 데스크톱 앱을 선택하여 콘솔 창을 엽니다.

1. HelloWorld 프로젝트(HelloWorld 솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 메뉴에서 **게시**를 선택합니다. 주 Visual Studio에서 **빌드** 메뉴에서 **HelloWorld 게시**를 선택할 수도 있습니다.

1. 다음 그림과 같은 **게시** 대화 상자가 나타나면 **새 프로필 만들기**를 선택하여 새 게시 프로필을 만듭니다.

1. 그림과 같이 **게시 대상 선택** 대화 상자에서 **확인** 단추를 선택하여 로컬 파일 시스템에 응용 프로그램을 게시합니다. 이 프로그램은 응용 프로그램 프로젝트 디렉터리의 bin\release\PublishOutput 하위 디렉터리에서 찾을 수 있습니다.

1. 지금까지 게시 프로필을 만들었으므로 다음 그림과 같이 **게시** 대화 상자에서 **게시** 단추를 선택합니다.

   ![이미지](media/publish-2.jpg)

1. 다음 그림에서 알 수 있듯이, 게시된 출력에는 응용 프로그램을 구성하며 대상 시스템으로 복사해서 배포할 수 있는 다음 세 개의 파일이 포함됩니다.

      - HelloWorld.dll
   
      - HelloWorld.deps.json

      - HelloWorld.runtimeconfig.json

   네 번째 파일인 HelloWorld.pdb에는 디버그 기호가 포함됩니다. 게시된 응용 프로그램 버전을 디버그해야 하는 경우에는 이 파일을 저장해야 하지만 그렇지 않으면 응용 프로그램과 함께 배포할 필요가 없습니다.

   ![이미지](media/pub-files.jpg)

게시 프로세스는 프레임워크 종속 배포를 만듭니다. 즉, 게시된 응용 프로그램은 시스템에 .NET Core가 설치되어 있기만 하면 .NET Core에서 지원하는 모든 플랫폼에서 실행될 수 있습니다. 사용자는 콘솔 창에서 `dotnet.exe HelloWorld.dll` 명령을 실행하여 응용 프로그램을 실행할 수 있습니다.

.NET Core 응용 프로그램 게시 및 배포에 대한 자세한 내용은 [.NET Core 응용 프로그램 배포](../../core/deploying/index.md)를 참조하세요.
