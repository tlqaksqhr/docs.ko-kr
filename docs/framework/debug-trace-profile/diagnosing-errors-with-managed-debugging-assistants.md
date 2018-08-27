---
title: 관리 디버깅 도우미를 사용하여 오류 진단
ms.date: 08/14/2018
f1_keywords:
- EHMDA
helpviewer_keywords:
- run-time error debugging
- managed code, run-time debugging
- resource debugging
- registry, MDAs
- common language runtime, debugging
- MDAs (managed debugging assistants)
- configuration files [.NET Framework], debugging runtime events
- messages, managed debugging assistants
- application configuration files, managed debugging assistants
- debugging [.NET Framework], managed debugging assistants
- environment variables, MDAs
- access violation debugging [.NET Framework]
- diagnostics, managed debugging assistants
- unmanaged code, run-time debugging
- default debug output stream
- memory, debugging
- app.config files, managed debugging assistants
- managed debugging assistants (MDAs)
- debugging [.NET Framework], run-time errors
- trapping events
- runtime, error debugging
- disabling MDAs
- output, managed debugging assistants
- errors [.NET Framework], managed debugging assistants
ms.assetid: 76994ee6-9fa9-4059-b813-26578d24427c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b745fa6a78ab2a7ab0b3a94c9921883d3c56c1b7
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935746"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a>관리 디버깅 도우미를 사용 하 여 오류 진단

MDA(관리 디버깅 도우미)는 런타임 상태에 대한 정보를 제공하기 위해 CLR(공용 언어 런타임)과 함께 작동하는 디버깅 도우미입니다. 이 도우미는 다른 방법으로는 트래핑할 수 없는 런타임 이벤트에 대한 정보 메시지를 생성합니다. MDA를 사용하면 관리 코드와 비관리 코드 간에 변환할 때 발생하는 찾기 어려운 응용 프로그램 버그를 구분할 수 있습니다.

