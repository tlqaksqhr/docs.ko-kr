---
title: "CLR 프로파일러 및 Windows 스토어 앱"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: csharp
applies_to:
- Windows 10
- Windows 8
helpviewer_keywords:
- profiling API
- profiling API [.NET Framework]
- profiling managed code
- profiling managed code [Windows Store Apps]
ms.assetid: 1c8eb2e7-f20a-42f9-a795-71503486a0f5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d884b80ba8ccc42d1b6acc671db408305a095a7d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="clr-profilers-and-windows-store-apps"></a>CLR 프로파일러 및 Windows 스토어 앱
이 항목에서는 쓰기 진단 도구 분석 하는 Windows 스토어 응용 프로그램 내에서 실행 되는 코드를 관리 하는 경우에 대해 생각 하는 데 필요한 사항 설명 합니다.  또한 Windows 스토어 앱에 대해 실행 하면 작업을 계속 하도록 기존 개발 도구를 수정 하는 지침을 제공 합니다.  이 정보를 이해 하는 것이 좋습니다 Windows 데스크톱 응용 프로그램을 올바르게 실행 하는 도구 수정 하는 이제 관심 있는 진단 도구에서이 API를 이미 사용 중인 공용 언어 런타임 프로 파일링 API에 익숙한 경우 Windows 스토어 앱에 대해 올바르게를 실행 합니다.  
  
 이 항목은 다음 섹션으로 구성되어 있습니다.  
  
 [소개](#Intro)  
 [아키텍처 및 용어](#Arch)  
 [Windows RT 장치](#RT)  
[Windows 런타임 Api를 사용합니다.](#Consuming)  
[프로파일러 DLL 로드](#Loading)  
 [시작에 대 한 일반적인 고려 사항 및 로드를 연결 합니다.](#Common)  
 [시작 부하](#Startup)  
 [부하를 연결 합니다.](#Attach)  
[Windows 스토어 응용 프로그램 내에서 실행](#Running)  
 [Windows 스토어 응용 프로그램 Api에 집중](#APIs)  
 [축소 된 권한](#Permissions)  
 [프로세스 간 통신](#Interprocess)  
 [Shutdown 알림이 표시 되지 않습니다](#Shutdown)  
[Windows 런타임 메타 데이터 파일](#Metadata)  
 [관리 되는 및 관리 되지 않는 Winmd](#WMDs)  
 [CLR 모듈 같이 WinMD 파일 표시](#CLRModules)  
 [Winmd에서 메타 데이터 읽기](#Reading)  
 [Winmd에서 메타 데이터를 수정합니다.](#Modifying)  
 [Winmd와 어셈블리 참조 확인](#Resolving)  
[메모리 프로파일러](#Profilers)  
 [ForceGC 관리 되는 스레드를 만듭니다.](#ForceGC)  
 [ConditionalWeakTableReferences](#WeakTable)  
[결론](#Conclusion)  
[리소스](#Resources)  
  
<a name="Intro"></a>   
## <a name="introduction"></a>소개  
 소개 단락 지나서 변경한 경우 다음 익숙한 CLR 프로 파일링 API입니다.  관리 되는 데스크톱 응용 프로그램에 따라 제대로 작동 하는 진단 도구로 이미 작성 합니다.  이제 자세한 내용을 보려면 도구에 관리 되는 Windows 스토어 앱과 함께 작동 하도록 해야 할 일입니다.  아마도이 작업을 간단한 작업 아닌지 가져 왔어 시도 이미 하셨습니다.  실제로, 모든 도구 개발자에 게 명확 하지 않을 수 있는 고려 사항에는 여러 가지가 있습니다.  예:  
  
-   Windows 스토어 앱 심각 하 게 축소 된 권한으로 컨텍스트에서 실행 됩니다.  
  
-   Windows 메타 데이터 파일에는 기존의 관리 되는 모듈에 비해 고유한 특징이 있습니다.  
  
-   Windows 스토어 앱은을 할애 하 여 대화형 작업 중단 되 면 자체를 일시 중단 합니다.  
  
-   프로세스 간 통신 메커니즘 여러 가지 이유로 작동 하지 않을 수 없습니다.  
  
 이 항목에 주의 해야 하는 항목 및 이들을 제대로 처리 하는 방법을 나열 합니다.  
  
 CLR 프로 파일링 API를 처음 접하는 경우이 항목의 끝에 리소스를 더 잘 소개 정보를 찾는으로 건너뜁니다.  
  
 특정 Windows Api 및 사용 방법에 대 한 세부 정보를 제공 하는이 항목의 범위 밖에는 합니다.  이 항목부터 시작 하 고 여기서 참조 된 Windows Api에 대 한 자세한 내용을 보려면 MSDN을 참조 하십시오.  
  
<a name="Arch"></a>   
## <a name="architecture-and-terminology"></a>아키텍처 및 용어  
 일반적으로 진단 도구에는 다음 그림에 표시 된 것 처럼 아키텍처를 있습니다. "프로파일러," 라는 용어를 사용 하 여 있지만 이러한 도구는 많은 일반적인 성능 또는 코드 검사와 같은 영역으로 메모리 프로 파일링을 뛰어넘는 모의 개체 프레임 워크, 시간 이동 디버깅, 응용 프로그램 모니터링, 등에.  간단한 설명을 위해이 항목 프로파일러도 이러한 도구를 모든 계속 됩니다.  
  
 다음과 같은 용어는이 항목 전체에서 사용 됩니다.  
  
 응용 프로그램  
 프로파일러를 분석 하는 응용 프로그램입니다.  일반적으로이 응용 프로그램 개발자는 이제 응용 프로그램 문제를 진단 하기 위해, 프로파일러를 사용 합니다.  일반적으로이 응용 프로그램으로는 Windows 데스크톱 응용 프로그램을 수 있지만이 항목의 검토 하 고 Windows 스토어 앱입니다.  
  
 프로파일러 DLL  
 분석 되 고 응용 프로그램의 프로세스 공간에 로드 하는 구성 요소입니다.  프로파일러 "에이전트" 라고도 함이 구성 요소를 구현 하는 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)[ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)(2, 3, 등) 인터페이스를 만들고 소비는 [ ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)(2, 3, 등) 및 잠재적으로 분석 된 응용 프로그램에 대 한 데이터를 수집 하는 인터페이스의 응용 프로그램의 동작 측면을 수정 합니다.  
  
 프로파일러 UI  
 이것이 프로파일러 사용자와 상호 작용 하는 데스크톱 응용 프로그램입니다.  이 사용자에 게 응용 프로그램 상태를 표시 하 고 분석 된 응용 프로그램의 동작을 제어 하는 방법을 사용자에 게 제공 하는 일을 담당 합니다.  이 구성 요소는 항상 프로 파일링 되 고 응용 프로그램의 프로세스 공간에서 별도 자체 프로세스 공간에서 실행 됩니다.  프로파일러 UI의 "연결 트리거"를 호출 하는 프로세스는 역할도 할 수 있습니다는 [iclrprofiling:: Attachprofiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) 프로파일러 DLL 하지 못한 경우 프로파일러 DLL을 로드 하려면 분석된 응용 프로그램 시키려면 메서드 시작 시 로드 합니다.  
  
> [!IMPORTANT]
>  프로파일러 UI 컨트롤 및 Windows 스토어 앱에서 보고서에 사용 되는 경우에 Windows 데스크톱 응용 프로그램을 유지 해야 합니다.  패키지 하 여 Windows 스토어에서 진단 도구를 제공 하는 작업을 할 수는 않을 것입니다.  도구는 Windows 스토어 앱에서 수행할 수 없는 프로파일러 UI 내 상주 하는 다양 한 작업 하는 작업을 수행 해야 합니다.  
  
 이 설명서에서는 샘플 있다고 가정 합니다.  
  
-   CLR 프로 파일링 API의 요구 사항에 따른 네이티브 DLL 해야 하기 때문에 c + +에서는 프로파일러 DLL 작성 됩니다.  
  
-   프로파일러 UI는 C#으로 작성 됩니다.  이 필요는 없지만 있기 때문에 프로파일러 UI의 프로세스에 대 한 언어에 필요한 요구 간결 하 고 간단한 되는 언어를 선택 하지 않고 이유?  
  
<a name="RT"></a>   
### <a name="windows-rt-devices"></a>Windows RT 장치  
 Windows RT 장치는 매우 잠겨 있습니다.  제 3 자 프로파일러 단순히 로드할 수 없습니다 이러한 장치에 있습니다.  이 문서는 Windows 8 Pc에 중점을 둡니다.  
  
<a name="Consuming"></a>   
## <a name="consuming-windows-runtime-apis"></a>Windows 런타임 Api를 사용합니다.  
 다음 섹션에 설명 된 시나리오의 번호, 프로파일러 UI 데스크톱 응용 프로그램 몇 가지 새로운 Windows 런타임 Api를 사용 해야 합니다.  데스크톱 응용 프로그램에서 사용할 수 있는 Windows 런타임 Api를 이해 하는 설명서를 참조 하려고 할 수 있는지 여부를 해당 명령의 동작은 다른 시기에서 호출 된 데스크톱 응용 프로그램 및 Windows 스토어 앱 및 합니다.  
  
 관리 되는 코드를 프로파일러 UI를 작성 하는 경우 쉽게 이러한 Windows 런타임 Api를 사용 하도록 하기 위해 수행 해야 하는 몇 가지 단계 됩니다.  참조는 [데스크톱 앱 및 Windows 런타임에 관리 되는](http://go.microsoft.com/fwlink/?LinkID=271858) 대 한 자세한 내용은 문서.  
  
<a name="Loading"></a>   
## <a name="loading-the-profiler-dll"></a>프로파일러 DLL 로드  
 이 섹션에서는 프로파일러 UI 프로파일러 DLL을 로드 하려면 Windows 스토어 응용 프로그램을 발생 하는 방법을 설명 합니다.  이 섹션에서 설명 하는 코드 프로파일러 UI 데스크톱 응용 프로그램에 속하고 따라서 데스크톱 응용 프로그램에 안전 하지만 Windows 스토어 앱에 대 한 안전 하지 않은 Windows Api를 사용 하는 것입니다.  
  
 프로파일러 UI 프로파일러 DLL 두 가지 방법으로 응용 프로그램의 프로세스 공간에 로드 될 수 있습니다.  
  
-   환경 변수에 의해 제어 되므로 응용 프로그램 시작 시  
  
-   호출 하 여 시작 된 후 응용 프로그램에 연결 하 여는 [iclrprofiling:: Attachprofiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) 메서드.  
  
 시작 로드 및 Windows 스토어 앱과 올바르게 작동 하도록 프로파일러 DLL의 연결 로드 하면 첫 번째 장애물 중 하나를 가져오는입니다.  두 형태의 로드 몇 가지 특별 한 고려 사항에서 공통, 이러한 시작 하겠습니다.  
  
<a name="Common"></a>   
### <a name="common-considerations-for-startup-and-attach-loads"></a>시작에 대 한 일반적인 고려 사항 및 로드를 연결 합니다.  
 **프로파일러 DLL 서명**  
 Windows에서 프로파일러 DLL을 로드 하려고 하는 경우 프로파일러 DLL가 올바르게 서명 되었는지 확인 합니다.  그렇지 않으면 기본적으로 부하 실패 합니다. 여기에는 두 가지 방법이 있습니다.  
  
-   프로파일러 DLL은 서명 되었는지 확인 합니다.  
  
-   도구를 사용 하기 전에 해당 Windows 8 컴퓨터에서 개발자 라이선스를 설치 해야 한다는 사용자를 알려 줍니다.  이렇게 자동으로 Visual Studio 또는 명령 프롬프트에서 수동으로 합니다.  자세한 내용은 참조 [개발자 라이선스 가져오기](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx)합니다.  
  
 **파일 시스템 권한**  
 Windows 스토어 응용 프로그램에 로드 하 고 존재 하는 파일 시스템 위치에서 프로파일러 DLL을 실행할 수 있는 권한이 있어야 합니다.  기본적으로 Windows 스토어 앱에 대부분의 디렉터리에 그러한 사용 권한은 없는 하 고 프로파일러 DLL 로드 실패 한 시도 다음과 같은 Windows 응용 프로그램 이벤트 로그에 항목을 생성 합니다.  
  
```Output  
NET Runtime version 4.0.30319.17929 - Loading profiler failed during CoCreateInstance.  Profiler CLSID: '{xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}'.  HRESULT: 0x80070005.  Process ID (decimal): 4688.  Message ID: [0x2504].  
```  
  
 일반적으로 제한 된 집합의 디스크 상의 위치에 액세스 하려면 Windows 스토어 앱 에서만 허용 됩니다.  각 Windows 스토어 응용 프로그램을 모든 Windows 스토어 응용 프로그램 액세스가 허용 된 파일 시스템에 응용 프로그램 데이터 폴더를 사용 하는 자체 뿐만 아니라 다른 몇 가지 영역 액세스할 수 있습니다.  모든 Windows 스토어 앱 읽기 및 권한이 있습니다. 기본적으로 실행 되므로 프로파일러 DLL 및 Program Files 또는 Program Files (x86)에서 어딘가에 해당 종속성을 설치 하는 것이 좋습니다.  
  
<a name="Startup"></a>   
### <a name="startup-load"></a>시작 부하  
 일반적으로 데스크톱 앱에서 프로파일러 UI 라는 메시지를 표시 하면 프로파일러 DLL의 시작 부하 필요한 CLR 프로 파일링 API 환경 변수를 포함 하는 환경 블록을 초기화 하 여 (즉, `COR_PROFILER`, `COR_ENABLE_PROFILING`, 및 `COR_PROFILER_PATH`), 및 해당 환경 블록을 사용 하 여 새 프로세스를 다음 만들기  마찬가지 Windows 스토어 앱 용 하지만 메커니즘 다릅니다.  
  
 **관리자 권한으로 실행 안 함**  
 처리 하는 경우 Windows 스토어 응용 프로그램 프로세스 B, A 프로세스 생성 시도의 실행 해야 중간 무결성 수준으로 높은 무결성 수준 (즉, 하지 권한 상승)에 없습니다.  즉, 프로파일러 UI 중간 무결성 수준에서 실행 해야이 없거나 해당 Windows 스토어 앱을 처리 하기 중간 무결성 수준에서 다른 데스크톱 프로세스를 생성 해야 합니다.  
  
 **Windows 스토어 응용 프로그램 프로필 선택**  
 첫째, 프로파일러 사용자에 게는 Windows 스토어 앱 시작을 요청 합니다.  데스크톱 응용 프로그램에 대 한 파일 찾아보기 대화 상자로 표시 됩니다는 아마도 및 사용자를 찾아.exe 파일을 선택 합니다.  하지만 Windows 스토어 앱은 서로 다르며 찾아보기 대화 상자를 사용 하 여은 바람직하지 않습니다.  대신, 사용자에서 선택 하려면 해당 사용자에 대해 설치 된 Windows 스토어 앱의 목록을 표시 하는 것이 좋습니다.  
  
 사용할 수는 [PackageManager 클래스](https://msdn.microsoft.com/library/windows/apps/windows.management.deployment.packagemanager.aspx) 이 목록을 생성 합니다.  `PackageManager`데스크톱 응용 프로그램에 제공 되는 Windows 런타임 클래스 이며은 실제로 *만* 데스크톱 앱에 사용할 수 있습니다.  
  
 C# yses에서 데스크톱 응용 프로그램으로 작성 된 가상의 프로파일러 UI에서 다음 ode 예제는 `PackageManager` Windows 앱의 목록을 생성 하려면:  
  
```csharp  
string currentUserSID = WindowsIdentity.GetCurrent().User.ToString();  
IAppxFactory appxFactory = (IAppxFactory) new AppxFactory();  
PackageManager packageManager = new PackageManager();  
IEnumerable<Package> packages = packageManager.FindPackagesForUser(currentUserSID);  
```  
  
 **사용자 정의 환경 블록 지정**  
 새 COM 인터페이스 [IPackageDebugSettings](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx), 몇 가지 형태의 진단을 쉽게 수행할 수 있도록 Windows 스토어 앱의 실행 동작을 사용자 지정할 수 있습니다.  해당 메서드 중 하나 [EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=vs.85\).aspx)를 시작 하는 Windows 스토어 앱에는 환경 블록을 전달할 수 있도록 자동 프로세스 일시 중단 해제와 같은 기타 유용한 효과 함께 합니다.  환경 변수를 지정 해야 하기 때문에 환경 블록은 중요 한 (`COR_PROFILER`, `COR_ENABLE_PROFILING`, 및 `COR_PROFILER_PATH)`) 프로파일러 DLL을 로드 하려면 CLR에서 사용 합니다.  
  
 다음 코드 조각을 참조 하십시오.  
  
```csharp  
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();  
pkgDebugSettings.EnableDebugging(packgeFullName, debuggerCommandLine,   
                                                                 (IntPtr)fixedEnvironmentPzz);  
```  
  
 몇 가지를 올바르게 해야 하는 항목이 있습니다.  
  
-   `packageFullName`패키지를 반복 하 고를 클릭 한 다음 확인할 수 있습니다 `package.Id.FullName`합니다.  
  
-   `debuggerCommandLine`좀 더 흥미로운 부분입니다.  사용자 정의 환경 블록을 Windows 스토어 응용 프로그램에 전달 하기 위해 단순화 한 것을 직접 더미 디버거를 작성 해야 합니다.  Windows 스 폰을 Windows 스토어 응용 프로그램 일시 중단 하 고이 예제에서와 같은 명령줄 디버거를 시작 하 여 디버거를 연결 합니다.  
  
    ```Output  
    MyDummyDebugger.exe -p 1336 -tid 1424  
    ```  
  
     여기서 `-p 1336` Windows 스토어 응용 프로그램에 프로세스 ID 1336 의미 및 `-tid 1424` 스레드 ID 1424은 일시 중단 된 스레드를 의미 합니다.  더미 디버거 ThreadID 명령줄에서 구문 분석 하 고 해당 스레드를 다시 시작 하 고 종료 합니다.  
  
     다음은 몇 가지 예는이 작업을 수행 하는 c + + 코드 (있어야 오류 검사를 추가 하려면!).  
  
    ```cpp  
    int wmain(int argc, wchar_t* argv[])  
    {      
        // …  
        // Parse command line here  
        // …  
  
        HANDLE hThread = OpenThread(THREAD_SUSPEND_RESUME,   
                                                                  FALSE /* bInheritHandle */, nThreadID);  
        ResumeThread(hThread);  
        CloseHandle(hThread);  
        return 0;  
    }  
    ```  
  
     진단 도구 설치의 일부로이 더미 디버거를 배포 하 고 경로에서이 디버거를 지정 합니다 해야는 `debuggerCommandLine` 매개 변수입니다.  
  
 **Windows 스토어 응용 프로그램을 시작합니다.**  
 Windows 스토어 응용 프로그램을 실행 하는 순간 마지막으로 도착 합니다. 이 작업을 직접 수행 도중 이미 이미, 알 수 있습니다는 [CreateProcess](https://msdn.microsoft.com/library/windows/desktop/ms682425\(v=vs.85\).aspx) 는 Windows 스토어 응용 프로그램 프로세스를 만드는 방법이 되지 않습니다.  사용 해야 하는 대신,는 [IApplicationActivationManager::ActivateApplication](https://msdn.microsoft.com/library/windows/desktop/Hh706903\(v=vs.85\).aspx) 메서드.  이렇게 하려면 실행 하는 Windows 스토어 앱의 앱 사용자 모델 ID를 가져오는 해야 합니다.  및는 매니페스트를 통해 약간 조사를 수행 해야 합니다.  
  
 패키지를 반복 하는 동안 ("선택 정도 Windows 스토어 앱을 프로필"에서 참조는 [시작 부하](#Startup) 이전 섹션), 현재 패키지의 매니페스트에 포함 된 응용 프로그램 집합을 잡고 합니다:  
  
```csharp  
string manifestPath = package.InstalledLocation.Path + "\\AppxManifest.xml";  
  
AppxPackaging.IStream manifestStream;  
SHCreateStreamOnFileEx(  
                    manifestPath,  
                    0x00000040,     // STGM_READ | STGM_SHARE_DENY_NONE  
                    0,              // file creation attributes  
                    false,          // fCreate  
                    null,           // reserved  
                    out manifestStream);  
  
IAppxManifestReader manifestReader = appxFactory.CreateManifestReader(manifestStream);  
  
IAppxManifestApplicationsEnumerator appsEnum = manifestReader.GetApplications();  
```  
  
 예, 한 개의 패키지는 여러 응용 프로그램을 가질 수 있습니다 및 각 응용 프로그램은 자체 응용 프로그램 사용자 모델 id입니다.  따라서 응용 프로그램 프로필을 사용자에 게 문의 하 고 해당 특정 응용 프로그램에서 응용 프로그램 사용자 모델 ID를 선택 해야:  
  
```csharp  
while (appsEnum.GetHasCurrent() != 0)  
{  
    IAppxManifestApplication app = appsEnum.GetCurrent();  
    string appUserModelId = app.GetAppUserModelId();  
…  
```  
  
 마지막으로, 해야 Windows 스토어 응용 프로그램을 실행 하는 데 필요한 사항:  
  
```csharp  
IApplicationActivationManager appActivationMgr = new ApplicationActivationManager();  
appActivationMgr.ActivateApplication(appUserModelId, appArgs, ACTIVATEOPTIONS.AO_NONE, out pid);  
```  
  
 **DisableDebugging를 호출 하 여**  
 호출할 때 [IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx)를 호출 하 여 사용자가 직접 후 정리 되는 프라미스를 변경한는 [IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx) 메서드를 수행 해야 프로 파일링 세션 끝났습니다.  
  
<a name="Attach"></a>   
### <a name="attach-load"></a>부하를 연결 합니다.  
 사용 하 여 프로파일러 UI를 이미 실행을 시작 하는 응용 프로그램에의 프로파일러 DLL을 연결 하려는 경우 [iclrprofiling:: Attachprofiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md)합니다.  Windows 스토어 앱도 마찬가지입니다.  하지만 앞에서 나열 된 일반적인 고려 사항 외에도 다음 사항을 확인는 대상 Windows 스토어 응용 프로그램 일시 중단 되지 않습니다.  
  
 **EnableDebugging**  
 시작 부하와 마찬가지로 호출는 [IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx) 메서드.  다른 기능 중 하나가 필요 하지만 환경 블록을 전달 하기 위해 필요 하지 않습니다: 일시 중단 자동 프로세스를 사용 하지 않도록 설정 합니다.  그렇지 않으면 프로파일러 UI를 호출할 때 [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md), 대상 Windows 스토어 응용 프로그램 일시 중단 될 수 있습니다.  실제로 사용자가 이제 프로파일러 UI를 상호 작용 하 고 Windows 스토어 앱에서 사용자의 화면 중 상태인 경우 가능성이입니다.  하는 경우 Windows 스토어 앱이 일시 중단 수는 없습니다 응답 하 고 프로파일러 DLL을 연결 하는 CLR 클라이언트로 보내는 알립니다.  
  
 다음과 같은 코드 하려고 합니다.  
  
```csharp  
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();  
pkgDebugSettings.EnableDebugging(packgeFullName, null /* debuggerCommandLine */,   
                                                                 IntPtr.Zero /* environment */);  
```  
  
 이것은 디버거 명령줄 이나 환경 블록을 지정 하지 않으면 점을 제외 하 고 시작 부하 사례에 대 한 확인은 같은 호출 합니다.  
  
 **DisableDebugging**  
 호출을 반드시 지정 늘 그렇듯이 [IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx) 프로 파일링 세션이 완료 되 면 합니다.  
  
<a name="Running"></a>   
## <a name="running-inside-the-windows-store-app"></a>Windows 스토어 응용 프로그램 내에서 실행  
 따라서 Windows 저장소 앱 프로파일러 DLL를 마지막으로 로드 했습니다.  축소 된 프로파일러 DLL Windows 스토어 앱에 필요한 다른 규칙에서 재생 하는 방법 뿐만 아니라 해야, 이제 권한 허용 되는 Api 및를 실행 하는 방법을 포함 하 여 합니다.  
  
<a name="APIs"></a>   
### <a name="stick-to-the-windows-store-app-apis"></a>Windows 스토어 응용 프로그램 Api에 집중  
 Windows API를 탐색할 때 데스크톱 앱, Windows 스토어 앱 중 하나 또는 둘 다에 적용할 수 있는 것으로 모든 API는 문서화 알 수 있습니다.  예를 들어는 **요구 사항** 에 대 한 설명서의 섹션은 [InitializeCriticalSectionAndSpinCount](https://msdn.microsoft.com/library/windows/desktop/ms683476\(v=vs.85\).aspx) 함수 함수 데스크톱 응용 프로그램에 적용 되도록 나타냅니다. 반면,는 [InitializeCriticalSectionEx](https://msdn.microsoft.com/library/windows/desktop/ms683477\(v=vs.85\).aspx) 함수는 데스크톱 앱 및 Windows 스토어 앱을 모두 사용할 수 있습니다.  
  
 프로파일러 DLL을 개발할 때는 Windows 스토어 앱의 경우 처럼 처리 하 고만 Windows 스토어 응용 프로그램에 사용 가능으로 설명 하는 Api를 사용 합니다.  종속성 분석 (실행할 수는 예를 들어 `link /dump /imports` 감사 프로파일러 DLL에 대 한), 한 다음 확인 하는 종속성 확인 된 고 하지는 문서를 검색 합니다.  대부분의 경우 프로그램 위반 단순히 안전한 설명 하는 API의 최신 형식으로 대체 하 여 수정 될 수 있습니다 (예를 들어 교체 [InitializeCriticalSectionAndSpinCount](https://msdn.microsoft.com/library/windows/desktop/ms683476\(v=vs.85\).aspx) 와 [ InitializeCriticalSectionEx](https://msdn.microsoft.com/library/windows/desktop/ms683477\(v=vs.85\).aspx)).  
  
 프로파일러 DLL만, 데스크톱 앱에 적용 되는 몇 가지 Api를 호출 하 고 프로파일러 DLL이 Windows 스토어 앱의 내 로드 될 때에 작동 것 아직 알 수 있습니다.  Windows 스토어 응용 프로그램 프로세스에 로드 될 때 프로파일러 DLL에서 Windows 스토어 앱에 사용할 설명 하지는 API를 사용 하는 것은 위험할 임을 고려해 야 합니다.  
  
-   이러한 Api는 Windows 스토어 앱에서 실행 하는 고유한 컨텍스트 내에서 호출할 때 실행 되도록 보장 되지 않습니다.  
  
-   서로 다른 Windows 스토어 응용 프로그램 프로세스 내에서 호출할 때 이러한 Api 일관 되 게 작동 하지 않을 수 있습니다.  
  
-   이러한 Api의 Windows에서 현재 버전에서 Windows 스토어 응용 프로그램에서 제대로 작동 하는 것 처럼 보일 수 되지만 바꾸어 벗어나지 또는 이후 버전의 Windows에서 비활성화할 수 있습니다.  
  
 모든 위반을 수정 하 고 위험을 방지 하려면이 최선이입니다.  
  
 반드시 특정 API에 반드시을 Windows 스토어 앱에 적합 한 대체를 찾을 수 없습니다 것을 알 수 있습니다.  이러한 경우에 최소한:  
  
-   테스트, 테스트, 주거 daylights 해당 API의 사용량 부족 합니다.  
  
-   API 수 갑자기 중단 되거나 메서드를 호출 하면 사라집니다 이해에서 Windows 스토어 내의 앱 향후 버전의 Windows 합니다.  이 않습니다로 간주 호환성 문제는 microsoft에서 하 고 그 사용을 지 원하는 우선 순위 되지 않습니다.  
  
<a name="Permissions"></a>   
### <a name="reduced-permissions"></a>축소 된 권한  
 Windows 스토어 앱 사용 권한 데스크톱 응용 프로그램에서 다른 모든 방법을 표시 하려면이 항목의 범위를 벗어납니다.  하지만 확실히 동작은 됩니다 (데스크톱 응용 프로그램을 비교 하 여 Windows 스토어 응용 프로그램으로 로드) 하는 경우 프로파일러 DLL 모든 리소스에 액세스 하려고 할 때마다 달라질 수 있습니다.  파일 시스템은 가장 일반적인 예입니다.  있지만 디스크에 지정된 된 Windows 스토어 앱에 액세스할 수 있는 몇 가지 배치 (참조 [파일 액세스 및 사용 권한 (Windows 런타임 앱](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)), 프로파일러 DLL의 동일한 제한 됩니다.  코드를 철저히 테스트 합니다.  
  
<a name="Interprocess"></a>   
### <a name="inter-process-communication"></a>프로세스 간 통신  
 프로파일러 DLL (Windows 스토어 응용 프로그램 프로세스 공간에 로드)이 문서의 시작 부분에서 다이어그램에 나와 있는 것 처럼 사용자 고유의 사용자 지정 간 프로세스를 통해 프로파일러 UI (데스크톱 응용 프로그램을 별도 프로세스 공간에서 실행)와 통신 해야 합니다. (IPC) 통신 채널입니다.  프로파일러 UI의 동작을 수정 하는 프로파일러 DLL에 신호를 보냅니다 및 프로파일러 DLL 후 처리 하 고 프로파일러 사용자에 게 표시에 대 한 프로파일러 UI를 다시 분석 된 Windows 스토어 앱에서 데이터를 보냅니다.  
  
 대부분의 프로파일러 이런 방식이으로 작동 하지만 Windows 스토어 앱에 프로파일러 DLL이 로드 될 때 좀 더 제한적을 IPC 메커니즘 선택.  예를 들어 명명 된 파이프의 일부분이 아닌 SDK, Windows 스토어 앱을 사용할 수 없습니다.  
  
 하지만 파일에 여전히 보다 제한적인된 방식으로 만드는 물론, 합니다.  이벤트를 사용할 수 있습니다.  
  
 **파일을 통해 통신합니다.**  
 대부분의 데이터가 가능성이 프로파일러 DLL과 프로파일러 UI 간에 파일을 통해 전달 합니다.  핵심은 프로파일러 DLL (Windows 스토어 앱의 경우)와 프로파일러 UI 읽기 파일 위치 및 쓰기 액세스를 선택 하는 것입니다.  예를 들어 임시 폴더 경로 프로그램 프로파일러 DLL 및 프로파일러 UI에서 액세스할 수 있는 위치 있지만 없는 다른 Windows 스토어 앱 패키지 (따라서 다른 Windows 스토어 응용 프로그램 패키지에서 로그 정보 보호)에 액세스할 수 있습니다.  
  
 프로파일러 UI 및 프로파일러 DLL 둘 다 확인할 수 없습니다이 경로 독립적으로.  현재 사용자에 대해 설치 된 모든 패키지를 반복 하는 경우 프로파일러 UI를 (이전 코드 예제 참조)에 대 한 액세스를 가져옵니다는 `PackageId` 이 코드 조각에서와 비슷한 코드와 임시 폴더 경로 파생 될 수 있는 클래스입니다.  (항상 오류 검사는 생략 됨 간결 합니다.)  
  
```csharp  
// C# code for the Profiler UI.  
ApplicationData appData =  
    ApplicationDataManager.CreateForPackageFamily(  
        packageId.FamilyName);  
  
tempDir = appData.TemporaryFolder.Path;  
```  
  
 프로파일러 DLL 수 기본적으로 동일한 작업을 수행 하는 한편, 수 있는 경우에 더 간단 하 게 액세스할는 [ApplicationData](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.aspx) 클래스를 사용 하 여는 [ApplicationData.Current](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.current.aspx) 속성입니다.  
  
 **이벤트를 통해 통신**  
 프로파일러 UI 및 프로파일러 DLL 간의 간단한 신호 의미 체계를 사용 하도록 하려는 경우 Windows 스토어 응용 프로그램과 데스크톱 응용 프로그램 이벤트를 사용할 수 있습니다.  
  
 프로파일러 DLL에서 호출 하면는 [CreateEventEx](https://msdn.microsoft.com/library/windows/desktop/ms682400\(v=vs.85\).aspx) 이름은 원하는 대로와 명명된 된 이벤트를 만들 함수입니다.  예:  
  
```cpp  
// Profiler DLL in Windows Store app (C++).  
CreateEventEx(   
    NULL,  // Not inherited  
    "MyNamedEvent"  
    CREATE_EVENT_MANUAL_RESET, /* explicit ResetEvent() required; leave initial state unsignaled */  
    EVENT_ALL_ACCESS);  
```  
  
 프로파일러 UI는 다음 Windows 스토어 응용 프로그램의 네임 스페이스 아래의 해당 명명 된 이벤트를 찾으려면 필요 합니다.  예를 들어 프로파일러 UI를 호출할 수 [CreateEventEx](https://msdn.microsoft.com/library/windows/desktop/ms682400\(v=vs.85\).aspx), 이벤트 이름으로 지정  
  
 `AppContainerNamedObjects\<acSid>\MyNamedEvent`  
  
 `<acSid>`Windows 스토어 앱의 AppContainer SID입니다.  이 항목의 이전 단원에는 현재 사용자에 대해 설치 된 패키지에 대해 반복 하는 방법을 배웠습니다.  해당 샘플 코드에서의 패키지 Id를 가져올 수 있습니다.  패키지 Id를 가져올 수 있습니다는 `<acSid>` 다음과 유사한 코드:  
  
```csharp  
IntPtr acPSID;  
DeriveAppContainerSidFromAppContainerName(packageId.FamilyName, out acPSID);  
  
string acSid;  
ConvertSidToStringSid(acPSID, out acSid);  
  
string acDir;  
GetAppContainerFolderPath(acSid, out acDir);  
```  
  
<a name="Shutdown"></a>   
### <a name="no-shutdown-notifications"></a>Shutdown 알림이 표시 되지 않습니다  
 Windows 스토어 응용 프로그램 내부에서 실행할 경우 프로파일러 DLL 중 하나에 의존 하지 않아야 [icorprofilercallback:: Shutdown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md) 또는 심지어 [DllMain](https://msdn.microsoft.com/library/windows/desktop/ms682583\(v=vs.85\).aspx) (으로 `DLL_PROCESS_DETACH`) 프로파일러 DLL에 알리기 위해 호출 되 고 Windows 스토어 앱이 종료 됩니다.  사실, 될 때 호출 되지 않습니다.  지금까지 많은 프로파일러 Dll 이러한 알림을로 사용 편리한 위치 하 고 파일을 닫고, 등 프로파일러 UI에 다시 알림을 보내려면 디스크 캐시를 플러시합니다.  그러나 프로파일러 DLL 이제 약간 다르게 구성 해야 합니다.  
  
 프로파일러 DLL 되는 것 만큼 로깅 정보 이어야 합니다.  성능상의 이유로에 대 한 정보를 메모리에에서 일괄 처리 및 일괄 처리 크기가 특정 임계값을 지 나 확장 되면서 디스크에 플러시하는 것이 좋습니다.  하지만 아직 디스크에 플러시된 모든 정보가 손실 될 수 있음을 가정 합니다.  이 임계값을 신중 하 게 선택 해야 하 고 프로파일러 UI를 프로파일러 DLL에서 작성 하는 완전 하지 않은 정보를 다루는 확정 해야 함을 의미 합니다.  
  
<a name="Metadata"></a>   
## <a name="windows-runtime-metadata-files"></a>Windows 런타임 메타 데이터 파일  
 이 문서에 정보를 확인할 범위 외부에서 Windows 런타임 메타 데이터 (WinMD) 파일.    이 섹션 프로파일러 DLL을 분석 하는 Windows 스토어 앱에서 WinMD 파일을 로드할 때 CLR 프로 파일링 API가 반응 하는 방법으로 제한 됩니다.  
  
<a name="WMDs"></a>   
### <a name="managed-and-non-managed-winmds"></a>관리 되는 및 관리 되지 않는 Winmd  
 개발자는 Visual Studio를 사용 하 여 새 Windows 런타임 구성 요소 프로젝트를 만들를 하는 경우 해당 프로젝트의 빌드를 개발자가 작성 메타 데이터 (클래스, 인터페이스 등의 형식 설명)를 설명 하는 WinMD 파일을 생성 합니다.  이 프로젝트는 C# 또는 VB로 작성 된 관리 되는 언어 프로젝트를 면 WinMD 파일의 해당 형식 (개발자의 소스 코드에서 컴파일된 모든 IL을 포함 하는 의미) 구현에 포함 합니다.  이러한 파일을 관리 되는 WinMD 파일 이라고 합니다.  Windows 런타임 메타 데이터와 기본 구현이 포함 한다는 점에서 흥미로운 일입니다.  
  
 반면, 개발자를 c + + Windows 런타임 구성 요소 프로젝트를 만드는 경우 해당 프로젝트의 빌드 메타 데이터만 포함 하는 WinMD 파일을 생성 하 고 구현은 별도 네이티브 DLL로 컴파일됩니다.  마찬가지로, Windows SDK에서 제공 되는 WinMD 파일 Windows의 일부로 제공 되는 별도 네이티브 Dll로 컴파일 구현을 메타 데이터만 포함 합니다.  
  
 아래 정보는 모두 관리 되는 Winmd 메타 데이터 및 구현, 포함 된 그리고 메타 데이터만 포함 하는 관리 되지 않는 Winmd에 적용 됩니다.  
  
<a name="CLRModules"></a>   
### <a name="winmd-files-look-like-clr-modules"></a>CLR 모듈 같이 WinMD 파일 표시  
 CLR은 관련 관련해 서 모든 WinMD 파일은 모듈입니다.  CLR 프로 파일링 API는 따라서 프로파일러 DLL WinMD 파일을 로드 하 고, 해당 ModuleIDs, 다른 관리 되는 모듈의 경우와 같은 방식으로 지시 합니다.  
  
 프로파일러 DLL 호출 하 여 다른 모듈에서 WinMD 파일을 구분할 수는 [icorprofilerinfo3:: Getmoduleinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) 메서드 및 검사는 `pdwModuleFlags` 출력에 대 한 매개 변수는 [COR_PRF_MODULE_WINDOWS_ 런타임](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) 플래그입니다.  (설정은 경우에 ModuleID winmd 인 것을 나타냅니다.)  
  
<a name="Reading"></a>   
### <a name="reading-metadata-from-winmds"></a>Winmd에서 메타 데이터 읽기  
 일반 모듈과 마찬가지로 WinMD 파일을 통해 읽을 수 있는 메타 데이터가 포함 된 [메타 데이터 Api](../../../../docs/framework/unmanaged-api/metadata/index.md)합니다.  그러나 CLR 개발자에 게 관리 되는 코드에서 프로그래밍 하 고 WinMD 파일을 사용 하 여 더 자연 스러운 프로그래밍 환경을 가질 수 있습니다 WinMD 파일을 읽을 때에 Windows 런타임 형식의.NET Framework 형식에 매핑합니다.  이러한 매핑 중 몇 가지 예를 참조 하십시오. [.NET Framework 지원에 대 한 Windows 스토어 앱 및 Windows Runtime](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)합니다.  
  
 따라서 보기는 프로파일러가 메타 데이터 Api를 사용 하는 경우: 원시 Windows 런타임 보기 또는 매핑된.NET Framework 보기?  대답:가 있습니다.  
  
 호출 하는 경우는 [icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) 메서드 메타 데이터 인터페이스와 같은 얻으려고 WinMD [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)를 설정 하도록 선택할 수 있습니다 [ofNoTransform](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)에 `dwOpenFlags` 이 매핑을 사용 하지 않으려면 매개 변수입니다.  그렇지 않은 경우 기본적으로 매핑이 활성화 합니다.  일반적으로 프로파일러가 친숙 하 고 프로파일러 사용자에 게 자연 프로파일러 DLL가 WinMD 메타 데이터 (예: 형식의 이름)에서 가져오는 문자열 보이는지 있도록 매핑을 사용 하 고, 유지 됩니다.  
  
<a name="Modifying"></a>   
### <a name="modifying-metadata-from-winmds"></a>Winmd에서 메타 데이터를 수정합니다.  
 Winmd에 대 한 메타 데이터를 수정 하는 것은 지원 되지 않습니다.  호출 하는 경우는 [icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) 메서드 WinMD에 대 한 파일을 지정 [ofWrite](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) 에 `dwOpenFlags` 매개 변수와 같은 쓰기 가능한 메타 데이터 인터페이스에 대 한 요청 또는 [ IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md), [GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) 실패 합니다.  이 메타 데이터 (예: Assemblyref 또는 새 메서드 추가)의 계측을 지원 하기 위해 수정 해야 할 IL 다시 쓰기 프로파일러에 특히 중요 합니다.  에 대 한 확인 해야 하므로 [COR_PRF_MODULE_WINDOWS_RUNTIME](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) (이전 섹션에서 설명)를 먼저 및가 이러한 모듈에 쓰기 가능한 메타 데이터 인터페이스에 대 한 확인이 포함 되지 않습니다.  
  
<a name="Resolving"></a>   
### <a name="resolving-assembly-references-with-winmds"></a>Winmd와 어셈블리 참조 확인  
 여러 프로파일러의 계측 또는 형식 검사를 지원 하기 위해 수동으로 메타 데이터 참조를 확인 해야 합니다.  이러한 프로파일러는 보다 표준 어셈블리 참조를 완전히 다른 방식으로 이러한 참조는 확인 하기 때문에 CLR에서 Winmd를 가리키는 어셈블리 참조를 해결 하는 방법을 알아야 합니다.  
  
<a name="Profilers"></a>   
## <a name="memory-profilers"></a>메모리 프로파일러  
 가비지 수집기 및 관리 되는 힙에서 Windows 스토어 앱 및 데스크톱 응용 프로그램에서 다른있지 않습니다.  그러나 프로파일러 작성자에 주의 해야 하는 몇 가지 미묘한 차이가 있습니다.  
  
<a name="ForceGC"></a>   
### <a name="forcegc-creates-a-managed-thread"></a>ForceGC 관리 되는 스레드를 만듭니다.  
 메모리 프로 파일링을 수행할 때 프로파일러 DLL에서 호출 하는 별도 스레드를 일반적으로 만듭니다는 [ForceGC 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) 메서드.  새로운 것입니다.  하지만 놀라운 것을 Windows 스토어 응용 프로그램 내에서 가비지 컬렉션을 수행 하는 작업 스레드를 관리 되는 스레드를 변형할 수 있는지 (예를 들어 프로 파일링 API ThreadID 만들어짐 해당 스레드에 대 한).  
  
 이 작업의 결과 이해 하려면 CLR 프로 파일링 API에 정의 된 대로 동기 및 비동기 호출 간의 차이점을 이해 해야 합니다. Note이 Windows 스토어 앱의 비동기 호출의 개념와에서 매우 다릅니다.  블로그 게시물을 참조 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE 있는 이유](https://blogs.msdn.microsoft.com/davbr/2008/12/23/why-we-have-corprof_e_unsupported_call_sequence/) 자세한 정보에 대 한 합니다.  
  
 관련 된 중요 한 점은 프로파일러에서 만든 스레드에 대 한 호출이 항상 간주 하 동기, 이러한 호출이 프로파일러 DLL의 중 하나의 구현 외부에서 수행 되는 경우에 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 메서드.  이것이 사용 하는 적어도 합니다.  CLR에 관리 되는 스레드를 호출 하 여 때문에 프로파일러 스레드를 켰가 [ForceGC 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md), 스레드가 프로파일러 스레드 간주 더 이상 않습니다.  이와 같이 CLR 적용으로 해당 스레드에 대 한 동기 한정 기능에 대 한 더 엄격한 정의-즉 호출에서 발생 해야 하는 프로파일러 DLL의 중 하나에서 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 메서드를 동기식으로 한정 합니다.  
  
 그 실제로?  대부분 [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) 메서드를 동기적으로 호출 하려면 안전만 하 고 그렇지 않은 경우 즉시 실패 합니다.  따라서 프로파일러 DLL을 다시 사용 하는 경우 프로그램 [ForceGC 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) 일반적으로 프로파일러에서 생성 된 스레드의에 대 한 다른 호출에 대 한 스레드 (예를 들어 [RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md), [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md), 또는 [RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md))에 문제가 있는 것입니다.  와 같은 안전한 비동기 함수도 [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) 는 관리 되는 스레드에서 호출 될 때 특별 한 규칙이 있습니다. (블로그 게시물을 참조 [프로파일러 스택 워크: 기본 사항 이상](https://blogs.msdn.microsoft.com/davbr/2005/10/06/profiler-stack-walking-basics-and-beyond/) 자세한 정보에 대 한 합니다.)  
  
 따라서 권장 하는 모든 스레드에서 호출할 프로파일러 DLL을 만듭니다 [ForceGC 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) 사용할지 *만* Gc 트리거 한 GC 콜백에 다음 응답 목적으로 합니다.  스택 샘플링 또는 분리 등의 다른 작업을 수행 하는 프로 파일링 API를 호출 하지 않습니다.  
  
<a name="WeakTable"></a>   
### <a name="conditionalweaktablereferences"></a>ConditionalWeakTableReferences  
 새 GC 콜백을.NET Framework 4.5 부터는 [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md), 프로파일러에 대 한 정보를 더 완료 제공 하는 *종속 핸들*합니다. 이러한 핸들은 효과적으로 GC 수명 관리를 수행할 대상 개체에는 원본 개체에서 참조를 추가 합니다.  종속 핸들은 새로 만들었거나, nothing 및 관리 코드에서 프로그래밍 하는 개발자가 자신의 종속 핸들을 사용 하 여 만들 수 있게 되었습니다는 <xref:System.Runtime.CompilerServices.ConditionalWeakTable%602?displayProperty=nameWithType> Windows 8 및.NET Framework 4.5 하기 전에 클래스입니다.  
  
 그러나 관리 되는 Windows 스토어 XAML 앱 확인 종속 핸들을 많이 사용 합니다.  특히 CLR 하는 데 사용의 원활한 관리 되는 개체와 관리 되지 않는 Windows 런타임 개체 참조 주기를 관리 합니다.  이 보다 더 중요 한 이제 힙 그래프의 가장자리의 나머지 부분과 함께 시각화할 수 있도록 이러한 종속 핸들 알아보기 위해 메모리 프로파일러에 대 한 적이 임을 의미 합니다.  프로파일러 DLL을 사용할지 [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md), [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), 및 [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) 힙 그래프의 한 전체 뷰를 형성 하 .  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>결론  
 Windows 스토어 응용 프로그램 내에서 실행 되는 관리 되는 코드를 분석 하는 CLR 프로 파일링 API를 사용 하는 것이 불가능 합니다.  실제로 개발 하는 기존 프로파일러는 가져와 Windows 스토어 앱을 대상 수 있도록 몇 가지 특정 내용을 변경할 수 있습니다.   프로파일러 UI 디버깅 모드에서 Windows 스토어 앱을 활성화 하기 위한 새 Api를 사용 해야 합니다.  프로파일러 DLL만 해당 Api를 사용 Windows 스토어 앱에 적용할 수 있는지 확인 합니다.  Windows 스토어 응용 프로그램 API 제한 사항에 주 및 제한 된 권한 Windows 스토어 앱에 대 한 위치에 대 한 인식을 높이 프로파일러 DLL 및 프로파일러 UI 사이의 통신 메커니즘을 작성 되어야 합니다.  프로파일러 DLL이 CLR Winmd를 처리 하는 방법을 알고 있어야 하 고 가비지 수집기 동작 하는 방식과 관련 하 여 관리 되는 스레드입니다.  
  
<a name="Resources"></a>   
## <a name="resources"></a>리소스  
 **공용 언어 런타임**  
 -   [CLR 프로 파일링 API 참조](../../../../docs/framework/unmanaged-api/profiling/index.md)  
  
-   [CLR 메타 데이터 API 참조](../../../../docs/framework/unmanaged-api/metadata/index.md)  
  
 **Windows 런타임와 CLR의 상호 작용**  
 [Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)  
  
 **Windows 스토어 앱**  
 -   [파일 액세스 및 사용 권한 (Windows 런타임 앱](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)  
  
-   [개발자 라이선스 얻기](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx)  
  
-   [IPackageDebugSettings 인터페이스](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx)  
  
## <a name="see-also"></a>참고 항목  
 [프로파일링](../../../../docs/framework/unmanaged-api/profiling/index.md)
