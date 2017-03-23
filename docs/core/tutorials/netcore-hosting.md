---
title: ".NET Core 호스트 | Microsoft 문서"
description: "네이티브 코드에서 .NET Core 런타임 호스트"
keywords: ".NET, .NET Core, 호스트, .NET Core 호스트"
author: mjrousos
ms.author: mikerou
ms.date: 2/3/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 13edec8b-614d-47ed-9e95-ed6d3b94ec0c
translationtype: Human Translation
ms.sourcegitcommit: 0a9d42f59e48a790e83a5a46b1559b613340136a
ms.openlocfilehash: 01b3b0e7a0e2d2a330b10b2f3482ddd1ed3d51bf
ms.lasthandoff: 03/03/2017

---

# <a name="hosting-net-core"></a>.NET Core 호스트

모든 관리 코드와 같이 .NET Core 응용 프로그램은 호스트에서 실행됩니다. 호스트는 런타임(가비지 수집기 및 JIT와 같은 구성 요소 포함)을 시작하고 AppDomain을 만들고 관리 진입점을 호출합니다.

.NET Core 런타임 호스트는 고급 시나리오이며, .NET Core 빌드 프로세스는 .NET Core 응용 프로그램을 실행하는 기본 호스트를 제공하므로 대부분의 경우 .NET Core 개발자는 호스트에 대해 걱정할 필요가 없습니다. 그러나 일부 특수한 경우, 네이티브 프로세스에서 관리 코드를 호출하는 수단으로나 런타임 작동 방식에 대해 더 많은 제어 권한을 얻기 위해 .NET Core 런타임을 명시적으로 호스트한 것이 유용할 수 있습니다.

이 문서에서는 네이티브 코드에서 .NET Core 런타임을 시작하고 초기 응용 프로그램 도메인(@System.AppDomain)을 만들고 관리 코드를 실행하는 데 필요한 단계에 대한 개요를 제공합니다.

## <a name="prerequisites"></a>필수 조건