할 수 있습니다 [사용할지](#enable-and-disable-mdas) Windows 레지스트리 키를 추가 하거나 환경 변수를 설정 하 여 모든 Mda 합니다. 응용 프로그램 구성 설정을 사용하여 특정 MDA를 사용하도록 설정할 수 있습니다. 응용 프로그램의 구성 파일에서 일부 개별 MDA에 대한 추가 구성 설정을 지정할 수 있습니다. 이러한 구성 파일은 런타임이 로드될 때 구문 분석되므로 관리되는 응용 프로그램이 시작되기 전에 MDA를 사용하도록 설정해야 합니다. 이미 시작된 응용 프로그램에 대해서는 MDA를 사용하도록 설정할 수 없습니다.

다음 표에서.NET Framework를 사용 하 여 제공 되는 Mda를 나열 합니다.

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

기본적으로 .NET Framework는 모든 관리되는 디버거에 대한 MDA의 하위 집합을 활성화합니다. 기본 선택 하 여 Visual Studio에서 집합을 볼 수 있습니다 **Windows** > **예외 설정** 에 **디버그** 메뉴 및 다음 확장 하는 **관리 디버깅 도우미** 목록입니다.

![Visual Studio에서 예외 설정 창](media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a>사용 안 함 Mda 사용 및 사용

레지스트리 키, 환경 변수 및 응용 프로그램 구성 설정을 사용하여 MDA를 사용하거나 사용하지 않도록 설정할 수 있습니다. 응용 프로그램 구성 설정을 사용하려면 레지스트리 키 또는 환경 변수를 사용하도록 설정해야 합니다.

> [!TIP]
> Mda를 비활성화 하는 대신 MDA 알림의 받을 때마다 MDA 대화 상자를 표시에서 Visual Studio를 방지할 수 있습니다. 이 위해 선택 **Windows** > **예외 설정** 에 **디버그** 메뉴를 확장 합니다 **관리 디버깅 도우미**목록 및 다음을 선택 하거나 선택을 취소 합니다 **중단 Throw** 개별 MDA에 대 한 확인란 합니다.

### <a name="registry-key"></a>레지스트리 키

Mda를 사용 하도록 설정 하려면 추가 합니다 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\합니다. NETFramework\MDA** Windows 레지스트리에서 하위 키 (종류 REG_SZ, 값 1). 다음 예제에서는 라는 텍스트 파일에 복사 *MDAEnable.reg*합니다. Windows 레지스트리 편집기 (RegEdit.exe)를 엽니다 들어오고 합니다 **파일** 메뉴 **가져오기**합니다. 선택 된 *MDAEnable.reg* 파일을 해당 컴퓨터에서 Mda를 사용 하도록 설정 합니다. 하위 키의 문자열 값을 설정 **1** (의 DWORD 값이 아닌 **1**)에서 MDA 설정 읽을 수 있습니다 합니다 *ApplicationName.suffix*..mda.config 파일입니다. 예를 들어 notepad.exe.mda.config로 지정 됩니다 메모장의 MDA 구성 파일 이라는 것입니다.

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

컴퓨터가 64비트 운영 체제에서 32비트 응용 프로그램을 실행 중인 경우 MDA 키는 다음과 같이 설정됩니다.

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

참조 [프로그램별 구성 설정을](#application-specific-configuration-settings) 자세한 내용은 합니다. 레지스트리 설정은 COMPLUS_MDA 환경 변수로 재정의할 수 있습니다. 참조 [환경 변수](#environment-variable) 자세한 내용은 합니다.

Mda를 사용 하지 않으려면 MDA 하위 키로 설정 합니다 **0** Windows 레지스트리 편집기를 사용 하 여 (0).

기본적으로 일부 MDA는 디버거에 연결된 응용 프로그램을 실행하면 레지스트리 키를 추가하지 않더라도 사용하도록 설정됩니다. 이러한 도우미를 실행 하 여 비활성화할 수 있습니다 합니다 *MDADisable.reg* 이 단원의 앞에서 설명한 대로 파일입니다.

### <a name="environment-variable"></a>환경 변수

MDA 활성화는 레지스트리 키를 재정의하는 환경 변수 COMPLUS_MDA에 의해서도 제어됩니다. COMPLUS_MDA 문자열은 대/소문자를 구분하지 않으며, 세미콜론으로 구분된 MDA 이름 또는 기타 특수 제어 문자열의 목록입니다. 관리되는 디버거 또는 관리되지 않는 디버거에서 시작하면 기본적으로 MDA 집합이 사용하도록 설정됩니다. 이러한 설정은 디버거에서 기본적으로 사용하도록 설정된, 세미콜론으로 구분된 MDA 목록을 환경 변수 또는 레지스트리 키 값에 추가하여 암시적으로 수행됩니다. 특수 제어 문자열은 다음과 같습니다.

- `0` - 모든 MDA를 비활성화합니다.

- `1` - *ApplicationName*.mda.config에서 MDA 설정을 읽습니다.

- `managedDebugger` - 관리되는 실행 파일이 디버거에서 시작되면 암시적으로 활성화되는 모든 MDA를 명시적으로 활성화합니다.

- `unmanagedDebugger` - 관리되지 않는 실행 파일이 디버거에서 시작되면 암시적으로 활성화되는 모든 MDA를 명시적으로 활성화합니다.

충돌하는 설정이 있는 경우 최신 설정이 이전 설정을 재정의합니다.

- `COMPLUS_MDA=0`은 디버거에서 암시적으로 사용하도록 설정된 MDA를 포함하여 모든 MDA를 사용하지 않도록 설정합니다.

- `COMPLUS_MDA=gcUnmanagedToManaged`는 디버거에서 암시적으로 사용하도록 설정된 모든 MDA 외에 `gcUnmanagedToManaged`를 사용하도록 설정합니다.

- `COMPLUS_MDA=0;gcUnmanagedToManaged`는 `gcUnmanagedToManaged`를 사용하도록 설정하지만 디버거에서 달리 암시적으로 사용하도록 설정되지 않는 MDA를 사용하지 않도록 설정합니다.

### <a name="application-specific-configuration-settings"></a>응용 프로그램별 구성 설정

응용 프로그램의 MDA 구성 파일에서 일부 도우미를 개별적으로 사용하도록 설정, 사용하지 않도록 설정 및 구성할 수 있습니다. MDA를 구성하는 데 응용 프로그램 구성 파일을 사용할 수 있으려면 MDA 레지스트리 키 또는 COMPLUS_MDA 환경 변수를 설정해야 합니다. 응용 프로그램 구성 파일은 일반적으로 응용 프로그램 실행 파일(.exe)과 동일한 디렉터리에 있습니다. 파일 이름은 *ApplicationName*.mda.config 형식을 사용합니다(예: notepad.exe.mda.config). 응용 프로그램 구성 파일에서 사용하도록 설정된 도우미는 특별히 해당 도우미의 동작을 제어하도록 디자인된 특성 또는 요소를 포함할 있습니다.

다음 예제에서는 설정 및 구성 하는 방법을 보여 줍니다 합니다 [마샬링](../../../docs/framework/debug-trace-profile/marshaling-mda.md):

```xml
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

`Marshaling` MDA는 응용 프로그램에서 각 관리되는-관리되지 않는 변환의 관리되지 않는 형식으로 마샬링되는 관리되는 형식에 대한 정보를 내보냅니다. `Marshaling` MDA 메서드의 이름을 필터링 수도 및 구조 필드에 제공 합니다 **methodFilter** 및 **fieldFilter** 자식 요소를 각각.

다음 예제에서는 해당 기본 설정을 사용 하 여 여러 Mda를 활성화 하는 방법을 보여 줍니다.

```xml
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
> 구성 파일에 둘 이상의 도우미를 지정할 때는 사전순으로 나열해야 합니다. 예를 들어, `virtualCERCall` MDA와 `invalidCERCall` MDA를 둘 다 사용하도록 설정하려면 `<invalidCERCall />` 항목 앞에 `<virtualCERCall />` 항목을 추가해야 합니다. 항목이 사전순이 아니면 처리되지 않은 잘못된 구성 파일 예외 메시지가 표시됩니다.

## <a name="mda-exceptions"></a>MDA 예외

MDA를 사용 하는 경우 활성 상태인도 때 프로그램 코드가 실행 되지 않는 디버거에서 합니다. 디버거가 없을 때 MDA 이벤트가 발생하면 이벤트 메시지가 처리되지 않은 예외가 아니더라도 처리되지 않은 예외 대화 상자에 표시됩니다. 이 대화 상자가 표시되지 않도록 하려면 코드가 디버깅 환경에서 실행되지 않는 경우 MDA 사용 설정을 제거하세요.

Visual Studio 통합된 개발 환경 (IDE)에서 코드 실행 하는 경우 특정 MDA 이벤트에 대해 표시 되는 예외 대화 상자를 방지할 수 있습니다. 이렇게 하는 **디버그** 메뉴 선택 **Windows** > **예외 설정**합니다. 에 **예외 설정** 창 확장를 **관리 디버깅 도우미** 목록에서 선택한 다음 선택을 취소는 **중단 Throw** 개별 MDA에 대 한 확인란 합니다. 이 대화 상자를 사용할 수도 있습니다 *사용* MDA 예외 대화 상자가 표시 됩니다.

## <a name="mda-output"></a>MDA 출력

MDA 출력에서 출력을 보여 주는 다음 예제와 비슷합니다.는 `PInvokeStackImbalance` MDA:

**PInvoke 함수 호출 ' MDATest! MDATest.Program::StdCall' 스택 불안정 하 게 되었습니다. 관리 되는 PInvoke 서명이 관리 되지 않는 대상 서명이 일치 하지 않으므로 가능성이 있습니다. 호출 규칙 및 PInvoke 서명의 매개 변수를 대상 비관리 시그니처와 일치 하는지 확인 합니다.**

## <a name="see-also"></a>참고자료

- [디버깅, 추적 및 프로파일링](../../../docs/framework/debug-trace-profile/index.md)
