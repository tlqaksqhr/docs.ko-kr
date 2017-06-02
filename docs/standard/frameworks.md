---
title: "대상 프레임워크 | Microsoft 문서"
description: ".NET Core 응용 프로그램 및 라이브러리에 대한 대상 프레임워크 관련 정보입니다."
keywords: ".NET, .NET Core, 프레임워크, TFM"
author: richlander
ms.author: mairaw
ms.date: 04/27/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 6ef56a2e-593d-497b-925a-1e25bb6df2e6
ms.translationtype: Machine Translation
ms.sourcegitcommit: 45835eb80642253f80ea630ae9db1ac766b72b9c
ms.openlocfilehash: 11c1f11e4f8354b7573d03e680cf4a8a16fa26d9
ms.contentlocale: ko-kr
ms.lasthandoff: 05/11/2017

---

# <a name="target-frameworks"></a>대상 프레임워크

*프레임워크*는 앱과 라이브러리를 만드는 데 사용할 개체, 메서드 및 도구를 정의합니다. .NET Framework는 Windows 운영 체제를 실행하는 시스템에서 실행할 앱 및 라이브러리를 만드는 데 사용됩니다. .NET Core에는 다양한 운영 체제에서 실행되는 앱 및 라이브러리를 빌드하는 데 사용되는 프레임워크가 포함됩니다.