호스트는 네이티브 응용 프로그램이기 때문에 이 자습서에서는 .NET Core를 호스트하는 C++ 응용 프로그램을 생성을 다룹니다. [Visual Studio](https://www.visualstudio.com/downloads/)에서 제공하는 C++ 개발 환경 같은 C++ 개발 환경이 필요합니다.

또한 호스트를 테스트할 간단한 .NET Core 응용 프로그램이 필요하므로 [.NET Core SDK](https://www.microsoft.com/net/core)를 설치하고 [소규모 .NET Core 테스트 앱](https://github.com/dotnet/docs/blob/master/docs/csharp/getting-started/with-visual-studio.md)(예: 'Hello World' 앱)을 빌드해야 합니다. 새로운 .NET Core 콘솔 프로젝트 템플릿으로 만든 'Hello World' 앱으로 충분합니다.

이 자습서와 해당 [관련 샘플](https://github.com/dotnet/docs/tree/master/samples/core/hosting)에서는 Windows 호스트를 빌드합니다. 그러나 Unix에서 호스트에 대해서는 이 문서의 마지막 부분을 참조하세요.

## <a name="creating-the-host"></a>호스트 만들기

이 문서에 설명된 단계를 보여 주는 샘플 호스트는 [.NET Core 샘플](https://github.com/dotnet/docs/tree/master/samples/core/hosting) 리포지토리에서 사용할 수 있습니다. 샘플의 host.cpp 파일의 주석은 이 자습서에서 번호가 매겨진 단계를 샘플에서 수행되는 위치와 명확하게 연결합니다.

샘플 호스트는 학습 목적으로 사용되므로 오류 검사가 부족하며 효율성보다 가독성을 강조하도록 설계되었습니다. [dotnet/coreclr](https://github.com/dotnet/coreclr/tree/master/src/coreclr/hosts) 리포지토리에서 더 많은 실제 호스트 샘플을 사용할 수 있습니다. 특히 [CoreRun 호스트](https://github.com/dotnet/coreclr/tree/master/src/coreclr/hosts/corerun)는 간단한 샘플을 읽은 후 학습하기 좋은 일반 용도의 호스트입니다.

### <a name="a-note-about-mscoreeh"></a>mscoree.h에 대한 정보
기본 .NET Core 호스팅 인터페이스(`ICLRRuntimeHost2`)는 [MSCOREE.IDL](https://github.com/dotnet/coreclr/blob/master/src/inc/MSCOREE.IDL)에 정의됩니다. 호스트에서 참조해야 할 이 파일의 헤더 버전(mscoree.h)은 [.NET Core 런타임](https://github.com/dotnet/coreclr/)이 빌드될 때 MIDL을 통해 생성됩니다. .NET Core 런타임을 빌드하지 않으려는 경우 mscoree.h는 dotnet/coreclr 리포지토리에 [미리 빌드된 헤더](https://github.com/dotnet/coreclr/tree/master/src/pal/prebuilt/inc)로 제공됩니다. [.NET Core 런타임 빌드에 대한 지침](https://github.com/dotnet/coreclr#building-the-repository)은 GitHub 리포지토리에서 찾을 수 있습니다. 

### <a name="step-1---identify-the-managed-entry-point"></a>1단계 - 관리되는 진입점 식별
필요한 헤더(예: [mscoree.h](https://github.com/dotnet/coreclr/tree/master/src/pal/prebuilt/inc/mscoree.h) 및 stdio.h)를 참조한 후 .NET Core 호스트에서는 가장 먼저 사용할 관리되는 진입점을 찾아야 합니다. 샘플 호스트에서는 `main` 메서드가 실행될 관리되는 이진 파일에 대한 경로로 첫 번째 명령줄 인수를 호스트로 사용하여 관리되는 진입점을 찾습니다.

[!code-cpp[NetCoreHost#1](../../../samples/core/hosting/host.cpp#1)]

### <a name="step-2---find-and-load-coreclrdll"></a>2단계 - CoreCLR.dll 찾기 및 로드
.NET Core 런타임 API는 *CoreCLR.dll*(Windows)에 있습니다. 호스팅 인터페이스(`ICLRRuntimeHost2`)를 가져오려면 *CoreCLR.dll*를 찾고 로드해야 합니다. 호스트에 따라 *CoreCLR.dll*을 찾는 방법에 대한 규칙을 정의합니다. 일부 호스트에서는 잘 알려진 컴퓨터 수준의 위치(예: %programfiles%\dotnet\shared\Microsoft.NETCore.App\1.1.0)에 파일이 있습니다. 다른 호스트에서는 *CoreCLR.dll*이 호스트 자체 또는 호스트되는 앱 옆의 위치에서 로드됩니다. 라이브러리를 찾기 위해 환경 변수를 참조할 수 있습니다.

Linux 또는 Mac에서 핵심 런타임 라이브러리는 각각 *libcoreclr.so* 또는 *libcoreclr.dylib*입니다.

샘플 호스트는 *CoreCLR.dll*에 대해 몇 가지 일반적인 위치를 검색합니다. 위치를 찾으면 `LoadLibrary`(또는 Linux/Mac에서`dlopen`)를 통해 로드되어야 합니다.

[!code-cpp[NetCoreHost#2](../../../samples/core/hosting/host.cpp#2)]

### <a name="step-3---get-an-iclrruntimehost2-instance"></a>3단계 - ICLRRuntimeHost2 인스턴스 가져오기
`ICLRRuntimeHost2` 호스팅 인터페이스는 `GetCLRRuntimeHost`에서 `GetProcAddress`(또는 Linux/Mac에서 `dlsym`)를 호출한 다음 해당 함수를 호출하여 검색됩니다. 

[!code-cpp[NetCoreHost#3](../../../samples/core/hosting/host.cpp#3)]

### <a name="step-4---setting-startup-flags-and-starting-the-runtime"></a>4단계 - 시작 플래그 설정 및 런타임 시작
`ICLRRuntimeHost2`를 사용하여 이제 전체 런타임의 시작 플래그를 지정하고 런타임을 시작할 수 있습니다. 시작 플래그는 사용할 GC(가비지 수집기)(동시 또는 서버), 단일 AppDomain을 사용할지 여러 AppDomain을 사용할지 여부, 사용할 로더 최적화 정책(도메인 중립적인 어셈블리 로드에 대해)을 결정합니다.

[!code-cpp[NetCoreHost#4](../../../samples/core/hosting/host.cpp#4)]

런타임은 `Start` 함수에 대한 호출로 시작됩니다.

```C++
hr = runtimeHost->Start();
```

### <a name="step-5---preparing-appdomain-settings"></a>5단계 - AppDomain 설정 준비
런타임이 시작되면 AppDomain을 설정합니다. .NET AppDomain을 만들 때 지정해야 하는 옵션이 여러 개 있지만 먼저 그러한 옵션을 준비해야 합니다.

AppDomain 플래그는 보안 및 interop와 관련된 AppDomain 동작을 지정합니다. 이전 Silverlight 호스트는 샌드박스 사용자 코드에 이러한 설정을 사용했지만, 최신.NET Core 호스트는 완전 신뢰 상태로 사용자 코드를 실행하고 interop을 사용하도록 설정합니다.

[!code-cpp[NetCoreHost#5](../../../samples/core/hosting/host.cpp#5)]

사용할 AppDomain 플래그를 결정한 후 AppDomain 속성을 정의해야 합니다. 속성은 문자열의 키/값 쌍입니다. 많은 속성은 AppDomain이 어셈블리를 로드하는 방법과 관련됩니다.

일반적인 AppDomain 속성에는 다음이 포함됩니다.

* `TRUSTED_PLATFORM_ASSEMBLIES` AppDomain에서 로드의 우선 순위를 지정하고 완전 신뢰(부분적으로 신뢰할 수 있는 도메인에서도)를 제공해야 하는 어셈블리 경로 목록입니다(Windows에서 ';'으로 구분되고 Unix에서 ':'으로 구분됨). 이 목록에는 'Framework' 어셈블리 및 .NET Framework 시나리오에서 GAC와 비슷한 기타 신뢰할 수 있는 모듈이 포함됩니다. 일부 호스트는 이 목록에서 *coreclr.dll* 옆에 라이브러리를 배치하고, 일부에는 목적에 대해 신뢰할 수 있는 어셈블리를 나열하는 하드 코드된 매니페스트가 있습니다.
* `APP_PATHS` TPA(신뢰할 수 있는 플랫폼 어셈블리) 목록에서 찾을 수 없는 경우 어셈블리에 대해 검색하는 경로 목록입니다. 이러한 경로는 사용자의 어셈블리를 찾을 수 있는 위치입니다. 샌드박스 AppDomain에서 이러한 경로에서 로드된 어셈블리에는 부분 신뢰만 제공됩니다. 일반적인 APP_PATH 경로에는 대상 앱이 로드되는 경로 또는 사용자 자산이 있다고 알려진 기타 위치가 포함됩니다.
*  `APP_NI_PATHS` 이 목록은 네이티브 이미지에 대해 검색되는 경로를 제외하고, APP_PATHS와 아주 비슷합니다.
*  `NATIVE_DLL_SEARCH_DIRECTORIES` 이 속성은 p/invoke를 통해 호출되는 네이티브 DLL을 찾을 때 로더에서 검색해야 하는 경로 목록입니다.
*  `PLATFORM_RESOURCE_ROOTS` 이 목록에는 (문화권별 하위 디렉터리에서) 리소스 위성 어셈블리에 대해 검색하는 경로가 포함됩니다.
*  `AppDomainCompatSwitch` 이 문자열은 명시적 대상 프레임워크 모니커(어셈블리에서 실행할 프레임워크를 나타내는 어셈블리 수준 특성)가 없는 어셈블리에 대해 사용해야 할 호환성 쿼크를 지정합니다. 일반적으로 `"UseLatestBehaviorWhenTFMNotSpecified"`로 설정되어야 하지만 일부 호스트에서는 대신 이전 Silverlight 또는 Windows Phone 호환성 쿼크를 가져올 수도 있습니다.

[간단한 샘플 호스트](https://github.com/dotnet/docs/tree/master/samples/core/hosting)에서는 이러한 속성이 다음과 같이 설정됩니다.

[!code-cpp[NetCoreHost#6](../../../samples/core/hosting/host.cpp#6)]

### <a name="step-6---create-the-appdomain"></a>6단계 - AppDomain 만들기
모든 AppDomain 플래그 및 속성이 준비되면 `ICLRRuntimeHost2::CreateAppDomainWithManager`를 사용하여 AppDomain을 설정할 수 있습니다. 이 함수는 선택적으로 정규화된 어셈블리 이름 및 형식 이름을 가져와서 도메인의 AppDomain 관리자로 사용합니다. AppDomain 관리자는 호스트에서 AppDomain 동작의 일부 측면을 제어하도록 허용할 수 있고, 호스트에서 사용자 코드를 직접 호출하지 않는 경우 관리 코드를 실행하기 위한 진입점을 제공할 수 있습니다.   

[!code-cpp[NetCoreHost#7](../../../samples/core/hosting/host.cpp#7)]

### <a name="step-7---run-managed-code"></a>7단계 - 관리 코드 실행
AppDomain이 실행 중이면 호스트에서 이제 관리 코드를 실행할 수 있습니다. `ICLRRuntimeHost2::ExecuteAssembly`를 사용하여 관리되는 어셈블리의 진입점 메서드를 호출하면 가장 쉽게 관리 코드를 실행할 수 있습니다. 이 함수는 단일 도메인 시나리오에서만 작동합니다.

[!code-cpp[NetCoreHost#8](../../../samples/core/hosting/host.cpp#8)]

`ExecuteAssembly`가 호스트의 요구 사항을 충족하지 않는 경우 `CreateDelegate`를 사용하여 정적 관리 메서드에 대한 함수 포인터를 만듭니다. 이 경우 호스트에서 호출하는 메서드의 시그니처를 알아야 하지만(함수 포인터 형식을 만들기 위해) 호스트는 어셈블리의 진입점이 아닌 코드를 호출할 수 있습니다.

```C++
void *pfnDelegate = NULL;
hr = runtimeHost->CreateDelegate(
  domainId,
  L"HW, Version=1.0.0.0, Culture=neutral",    // Target managed assembly
  L"ConsoleApplication.Program",            // Target managed type
  L"Main",                                    // Target entry point (static method)
  (INT_PTR*)&pfnDelegate);

((MainMethodFp*)pfnDelegate)(NULL);
```

### <a name="step-8---clean-up"></a>8단계 - 정리
마지막으로 호스트는 AppDomain을 언로드하고, 런타임을 중지하고, `ICLRRuntimeHost2` 참조를 릴리스하여 자체 정리해야 합니다.

[!code-cpp[NetCoreHost#9](../../../samples/core/hosting/host.cpp#9)]

## <a name="about-hosting-net-core-on-unix"></a>Unix에서.NET Core 호스트에 대한 정보
.NET Core는 Windows, Linux 및 Mac 운영 체제에서 실행되는 플랫폼 간 제품입니다. 그러나 네이티브 응용 프로그램으로서, 여러 플랫폼의 호스트에는 서로 몇 가지 차이점이 있습니다. 위에서 설명한 `ICLRRuntimeHost2`를 사용하여 런타임을 시작하고 AppDomain을 만들며 관리 코드를 실행하는 프로세스는 지원되는 운영 체제에서 작동되어야 합니다. 그러나 mscoree.h에 정의된 인터페이스는 mscoree가 많은 Win32 가정을 만들기 때문에 Unix 플랫폼에서 사용하기 힘들 수 있습니다.

Unix 플랫폼에서 더 간단하게 호스트하기 위해 [coreclrhost.h](https://github.com/dotnet/coreclr/blob/master/src/coreclr/hosts/inc/coreclrhost.h)에서 더 많은 플랫폼 중립적인 호스팅 API 래퍼 집합을 제공합니다.

coreclrhost.h를 사용(mscoree.h 대신 직접적으로)하는 예는 [UnixCoreRun 호스트](https://github.com/dotnet/coreclr/tree/master/src/coreclr/hosts)에서 확인할 수 있습니다. coreclrhost.h의 API를 사용하여 런타임을 호스트하는 단계는 mscoree.h를 사용할 때의 단계와 비슷합니다.

1. 실행할 관리 코드를 식별합니다(예: 명령줄 매개 변수에서). 
2. CoreCLR 라이브러리를 로드합니다.
    1. `dlopen("./libcoreclr.so", RTLD_NOW | RTLD_LOCAL);` 
3. `dlsym`을 사용하여 CoreCLR의 `coreclr_initialize`, `coreclr_create_delegate`, `coreclr_execute_assembly` 및 `coreclr_shutdown` 함수에 대한 함수 포인터를 가져옵니다.
    1. `coreclr_initialize_ptr coreclr_initialize = (coreclr_initialize_ptr)dlsym(coreclrLib, "coreclr_initialize");`
4. AppDomain 속성(예: TPA 목록)을 설정합니다. 위 mscoree 워크플로의 5단계와 동일합니다.
5. `coreclr_initialize`를 사용하여 런타임을 시작하고 AppDomain을 만듭니다. 그러면 향후 호스팅 호출에 사용되는 `hostHandle` 포인터도 생성됩니다.
    1. 이 함수는 이전 워크플로에서 4단계 및 6단계의 역할을 모두 수행합니다. 
6. `coreclr_execute_assembly` 또는 `coreclr_create_delegate`를 사용하여 관리 코드를 실행합니다. 이러한 함수는 이전 워크플로에서 7단계에 있는 mscoree의 `ExecuteAssembly` 및 `CreateDelegate` 함수와 유사합니다.
7. `coreclr_shutdown`을 사용하여 AppDomain을 언로드하고 런타임을 종료합니다. 

## <a name="conclusion"></a>결론
호스트가 빌드되면 명령줄에서 실행하고 호스트에서 예상하는 인수(예: 실행할 관리 앱)를 전달하여 테스트할 수 있습니다. 실행할 호스트에 대해 .NET Core 앱을 지정할 때 `dotnet build`로 생성된 .dll을 사용하세요. 자체 포함된 응용 프로그램에 대해 `dotnet publish`로 생성된 실행 파일이 실제로 기본 .NET Core 호스트이며(앱이 주 시나리오의 명령줄에서 직접 실행될 수 있음), 사용자 코드는 동일한 이름의 DLL로 컴파일됩니다. 

처음에 작동되지 않으면, 호스트가 예상한 위치에서 *coreclr.dll*을 사용할 수 있고, 필요한 프레임워크 라이브러리가 모두 TPA 목록에 있으며 CoreCLR의 비트 수(32비트 또는 64비트)가 호스트가 빌드된 방식과 일치하는지 다시 확인합니다.

.NET Core 런타임 호스트는 일부 개발자만 필요로 하는 고급 시나리오이지만, 네이티브 프로세스에서 관리 코드를 실행해야 하거나 .NET Core 런타임의 동작에 대해 더 많은 제어권이 필요한 경우 아주 유용할 수 있습니다. .NET Core는 자체를 나란히 실행할 수 있기 때문에 여러 버전의 .NET Core 런타임을 초기화 및 시작하는 호스트를 만들고 동일한 프로세스로 모든 호스트에서 앱을 실행할 수도 있습니다. 
