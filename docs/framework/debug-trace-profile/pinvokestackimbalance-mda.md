---
title: pInvokeStackImbalance MDA
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5594166081c36fbda1e5d1a62e017aaceb7a553d
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42912116"
---
# <a name="pinvokestackimbalance-mda"></a>PInvokeStackImbalance MDA

합니다 `PInvokeStackImbalance` MDA (관리 디버깅 도우미)는 CLR 플랫폼 호출 후 스택 깊이에 지정 된 호출 규칙은 예상된 스택 깊이 일치 하지 않음을 감지할 때 활성화 되는 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성 및 관리 되는 시그니처에서 매개 변수의 선언입니다.

`PInvokeStackImbalance` MDA는 32비트 x86 플랫폼에 대해서만 구현됩니다.

> [!NOTE]
> `PInvokeStackImbalance` MDA는 기본적으로 비활성화 됩니다. Visual Studio 2017에서를 `PInvokeStackImbalance` MDA에 표시 되는 **관리 디버깅 도우미** 목록에 **예외 설정** 대화 상자 (선택 하면 표시 되는 **디버그**  >  **Windows** > **예외 설정**). 그러나 선택 하거나 선택 취소 합니다 **중단 Throw** MDA가 활성화 하는 경우 Visual Studio 예외를 throw 하는지 여부를 제어; 확인란을 사용 하도록 설정 하지 않거나 MDA를 사용 하지 않도록 설정 합니다.

## <a name="symptoms"></a>증상

응용 프로그램이 플랫폼 호출을 수행할 때나 이후에 액세스 위반 또는 메모리 손상을 발견합니다.

## <a name="cause"></a>원인

플랫폼 호출의 관리되는 서명이 호출되는 메서드의 관리되지 않는 서명과 일치하지 않을 수 있습니다.  이 불일치는 관리되는 서명에서 올바른 개수의 매개 변수를 선언하지 않았거나 매개 변수에 대해 적절한 크기를 지정하지 않아서 발생할 수 있습니다.  <xref:System.Runtime.InteropServices.DllImportAttribute> 특성에 지정될 수 있는 호출 규칙이 관리되지 않는 호출 규칙과 일치하지 않아 MDA가 활성화될 수도 있습니다.

## <a name="resolution"></a>해결

관리되는 플랫폼 호출 서명과 호출 규칙을 검토하여 기본 대상의 서명 및 호출 규칙과 일치하는지 확인합니다.  관리되는 측면과 관리되지 않는 측면 둘 다에서 호출 규칙을 명시적으로 지정합니다. 가능성은 적지만 관리되지 않는 컴파일러의 버그와 같은 다른 이유로 관리되지 않는 함수에서 스택 불균형이 발생했을 수도 있습니다.

## <a name="effect-on-the-runtime"></a>런타임에 대한 영향

모든 플랫폼 호출이 CLR에서 최적화되지 않은 경로를 사용하도록 강제합니다.

## <a name="output"></a>출력

MDA 메시지는 스택 불균형을 발생시키는 플랫폼 호출 메서드 호출의 이름을 제공합니다. `SampleMethod` 메서드의 플랫폼 호출 샘플 메시지는 다음과 같습니다.

**PInvoke '은 SampleMethod' 함수에 대 한 호출 스택 불안정 하 게 되었습니다. 관리 되는 PInvoke 서명이 관리 되지 않는 대상 서명이 일치 하지 않으므로 가능성이 있습니다. 호출 규칙 및 PInvoke 서명의 매개 변수를 대상 비관리 시그니처와 일치 하는지 확인 합니다.**

## <a name="configuration"></a>구성

```xml
<mdaConfig>
  <assistants>
    <pInvokeStackImbalance />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a>참고 항목

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [관리 디버깅 도우미를 사용하여 오류 진단](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)
