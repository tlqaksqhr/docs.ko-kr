---
title: "Diagnosing Errors with Managed Debugging Assistants | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EHMDA"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "run-time error debugging"
  - "managed code, run-time debugging"
  - "resource debugging"
  - "registry, MDAs"
  - "common language runtime, debugging"
  - "MDAs (managed debugging assistants)"
  - "configuration files [.NET Framework], debugging runtime events"
  - "messages, managed debugging assistants"
  - "application configuration files, managed debugging assistants"
  - "debugging [.NET Framework], managed debugging assistants"
  - "environment variables, MDAs"
  - "access violation debugging [.NET Framework]"
  - "diagnostics, managed debugging assistants"
  - "unmanaged code, run-time debugging"
  - "default debug output stream"
  - "memory, debugging"
  - "app.config files, managed debugging assistants"
  - "managed debugging assistants (MDAs)"
  - "debugging [.NET Framework], run-time errors"
  - "trapping events"
  - "runtime, error debugging"
  - "disabling MDAs"
  - "output, managed debugging assistants"
  - "errors [.NET Framework], managed debugging assistants"
ms.assetid: 76994ee6-9fa9-4059-b813-26578d24427c
caps.latest.revision: 63
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 63
---
# Diagnosing Errors with Managed Debugging Assistants
MDA\(관리 디버깅 도우미\)는 런타임 상태에 대한 정보를 제공하기 위해 CLR\(공용 언어 런타임\)과 함께 작동하는 디버깅 도우미입니다.  이 도우미는 다른 방법으로는 트래핑할 수 없는 런타임 이벤트에 대한 정보 메시지를 생성합니다.  MDA를 사용하면 관리 코드와 비관리 코드 간에 변환할 때 발생하는 찾기 어려운 응용 프로그램 버그를 구분할 수 있습니다.  Windows 레지스트리에 키를 추가하거나 환경 변수를 설정하여 모든 MDA를 사용하거나 사용하지 않도록 설정할 수 있습니다.  응용 프로그램 구성 설정을 사용하여 특정 MDA를 사용하도록 설정할 수 있습니다.  응용 프로그램의 구성 파일에서 일부 개별 MDA에 대한 추가 구성 설정을 지정할 수 있습니다.  이러한 구성 파일은 런타임이 로드될 때 구문 분석되므로 관리되는 응용 프로그램이 시작되기 전에 MDA를 사용하도록 설정해야 합니다.  이미 시작된 응용 프로그램에 대해서는 MDA를 사용하도록 설정할 수 없습니다.  
  
> [!NOTE]
>  MDA가 사용하도록 설정되면 코드가 디버거에서 실행되지 않을 때도 MDA가 활성 상태입니다.  디버거가 없을 때 MDA 이벤트가 발생하면 이벤트 메시지가 처리되지 않은 예외가 아니더라도 처리되지 않은 예외 대화 상자에 표시됩니다.  이 대화 상자가 표시되지 않도록 하려면 코드가 디버깅 환경에서 실행되지 않는 경우 MDA 사용 설정을 제거하세요.  
  
> [!NOTE]
>  코드가 Visual Studio IDE\(통합 개발 환경\)에서 실행되는 경우 특정 MDA 이벤트에 대해 나타나는 예외 대화 상자가 표시되지 않도록 할 수 있습니다.  이렇게 하려면 **디버그** 메뉴에서 **예외**를 클릭합니다.  \(**디버그** 메뉴에 **예외** 명령이 없는 경우 **도구** 메뉴에서 **사용자 지정**을 클릭하여 추가합니다.\) **예외** 대화 상자에서 **관리 디버깅 도우미** 목록을 확장한 다음 개별 MDA의 **Throw됨** 확인란을 선택 취소합니다.  예를 들어, [contextSwitchDeadlock](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md)에 대한 예외 대화 상자가 표시되지 않도록 하려면 **관리 디버깅 도우미** 목록에서 해당 이름 옆에 있는 **Throw됨** 확인란을 선택 취소합니다.  또한 이 대화 상자를 사용하여 MDA 예외 대화 상자가 표시되도록 할 수 있습니다.  
  
 다음 테이블에서는 .NET Framework와 함께 제공되는 MDA를 보여 줍니다.  
  
