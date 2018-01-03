---
title: pInvokeStackImbalance MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9da05a84568a6168ed9f450afa48aa6864ed575
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="pinvokestackimbalance-mda"></a>pInvokeStackImbalance MDA
`pInvokeStackImbalance` MDA(관리 디버깅 도우미)는 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성에 지정된 호출 규칙과 관리되는 서명의 매개 변수 선언을 기준으로 CLR에서 플랫폼 호출 후의 스택 깊이가 예상 스택 깊이와 일치하지 않음을 감지할 때 활성화됩니다.  
  
> [!NOTE]
>  `pInvokeStackImbalance` MDA는 32비트 x86 플랫폼에 대해서만 구현됩니다.  
  
> [!NOTE]
>  .NET Framework 버전 3.5에서는 `pInvokeStackImbalance` MDA가 기본적으로 사용되지 않습니다. Visual Studio 2005와 함께 .NET Framework 버전 3.5를 사용하는 경우 **디버그** 메뉴에서 **예외**를 클릭할 때 표시되는 **예외** 대화 상자의 **관리 디버깅 도우미** 목록에 `pInvokeStackImbalance` MDA가 나타납니다. 그러나 `pInvokeStackImbalance`에 대해 **Throw됨** 확인란을 선택하거나 선택 취소해도 MDA가 사용하거나 사용하지 않도록 설정되지는 않습니다. MDA가 활성화될 때 Visual Studio에서 예외를 발생시키는지 여부만 제어합니다.  
  
## <a name="symptoms"></a>증상  
 응용 프로그램이 플랫폼 호출을 수행할 때나 이후에 액세스 위반 또는 메모리 손상을 발견합니다.  
  
## <a name="cause"></a>원인  
 플랫폼 호출의 관리되는 서명이 호출되는 메서드의 관리되지 않는 서명과 일치하지 않을 수 있습니다.  이 불일치는 관리되는 서명에서 올바른 개수의 매개 변수를 선언하지 않았거나 매개 변수에 대해 적절한 크기를 지정하지 않아서 발생할 수 있습니다.  <xref:System.Runtime.InteropServices.DllImportAttribute> 특성에 지정될 수 있는 호출 규칙이 관리되지 않는 호출 규칙과 일치하지 않아 MDA가 활성화될 수도 있습니다.  
  
## <a name="resolution"></a>해결  
 관리되는 플랫폼 호출 서명과 호출 규칙을 검토하여 기본 대상의 서명 및 호출 규칙과 일치하는지 확인합니다.  관리되는 측면과 관리되지 않는 측면 둘 다에서 호출 규칙을 명시적으로 지정합니다. 가능성은 적지만 관리되지 않는 컴파일러의 버그와 같은 다른 이유로 관리되지 않는 함수에서 스택 불균형이 발생했을 수도 있습니다.  
  
## <a name="effect-on-the-runtime"></a>런타임에 대한 영향  
 모든 플랫폼 호출이 CLR에서 최적화되지 않은 경로를 사용하도록 강제합니다.  
  
## <a name="output"></a>출력  
 MDA 메시지는 스택 불균형을 발생시키는 플랫폼 호출 메서드 호출의 이름을 제공합니다.  `SampleMethod` 메서드의 플랫폼 호출 샘플 메시지는 다음과 같습니다.  
  
```  
A call to PInvoke function 'SampleMethod' has unbalanced the stack.   
This is likely because the managed PInvoke signature does not match   
the unmanaged target signature. Check that the calling convention and   
parameters of the PInvoke signature match the target unmanaged signature.  
```  
  
## <a name="configuration"></a>구성  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeStackImbalance />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [관리 디버깅 도우미를 사용하여 오류 진단](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)
