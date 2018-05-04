---
title: .NET 이식성 분석기 - .NET
description: .NET 이식성 분석기 도구를 사용하여 .NET Core, .NET Standard, UWP 및 Xamarin을 비롯한 다양한 .NET 구현에서 코드가 얼마나 이식성이 있는지 평가하는 방법을 알아봅니다.
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 07/26/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3d813292a821c2ebfa7b40ee873cf36e71104ebf
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="the-net-portability-analyzer"></a>.NET 이식성 분석기

라이브러리를 다중 플랫폼으로 만들고 싶으세요? 응용 프로그램이 iOS, Android 및 Mac용 .NET Core, .NET Standard, UWP 및 Xamarin을 비롯한 다른 .NET 구현 및 프로필과 호환되도록 하는 데 필요한 작업량을 확인하고 싶으세요? [.NET 이식성 분석기](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)는 어셈블리를 분석하여 프로그램이 .NET 구현에서 얼마나 유연한지에 대한 자세한 보고서를 제공하는 도구입니다. 이식성 분석기는 Visual Studio 확장 및 콘솔 앱으로 제공됩니다.

## <a name="new-targets"></a>새 대상

* [.NET Core](../../core/index.md): 모듈형 디자인을 포함하고, Side-by-Side를 이용하며, 플랫폼 간 시나리오를 대상으로 합니다. Side-by-Side를 사용하면 다른 앱을 중단하지 않고 새로운 .NET Core 버전을 채택할 수 있습니다.
* [ASP.NET Core](/aspnet/core): .NET Core를 기반으로 하는 최신 웹 프레임워크이므로 개발자에게 동일한 혜택을 제공합니다.
* [유니버설 Windows 플랫폼](https://blogs.msdn.microsoft.com/dotnet/2014/04/24/net-native-performance): .NET 네이티브의 정적 컴파일을 사용하여 x64 및 ARM 컴퓨터에서 실행되는 Windows 스토어 앱의 성능을 향상합니다. 
* .NET Core + 플랫폼 확장: .NET Core API뿐만 아니라 WCF, ASP.NET Core, FSharp 및 Azure 같은 .NET 에코시스템의 다른 API도 포함합니다.
* .NET Standard + 플랫폼 확장: .NET Standard API뿐만 아니라 WCF, ASP.NET Core, FSharp 및 Azure 같은 다른 .NET 에코시스템도 포함합니다.

## <a name="how-to-use-portability-analyzer"></a>이식성 분석기를 사용하는 방법

.NET 이식성 분석기 사용을 시작하려면 먼저 [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)에서 확장을 다운로드하고 설치해야 합니다. Visual Studio 2015 및 Visual Studio 2017에서 작동합니다. Visual Studio에서 **분석** > **Portability Analyzer Settings**(이식성 분석기 설정)를 통해 구성하고 대상 플랫폼을 선택할 수 있습니다.

![이식성 스크린샷](./media/portability-analyzer/portability-screenshot.png)

전체 프로젝트를 분석하려면 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **어셈블리 이식성 분석**을 선택합니다. 전체 프로젝트를 분석하지 않으려면 **분석** 메뉴로 이동한 다음 **어셈블리 이식성 분석**을 선택합니다. 여기서 프로젝트의 실행 파일 또는 DLL을 선택합니다.

![이식성 솔루션 탐색기](./media/portability-analyzer/portability-solution-explorer.png)

분석을 실행한 후 .NET 이식성 보고서를 확인합니다. 대상 플랫폼에서 지원되지 않는 형식만 목록에 표시되며, **오류 목록**의 **메시지** 탭에서 권장 사항을 검토할 수 있습니다. **메시지** 탭에서 문제 영역으로 직접 이동할 수도 있습니다.

![이식성 보고서](./media/portability-analyzer/portability-report.png)

Visual Studio를 사용하고 싶지 않으신가요? 명령 프롬프트에서 이식성 분석기를 사용할 수도 있습니다. [API 이식성 분석기](http://www.microsoft.com/download/details.aspx?id=42678)를 다운로드합니다.

*   현재 디렉터리를 분석하려면 다음 명령을 입력합니다. `\...\ApiPort.exe analyze -f .`
*   .dll 파일의 특정 목록을 분석하려면 다음 명령을 입력합니다. `\...\ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`

.NET 이식성 보고서는 현재 디렉터리에 Excel 파일(*.xlsx*)로 저장됩니다. Excel 통합 문서의 **세부 정보** 탭에는 추가 정보가 포함됩니다.

.NET 이식성 분석기에 대한 자세한 내용은 [GitHub 문서](https://github.com/Microsoft/dotnet-apiport#documentation) 및 [A Brief Look at the .NET Portability Analyzer](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer)(.NET 이식성 분석기 간단하게 살펴보기) Channel 9 비디오를 참조하세요.