|||  
|-|-|  
|[asynchronousThreadAbort](../../../docs/framework/debug-trace-profile/asynchronousthreadabort-mda.md)|[bindingFailure](../../../docs/framework/debug-trace-profile/bindingfailure-mda.md)|  
|[callbackOnCollectedDelegate](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)|[contextSwitchDeadlock](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md)|  
|[dangerousThreadingAPI](../../../docs/framework/debug-trace-profile/dangerousthreadingapi-mda.md)|[dateTimeInvalidLocalFormat](../../../docs/framework/debug-trace-profile/datetimeinvalidlocalformat-mda.md)|  
|[dirtyCastAndCallOnInterface](../../../docs/framework/debug-trace-profile/dirtycastandcalloninterface-mda.md)|[disconnectedContext](../../../docs/framework/debug-trace-profile/disconnectedcontext-mda.md)|  
|[dllMainReturnsFalse](../../../docs/framework/debug-trace-profile/dllmainreturnsfalse-mda.md)|[exceptionSwallowedOnCallFromCom](../../../docs/framework/debug-trace-profile/exceptionswallowedoncallfromcom-mda.md)|  
|[failedQI](../../../docs/framework/debug-trace-profile/failedqi-mda.md)|[fatalExecutionEngineError](../../../docs/framework/debug-trace-profile/fatalexecutionengineerror-mda.md)|  
|[gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)|[gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)|  
|[illegalPrepareConstrainedRegion](../../../docs/framework/debug-trace-profile/illegalprepareconstrainedregion-mda.md)|[invalidApartmentStateChange](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md)|  
|[invalidCERCall](../../../docs/framework/debug-trace-profile/invalidcercall-mda.md)|[invalidFunctionPointerInDelegate](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)|  
|[invalidGCHandleCookie](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)|[invalidIUnknown](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)|  
|[invalidMemberDeclaration](../../../docs/framework/debug-trace-profile/invalidmemberdeclaration-mda.md)|[invalidOverlappedToPinvoke](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)|  
|[invalidVariant](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)|[jitCompilationStart](../../../docs/framework/debug-trace-profile/jitcompilationstart-mda.md)|  
|[loaderLock](../../../docs/framework/debug-trace-profile/loaderlock-mda.md)|[loadFromContext](../../../docs/framework/debug-trace-profile/loadfromcontext-mda.md)|  
|[marshalCleanupError](../../../docs/framework/debug-trace-profile/marshalcleanuperror-mda.md)|[marshaling](../../../docs/framework/debug-trace-profile/marshaling-mda.md)|  
|[memberInfoCacheCreation](../../../docs/framework/debug-trace-profile/memberinfocachecreation-mda.md)|[moduloObjectHashcode](../../../docs/framework/debug-trace-profile/moduloobjecthashcode-mda.md)|  
|[nonComVisibleBaseClass](../../../docs/framework/debug-trace-profile/noncomvisiblebaseclass-mda.md)|[notMarshalable](../../../docs/framework/debug-trace-profile/notmarshalable-mda.md)|  
|[openGenericCERCall](../../../docs/framework/debug-trace-profile/opengenericcercall-mda.md)|[overlappedFreeError](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)|  
|[pInvokeLog](../../../docs/framework/debug-trace-profile/pinvokelog-mda.md)|[pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)|  
|[raceOnRCWCleanup](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)|[reentrancy](../../../docs/framework/debug-trace-profile/reentrancy-mda.md)|  
|[releaseHandleFailed](../../../docs/framework/debug-trace-profile/releasehandlefailed-mda.md)|[reportAvOnComRelease](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)|  
|[streamWriterBufferedDataLost](../../../docs/framework/debug-trace-profile/streamwriterbuffereddatalost-mda.md)|[virtualCERCall](../../../docs/framework/debug-trace-profile/virtualcercall-mda.md)|  
  
 기본적으로 .NET Framework는 모든 관리되는 디버거에 대한 MDA의 하위 집합을 활성화합니다.  **디버그** 메뉴에서 **예외**를 클릭하고 **관리 디버깅 도우미** 목록을 확장하여 Visual Studio의 기본 집합을 볼 수 있습니다.  
  
## MDA 사용 및 사용 안 함  
 레지스트리 키, 환경 변수 및 응용 프로그램 구성 설정을 사용하여 MDA를 사용하거나 사용하지 않도록 설정할 수 있습니다.  응용 프로그램 구성 설정을 사용하려면 레지스트리 키 또는 환경 변수를 사용하도록 설정해야 합니다.  
  
 Visual Studio 2005 이상 버전에서는 호스팅 프로세스가 사용하도록 설정된 경우 기본 집합에 있는 MDA를 사용하지 않도록 설정하거나 기본 집합에 없는 MDA를 사용하도록 설정할 수 없습니다.  호스팅 프로세스는 기본적으로 사용하도록 설정되므로 명시적으로 사용하지 않도록 설정되어야 합니다.  
  
 Visual Studio에서 호스팅 프로세스를 사용하지 않도록 설정하려면 다음을 수행합니다.  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
     **프로젝트 디자이너** 창이 나타납니다.  
  