*프레임워크* 및 *플랫폼*이라는 용어는 구에서 사용되는 방법에 따라 혼동되는 경우가 있습니다. 잘못 해석될 경우 *플랫폼*은 컨텍스트에 따라 다른 의미를 가집니다. 예를 들어 “.NET Core”는 앱 및 라이브러리 빌드의 컨텍스트에서는 “.NET Core 프레임워크”로 설명되고, 앱 및 라이브러리 코드가 실행되는 컨텍스트에서는 “.NET Core 플랫폼”으로 설명됩니다. *컴퓨팅 플랫폼*은 응용 프로그램이 실행되는 *위치 및 방법*을 설명합니다. .NET Core는 [.NET CoreCLR(Core 공용 언어 런타임)](https://github.com/dotnet/coreclr)을 사용하여 코드를 실행하므로 플랫폼이기도 합니다. .NET Framework의 프레임워크 개체, 메서드 및 도구로 개발된 앱 및 라이브러리 코드를 실행하기 위한 [CLR(공용 언어 런타임)](clr.md)가 포함된 .NET Framework의 경우에도 마찬가지입니다. “플랫폼 간”이라는 용어가 문서에서 자주 보이지만 이 용어를 볼 경우 작성자가 일반적으로 전달하고자 하는 의미 때문에 “운영 체제 간 및 아키텍처 간(x86, x64, arm)”을 생각해야 합니다.

프레임워크의 개체 및 메서드를 API(응용 프로그램 인터페이스)라고 합니다. 프레임워크 API는 [Visual Studio](https://www.visualstudio.com/), [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/), [Visual Studio Code](https://code.visualstudio.com/), 기타 IDE(통합 개발 환경) 및 편집기에서 개발을 위한 올바른 개체 및 메서드 집합을 제공하는 데 사용됩니다. [NuGet](https://www.nuget.org/)에서도 NuGet 패키지의 프로덕션 및 소비에 프레임워크를 사용하여 앱 또는 라이브러리에서 대상으로 지정할 프레임워크에 대한 적절한 패키지를 생성 및 사용하도록 합니다.

하나 이상의 *프레임워크를 대상으로 지정*하면 사용하려는 API 집합 및 해당 API의 버전이 결정됩니다. 프레임워크는 제품 이름별, 길거나 짧은 형식의 프레임워크 이름별, 패밀리별 등의 여러 방법으로 참조됩니다.

## <a name="referring-to-frameworks"></a>프레임워크 참조

프레임워크를 참조하는 여러 가지 방법이 있으며, 대부분 전체 .NET Core 문서에서 사용됩니다. 예를 들어 .NET Framework 4.6.2의 경우 다음 형식이 사용됩니다.

**제품 참조**

.NET 플랫폼 또는 런타임을 참조할 수 있습니다. 둘 다 유효합니다.

* .NET Framework 4.6.2
* .NET 4.6.2

**프레임워크 참조**

길거나 짧은 형식의 TFM을 사용하여 프레임워크 또는 프레임워크의 대상 지정을 참조할 수 있습니다. 둘 다 유효합니다.

* `.NETFramework,Version=4.6.2`
* `net462`

**프레임워크 패밀리 참조**

길거나 짧은 형식의 프레임워크 ID를 사용하여 프레임워크 패밀리를 참조할 수 있습니다. 둘 다 유효합니다.

* `.NETFramework`
* `net`

## <a name="latest-framework-versions"></a>최신 프레임워크 버전

다음 표에서는 사용할 수 있는 프레임워크 집합, 프레임워크가 참조되는 방법 및 프레임워크에서 구현하는 [.NET 표준 라이브러리](library.md) 버전을 정의합니다. 이러한 프레임워크 버전은 안정적인 최신 버전입니다. 시험판 버전은 표시되지 않습니다.

| 프레임워크             | 최신 버전 | TFM(대상 프레임워크 모니커) | Compact TFM(대상 프레임워크 모니커) | .NET 표준 버전 | Metapackage |
| :-------------------: | :------------: | :----------------------------: | :------------------------------------: | :-------------------: | :---------: |
| .NET 표준         | 1.6.1          | .NETStandard,Version=1.6       | netstandard1.6                         | N/A                   | [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library) |
| .NET Core 응용 프로그램 | 1.1.1          | .NETCoreApp,Version=1.1        | netcoreapp1.1                          | 1.6                   | [Microsoft.NETCore.App](https://www.nuget.org/packages/Microsoft.NETCore.App) |
| .NET Framework        | 4.6.2          | .NETFramework,Version=4.6.2    | net462                                 | 1.5                   | N/A |

## <a name="supported-frameworks"></a>지원되는 프레임워크

프레임워크는 대개 짧은 대상 프레임워크 모니커 또는 *TFM*에서 참조됩니다. .NET 표준에서 이 프레임워크는 *TxM*으로 일반화되어 여러 프레임워크에 대한 단일 참조를 허용합니다. NuGet 클라이언트는 다음 프레임워크를 지원합니다. 일치하는 항목은 대괄호(`[]`) 내에 표시됩니다.

| 이름                       | 약어 | TFM/TxM                                    |
| -------------------------- | ------------ | -------------------------------------------- |
| .NET 표준              | netstandard  | netstandard1.0                               |
|                            |              | netstandard1.1                               |
|                            |              | netstandard1.2                               |
|                            |              | netstandard1.3                               |
|                            |              | netstandard1.4                               |
|                            |              | netstandard1.5                               |
|                            |              | netstandard1.6                               |
| .NET Core                  | netcoreapp   | netcoreapp1.0                                |
|                            |              | netcoreapp1.1                                |
| .NET Framework             | net          | net11                                        |
|                            |              | net20                                        |
|                            |              | net35                                        |
|                            |              | net40                                        |
|                            |              | net403                                       |
|                            |              | net45                                        |
|                            |              | net451                                       |
|                            |              | net452                                       |
|                            |              | net46                                        |
|                            |              | net461                                       |
|                            |              | net462                                       |
| Windows 스토어              | netcore      | netcore [netcore45]                          |
|                            |              | netcore45 [win, win8]                        |
|                            |              | netcore451 [win81]                           |
| .NET Micro Framework       | netmf        | netmf                                        |
| Silverlight                | sl           | sl4                                          |
|                            |              | sl5                                          |
| Windows Phone              | wp           | wp [wp7]                                     |
|                            |              | wp7                                          |
|                            |              | wp75                                         |
|                            |              | wp8                                          |
|                            |              | wp81                                         |
|                            |              | wpa81                                        |
| 범용 Windows 플랫폼 | uap          | uap [uap10.0]                                |
|                            |              | uap10.0 [win10] [netcore50]                  |

## <a name="deprecated-frameworks"></a>사용되지 않는 프레임워크

다음 프레임워크는 사용되지 않습니다. 이러한 프레임워크를 대상으로 하는 패키지는 지정된 대체 항목으로 마이그레이션되어야 합니다.

| 사용되지 않는 프레임워크 | Replacement |
| -------------------- | ----------- |
| aspnet50             | netcoreapp  |
| aspnetcore50         |             |
| dnxcore50            |             |
| dnx                  |             |
| dnx45                |             |
| dnx451               |             |
| dnx452               |             |
| dotnet               | netstandard |
| dotnet50             |             |
| dotnet51             |             |
| dotnet52             |             |
| dotnet53             |             |
| dotnet54             |             |
| dotnet55             |             |
| dotnet56             |             |
| netcore50            | uap10.0     |
| win                  | netcore45   |
| win8                 | netcore45   |
| win81                | netcore451  |
| win10                | uap10.0     |
| winrt                | netcore45   |

## <a name="precedence"></a>우선 순위

많은 프레임워크가 서로 관련되고 호환되지만 반드시 일치하는 것은 아닙니다.

| 프레임워크                        | 사용 가능   |
| -------------------------------- | --------- |
| uap(유니버설 Windows 플랫폼) | win81     |
|                                  | wpa81     |
|                                  | netcore50 |
| win(Windows 스토어)              | winrt     |
|                                  | winrt45   |

## <a name="net-standard"></a>.NET 표준

[.NET 표준](https://github.com/dotnet/standard)은 이진 호환 가능 프레임워크 간의 참조를 간소화하여 단일 대상 프레임워크가 다른 프레임워크의 조합을 참조하도록 합니다. 자세한 내용은 [.NET 표준 라이브러리](library.md) 항목을 참조하세요.

[NuGet Tools Get Nearest Framework Tool](http://nugettoolsdev.azurewebsites.net/)(NuGet 도구는 가장 가까운 프레임워크를 가져옴)에서는 프로젝트의 프레임워크에 따라, 패키지의 여러 사용 가능한 프레임워크 자산 중 하나의 프레임워크를 선택하는 데 사용되는 NuGet 논리를 시뮬레이트합니다. 도구를 사용하려면 하나의 프로젝트 프레임워크 및 하나 이상의 패키지 프레임워크를 입력합니다. **제출** 단추를 선택합니다. 도구는 나열하는 패키지 프레임워크가 제공하는 프로젝트 프레임워크와 호환되는지 여부를 나타냅니다.

## <a name="portable-class-libraries"></a>이식 가능한 클래스 라이브러리

이식 가능한 클래스 라이브러리에 대한 자세한 내용은 NuGet 문서에서 *Target Framework*(대상 프레임워크) 항목의 [Portable Class Libraries](https://docs.microsoft.com/nuget/schema/target-frameworks#portable-class-libraries)(이식 가능한 클래스 라이브러리) 섹션을 참조하세요. Stephen Cleary는 지원되는 PCL을 나열하는 도구를 만들었습니다. 자세한 내용은 [Framework Profiles in .NET](http://blog.stephencleary.com/2012/05/framework-profiles-in-net.html)(.NET의 프레임워크 프로필)을 참조하세요.

