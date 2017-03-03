---
title: ".NET 아키텍처 구성 요소"
description: ".NET 표준 라이브러리, .NET 런타임 및 도구와 같은 주요 .NET 아키텍처 구성 요소를 설명합니다."
keywords: ".NET, .NET 표준 라이브러리, .NET 표준, .NET Core, .NET Framework, Xamarin, MSBuild, C#, F#, VB, 컴파일러"
author: cartermp
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 2e38e9d9-8284-46ee-a15f-199adc4f26f4
translationtype: Human Translation
ms.sourcegitcommit: 7741df222250f3746abb1e3c359bd9e89e6a732c
ms.openlocfilehash: e93764ff4d3391110c79f73a34512bd073ce0499
ms.lasthandoff: 01/18/2017

---

# <a name="net-architectural-components"></a>.NET 아키텍처 구성 요소

.NET은 많은 주요 구성 요소로 이루어져 있습니다.  위치에 상관없이 실행되는 다양한 API 집합인 표준 라이브러리가 포함되어 있으며, .NET 표준 라이브러리라고 합니다.  이 표준 라이브러리는 세 가지 .NET 런타임, 즉 .NET Framework, .NET Core 및 Xamarin용 Mono에 의해 구현됩니다.  .NET 언어는 어떤 .NET 런타임에서도 실행할 수 있습니다.  또한 프로젝트를 빌드할 수 있게 하는 플랫폼이면 모두 도구가 있습니다.  이러한 도구는 런타임 선택에 상관없이 동일합니다.

다음은 앞에서 언급한 각 .NET 구성 요소와, 이러한 구성 요소가 어떻게 연동하는지 그래픽으로 간략하게 보여 줍니다.

![.NET 아키텍처 구성 요소 전체 보기](media/components.png)

다음에서는 위에 표시된 주요 구성 요소 각각에 대해 간략하게 설명합니다.  

## <a name="net-standard-library"></a>.NET 표준 라이브러리

.NET 표준 라이브러리는 .NET 런타임에서 구현되는 API 집합입니다.

공식적으로 말하자면 코드를 컴파일할 균일한 계약 집합을 구성하는 .NET API 사양입니다.  이러한 계약에는 각 .NET 런타임에 대한 기본 구현 방식이 있습니다.  그러면 코드가 “어디서든 실행”될 수 있도록 여러 .NET 런타임 간에 이식할 수 있습니다.

.NET 표준 라이브러리는 .NET 표준으로 알려져 있는 빌드 대상이기도 합니다.  현재 .NET 표준 1.0~1.6을 대상으로 할 수 있습니다.  코드를 .NET 표준 버전을 대상으로 하는 경우에는 해당 버전을 구현하는 모든 .NET 런타임에서 실행됩니다.

표준 .NET 라이브러리와, .NET 표준을 대상으로 지정하는 방법을 알아보려면 [.NET 표준 라이브러리](library.md)를 참조하세요.

## <a name="net-runtimes"></a>.NET 런타임

Microsoft에서 적극적으로 개발하고 유지 관리하는 세 가지 기본 .NET 런타임은 .NET Core, .NET Framework 및 Xamarin용 Mono입니다.

### <a name="net-core"></a>.NET Core

.NET Core는 서버 작업을 위해 최적화된 플랫폼 간 런타임으로  .NET 표준 라이브러리를 구현합니다. 즉 .NET 표준을 대상으로 하는 모든 코드는 .NET Core에서 실행할 수 있습니다.  ASP.NET Core 및 UWP(유니버설 Windows 플랫폼)에서 사용하는 런타임입니다.  최신 버전이며, 효율적이고, 서버 및 클라우드 작업을 대규모로 처리하도록 설계되었습니다.

.NET Core에 대한 자세한 내용은 [.NET Core 가이드](../core/index.md)를 참조하세요.

### <a name="net-framework"></a>.NET Framework

.NET Framework는 2002년부터 사용되어 역사적으로 의미있는 .NET 런타임입니다.  기존 .NET 개발자가 항상 사용해 온 것과 동일한 .NET Framework입니다.  이를 통해 .NET 표준 라이브러리를 구현합니다. 즉 .NET 표준을 대상으로 하는 모든 코드는 .NET Framework에서 실행할 수 있습니다.  Windows Forms 및 WPF를 사용하는 Windows 데스크톱 개발용 API와 같이 Windows 관련 추가 API가 포함되어 있습니다.  .NET Framework는 Windows 데스크톱 응용 프로그램을 구축을 위해 최적화되어 있습니다.

.NET Framework에 대한 자세한 내용은 [.NET Framework 가이드](../framework/index.md)를 참조하세요.

### <a name="mono-for-xamarin"></a>Xamarin용 Mono

Mono는 Xamarin 앱에서 사용하는 런타임으로  .NET 표준 라이브러리를 구현합니다. 즉 .NET 표준을 대상으로 하는 모든 코드는 Xamarin 앱에서 실행할 수 있습니다.  iOS, Android, Xamarin.Forms 및 Xamarin.Mac용 추가 API가 포함되어 있습니다.  iOS 및 Android에서 모바일 응용 프로그램 구축을 위해 최적화되어 있습니다.

Mono에 대한 자세한 내용은 [Mono 설명서](http://www.mono-project.com/docs/)를 참조하세요.

## <a name="net-tooling-and-common-infrastructure"></a>.NET 도구 및 공통 인프라

.NET용 도구는 각 .NET 구현 전체에서 공통으로 사용됩니다.  여기에는 다음과 같은 응용 프로그램이 포함되며 이에 제한되지는 않습니다.

* .NET 언어 및 해당 컴파일러
* JIT 및 가비지 수집기 등의 런타임 구성 요소
* .NET 프로젝트 시스템("csproj", "vbproj" 또는 "fsproj"라고도 함)
* 프로젝트를 빌드하는 데 사용하는 빌드 엔진 MSBuild
* .NET에 대한 Microsoft의 패키지 관리자 NuGet
* .NET 프로젝트를 빌드하는 데 필요한 플랫폼 간 명령줄 인터페이스 .NET CLI
* CAKE 및 FAKE 등의 오픈 소스 빌드 오케스트레이션 도구

여기서 주요한 내용은 앱을 빌드하도록 선택할 .NET의 모든 "버전"에 공통적으로 사용되는 다양한 도구 및 인프라가 있다는 점입니다.

## <a name="next-steps"></a>다음 단계

자세히 알아보려면 다음을 방문하세요.

* [.NET 표준 라이브러리](library.md)
* [.NET Core 가이드](../core/index.md)
* [.NET Framework 가이드](../framework/index.md)
* [C# 가이드](../csharp/index.md)
* [F# 가이드](../fsharp/index.md)
* [VB.NET 가이드](../visual-basic/index.md)