3.  **디버그** 탭을 클릭합니다.  
  
4.  **디버거 사용** 섹션에서 **Visual Studio 호스팅 프로세스 사용** 확인란을 선택 취소합니다.  
  
 그러나 호스팅 프로세스를 사용하지 않도록 설정하면 성능에 영향을 미칠 수 있습니다.  MDA 알림을 받을 때마다 Visual Studio에 MDA 대화 상자가 표시되지 않도록 하여 MDA를 사용하지 않도록 설정해야 하는 필요성을 방지할 수 있습니다.  이렇게 하려면 **디버그** 메뉴에서 **예외**를 클릭하고 **관리 디버깅 도우미** 목록을 확장한 다음 개별 MDA의 **Throw됨** 확인란을 선택하거나 선택 취소합니다.  
  
### 레지스트리 키를 사용하여 MDA 사용 및 사용 안 함  
 Windows 레지스트리에서 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework\\MDA 하위 키\(종류 REG\_SZ, 값 1\)를 추가하여 MDA를 사용하도록 설정할 수 있습니다.  다음 예제를 MDAEnable.reg라는 텍스트 파일에 복사합니다.  Windows 레지스트리 편집기\(RegEdit.exe\)를 열고 **파일** 메뉴에서 **가져오기**를 선택합니다.  MDAEnable.reg 파일을 선택하여 해당 컴퓨터에서 MDA를 사용하도록 설정합니다.  하위 키를 문자열 값 1\(DWORD 값 1 아님\)로 설정하면 *ApplicationName.suffix*.mda.config 파일에서 MDA 설정 읽기가 사용하도록 설정됩니다.  \(예를 들어, 메모장의 MDA 구성 파일은 이름이 notepad.exe.mda.config로 지정됩니다.\)  
  
```  
Windows Registry Editor Version 5.00  
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]  
"MDA"="1"  
  
```  
  
 컴퓨터가 64비트 운영 체제에서 32비트 응용 프로그램을 실행 중인 경우 MDA 키는 다음과 같이 설정됩니다.  
  
