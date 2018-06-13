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
ms.openlocfilehash: 9938db3f4a3d054fde52139c166fb6a2e2a402df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33388058"
---
# <a name="pinvokestackimbalance-mda"></a><span data-ttu-id="c4ad1-102">pInvokeStackImbalance MDA</span><span class="sxs-lookup"><span data-stu-id="c4ad1-102">pInvokeStackImbalance MDA</span></span>
<span data-ttu-id="c4ad1-103">`pInvokeStackImbalance` MDA(관리 디버깅 도우미)는 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성에 지정된 호출 규칙과 관리되는 서명의 매개 변수 선언을 기준으로 CLR에서 플랫폼 호출 후의 스택 깊이가 예상 스택 깊이와 일치하지 않음을 감지할 때 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4ad1-103">The `pInvokeStackImbalance` managed debugging assistant (MDA) is activated when the CLR detects that the stack depth after a platform invoke call does not match the expected stack depth, given the calling convention specified in the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute as well as the declaration of the parameters in the managed signature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4ad1-104">`pInvokeStackImbalance` MDA는 32비트 x86 플랫폼에 대해서만 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4ad1-104">The `pInvokeStackImbalance` MDA is implemented only for 32-bit x86 platforms.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4ad1-105">.NET Framework 버전 3.5에서는 `pInvokeStackImbalance` MDA가 기본적으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ad1-105">In the .NET Framework version 3.5, the `pInvokeStackImbalance` MDA is disabled by default.</span></span> <span data-ttu-id="c4ad1-106">Visual Studio 2005와 함께 .NET Framework 버전 3.5를 사용하는 경우 **디버그** 메뉴에서 **예외**를 클릭할 때 표시되는 **예외** 대화 상자의 **관리 디버깅 도우미** 목록에 `pInvokeStackImbalance` MDA가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c4ad1-106">When you use the .NET Framework version 3.5 with Visual Studio 2005, the `pInvokeStackImbalance` MDA will appear in the **Managed Debugging Assistants** list in the **Exceptions** dialog box (which is displayed when you click **Exceptions** on the **Debug** menu).</span></span> <span data-ttu-id="c4ad1-107">그러나 `pInvokeStackImbalance`에 대해 **Throw됨** 확인란을 선택하거나 선택 취소해도 MDA가 사용하거나 사용하지 않도록 설정되지는 않습니다. MDA가 활성화될 때 Visual Studio에서 예외를 발생시키는지 여부만 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ad1-107">However, selecting or clearing the **Thrown** check box for `pInvokeStackImbalance` does not enable or disable the MDA; it only controls whether Visual Studio throws an exception when the MDA is activated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="c4ad1-108">증상</span><span class="sxs-lookup"><span data-stu-id="c4ad1-108">Symptoms</span></span>  
 <span data-ttu-id="c4ad1-109">응용 프로그램이 플랫폼 호출을 수행할 때나 이후에 액세스 위반 또는 메모리 손상을 발견합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ad1-109">An application encounters an access violation or memory corruption when making or following a platform invoke call.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="c4ad1-110">원인</span><span class="sxs-lookup"><span data-stu-id="c4ad1-110">Cause</span></span>  
 <span data-ttu-id="c4ad1-111">플랫폼 호출의 관리되는 서명이 호출되는 메서드의 관리되지 않는 서명과 일치하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ad1-111">The managed signature of the platform invoke call might not match the unmanaged signature of the method being called.</span></span>  <span data-ttu-id="c4ad1-112">이 불일치는 관리되는 서명에서 올바른 개수의 매개 변수를 선언하지 않았거나 매개 변수에 대해 적절한 크기를 지정하지 않아서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ad1-112">This mismatch can be caused by the managed signature not declaring the correct number of parameters or not specifying the appropriate size for the parameters.</span></span>  <span data-ttu-id="c4ad1-113"><xref:System.Runtime.InteropServices.DllImportAttribute> 특성에 지정될 수 있는 호출 규칙이 관리되지 않는 호출 규칙과 일치하지 않아 MDA가 활성화될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ad1-113">The MDA can also activate because the calling convention, possibly specified by the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute, does not match the unmanaged calling convention.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="c4ad1-114">해결</span><span class="sxs-lookup"><span data-stu-id="c4ad1-114">Resolution</span></span>  
 <span data-ttu-id="c4ad1-115">관리되는 플랫폼 호출 서명과 호출 규칙을 검토하여 기본 대상의 서명 및 호출 규칙과 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ad1-115">Review the managed platform invoke signature and calling convention to confirm it matches the signature and calling convention of the native target.</span></span>  <span data-ttu-id="c4ad1-116">관리되는 측면과 관리되지 않는 측면 둘 다에서 호출 규칙을 명시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ad1-116">Try explicitly specifying the calling convention on both the managed and unmanaged sides.</span></span> <span data-ttu-id="c4ad1-117">가능성은 적지만 관리되지 않는 컴파일러의 버그와 같은 다른 이유로 관리되지 않는 함수에서 스택 불균형이 발생했을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ad1-117">It is also possible, although not as likely, that the unmanaged function unbalanced the stack for some other reason, such as a bug in the unmanaged compiler.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="c4ad1-118">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="c4ad1-118">Effect on the Runtime</span></span>  
 <span data-ttu-id="c4ad1-119">모든 플랫폼 호출이 CLR에서 최적화되지 않은 경로를 사용하도록 강제합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ad1-119">Forces all platform invoke calls to take the nonoptimized path in the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="c4ad1-120">출력</span><span class="sxs-lookup"><span data-stu-id="c4ad1-120">Output</span></span>  
 <span data-ttu-id="c4ad1-121">MDA 메시지는 스택 불균형을 발생시키는 플랫폼 호출 메서드 호출의 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ad1-121">The MDA message gives the name of the platform invoke method call that is causing the stack imbalance.</span></span>  <span data-ttu-id="c4ad1-122">`SampleMethod` 메서드의 플랫폼 호출 샘플 메시지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ad1-122">A sample message of a platform invoke call on method `SampleMethod` is:</span></span>  
  
```  
A call to PInvoke function 'SampleMethod' has unbalanced the stack.   
This is likely because the managed PInvoke signature does not match   
the unmanaged target signature. Check that the calling convention and   
parameters of the PInvoke signature match the target unmanaged signature.  
```  
  
## <a name="configuration"></a><span data-ttu-id="c4ad1-123">구성</span><span class="sxs-lookup"><span data-stu-id="c4ad1-123">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeStackImbalance />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4ad1-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4ad1-124">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="c4ad1-125">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="c4ad1-125">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="c4ad1-126">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="c4ad1-126">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