```  
Windows Registry Editor Version 5.00   
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]  
"MDA"="1"  
  
```  
  
 자세한 내용은 [응용 프로그램별 구성 설정을 사용하여 MDA 사용 및 사용 안 함](#appConfig)을 참조하세요.  레지스트리 설정은 COMPLUS\_MDA 환경 변수로 재정의할 수 있습니다.  자세한 내용은 [환경 변수를 사용하여 MDA 사용 및 사용 안 함](#envVariable)을 참조하세요.  
  
 MDA를 사용하지 않도록 설정하려면 Windows 레지스트리 편집기를 사용하여 MDA 하위 키를 0\(영\)으로 설정합니다.  
  
 기본적으로 일부 MDA는 디버거에 연결된 응용 프로그램을 실행하면 레지스트리 키를 추가하지 않더라도 사용하도록 설정됩니다.  이러한 도우미의 예는 [pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) 및 [invalidApartmentStateChange](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md)에 있습니다.  이 섹션의 앞부분에 설명되어 있는 것처럼 MDADisable.reg 파일을 실행하여 이러한 도우미를 사용하지 않도록 설정할 수 있습니다.  
  
<a name="envVariable"></a>   
### 환경 변수를 사용하여 MDA 사용 및 사용 안 함  
 MDA 활성화는 레지스트리 키를 재정의하는 환경 변수 COMPLUS\_MDA에 의해서도 제어됩니다.  COMPLUS\_MDA 문자열은 대\/소문자를 구분하지 않으며, 세미콜론으로 구분된 MDA 이름 또는 기타 특수 제어 문자열의 목록입니다.  관리되는 디버거 또는 관리되지 않는 디버거에서 시작하면 기본적으로 MDA 집합이 사용하도록 설정됩니다.  이러한 설정은 디버거에서 기본적으로 사용하도록 설정된, 세미콜론으로 구분된 MDA 목록을 환경 변수 또는 레지스트리 키 값에 추가하여 암시적으로 수행됩니다.  특수 제어 문자열은 다음과 같습니다.  
  
-   `0` \- 모든 MDA를 비활성화합니다.  
  
-   `1` \- *ApplicationName*.mda.config에서 MDA 설정을 읽습니다.  
  
-   `managedDebugger` \- 관리되는 실행 파일이 디버거에서 시작되면 암시적으로 활성화되는 모든 MDA를 명시적으로 활성화합니다.  
  
-   `unmanagedDebugger` \- 관리되지 않는 실행 파일이 디버거에서 시작되면 암시적으로 활성화되는 모든 MDA를 명시적으로 활성화합니다.  
  
 충돌하는 설정이 있는 경우 최신 설정이 이전 설정을 재정의합니다.  
  
-   `COMPLUS_MDA=0`은 디버거에서 암시적으로 사용하도록 설정된 MDA를 포함하여 모든 MDA를 사용하지 않도록 설정합니다.  
  
-   `COMPLUS_MDA=gcUnmanagedToManaged`는 디버거에서 암시적으로 사용하도록 설정된 모든 MDA 외에 `gcUnmanagedToManaged`를 사용하도록 설정합니다.  
  
-   `COMPLUS_MDA=0;gcUnmanagedToManaged`는 `gcUnmanagedToManaged`를 사용하도록 설정하지만 디버거에서 달리 암시적으로 사용하도록 설정되지 않는 MDA를 사용하지 않도록 설정합니다.  
  
<a name="appConfig"></a>   
### 응용 프로그램별 구성 설정을 사용하여 MDA 사용 및 사용 안 함  
 응용 프로그램의 MDA 구성 파일에서 일부 도우미를 개별적으로 사용하도록 설정, 사용하지 않도록 설정 및 구성할 수 있습니다.  MDA를 구성하는 데 응용 프로그램 구성 파일을 사용할 수 있으려면 MDA 레지스트리 키 또는 COMPLUS\_MDA 환경 변수를 설정해야 합니다.  응용 프로그램 구성 파일은 일반적으로 응용 프로그램 실행 파일\(.exe\)과 동일한 디렉터리에 있습니다.  파일 이름은 *ApplicationName*.mda.config 형식을 취합니다\(예: notepad.exe.mda.config\).  응용 프로그램 구성 파일에서 사용하도록 설정된 도우미는 특별히 해당 도우미의 동작을 제어하도록 디자인된 특성 또는 요소를 포함할 있습니다.  다음 예제에서는 [marshaling](../../../docs/framework/debug-trace-profile/marshaling-mda.md)를 사용하도록 설정하고 구성하는 방법을 보여 줍니다.  
  
```  
<mdaConfig>  
  <assistants>  
    <marshaling>  
      <methodFilter>  
        <match name="*"/>  
      </methodFilter>  
      <fieldFilter>  
        <match name="*"/>  
      </fieldFilter>  
    </marshaling>  
  </assistants>  
</mdaConfig>  
```  
  
 `Marshaling` MDA는 응용 프로그램에서 각 관리되는\-관리되지 않는 변환의 관리되지 않는 형식으로 마샬링되는 관리되는 형식에 대한 정보를 내보냅니다.  또한 `Marshaling` MDA는 각각 `<methodFilter>` 및 `<fieldFilter>` 자식 요소에 제공된 메서드 및 구조 필드의 이름을 필터링할 수 있습니다.  
  
 다음 예제에서는 해당 기본 설정을 사용하여 여러 MDA를 사용하도록 설정하는 방법을 보여 줍니다.  
  
```  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion />  
    <invalidCERCall />  
    <openGenericCERCall />  
    <virtualCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
> [!IMPORTANT]
>  구성 파일에 둘 이상의 도우미를 지정할 때는 사전순으로 나열해야 합니다.  예를 들어, `virtualCERCall` MDA와 `invalidCERCall` MDA를 둘 다 사용하도록 설정하려면 `<virtualCERCall />` 항목 앞에 `<invalidCERCall />` 항목을 추가해야 합니다.  항목이 사전순이 아니면 처리되지 않은 잘못된 구성 파일 예외 메시지가 표시됩니다.  
  
### MDA 출력  
 MDA 출력은 `pInvokeStackImbalance` MDA의 출력을 보여 주는 다음 예제와 유사합니다.  
  
 `A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack.  This is likely because the managed PInvoke signature does not match the unmanaged target signature.  Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.`  
  
## 참고 항목  
 [Debugging, Tracing, and Profiling](../../../docs/framework/debug-trace-profile/index.md)