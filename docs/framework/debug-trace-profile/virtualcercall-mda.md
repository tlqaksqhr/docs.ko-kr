---
title: virtualCERCall MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- virtualCERCall MDA
- virtual CER calls
- constrained execution regions
- CER calls
- managed debugging assistants (MDAs), CER calls
ms.assetid: 1eb18c7a-f5e0-443f-80fb-67bfbb047da2
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 010c5dd082c10556ed264306b7575cbe5399fda3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="virtualcercall-mda"></a><span data-ttu-id="80d3e-102">virtualCERCall MDA</span><span class="sxs-lookup"><span data-stu-id="80d3e-102">virtualCERCall MDA</span></span>
<span data-ttu-id="80d3e-103">`virtualCERCall` MDA(관리 디버깅 도우미)는 CER(제약이 있는 실행 영역) 호출 그래프 내의 호출 사이트가 가상 대상, 즉 최종이 아닌 가상 메서드에 대한 가상 호출 또는 인터페이스를 사용한 호출을 참조함을 나타내는 경고로 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="80d3e-103">The `virtualCERCall` managed debugging assistant (MDA) is activated as a warning indicating that a call site within a constrained execution region (CER) call graph refers to a virtual target, that is, a virtual call to a non-final virtual method or a call using an interface.</span></span> <span data-ttu-id="80d3e-104">CLR(공용 언어 런타임)은 중간 언어 및 메타데이터 분석만으로 이러한 호출의 대상 메서드를 예측할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80d3e-104">The common language runtime (CLR) cannot predict the destination method of these calls from the intermediate language and metadata analysis alone.</span></span> <span data-ttu-id="80d3e-105">결과적으로, CER 그래프의 일부로 호출 트리를 준비할 수 없으며 하위 트리가 자동으로 차단될 수 없다는 점에서 스레드가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="80d3e-105">As a result, the call tree cannot be prepared as part of the CER graph and thread aborts in that subtree cannot be automatically blocked.</span></span> <span data-ttu-id="80d3e-106">이 MDA는 호출 대상을 계산하는 데 필요한 추가 정보가 런타임 시 확인된 다음 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> 메서드에 대한 명시적 호출을 사용하여 CER을 확장해야 하는 경우를 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="80d3e-106">This MDA warns of cases where a CER might need to be extended by using explicit calls to the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> method once the additional information required to compute the call target is known at run time.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="80d3e-107">증상</span><span class="sxs-lookup"><span data-stu-id="80d3e-107">Symptoms</span></span>  
 <span data-ttu-id="80d3e-108">스레드가 중단되거나 응용 프로그램 도메인이 언로드될 때 CER이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80d3e-108">CERs that do not run when a thread is aborted or an application domain is unloaded.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="80d3e-109">원인</span><span class="sxs-lookup"><span data-stu-id="80d3e-109">Cause</span></span>  
 <span data-ttu-id="80d3e-110">CER에 자동으로 준비할 수 없는 가상 메서드 호출이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80d3e-110">A CER contains a call to a virtual method that cannot be prepared automatically.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="80d3e-111">해결</span><span class="sxs-lookup"><span data-stu-id="80d3e-111">Resolution</span></span>  
 <span data-ttu-id="80d3e-112">가상 메서드에 대해 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="80d3e-112">Call <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> for the virtual method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="80d3e-113">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="80d3e-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="80d3e-114">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80d3e-114">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="80d3e-115">출력</span><span class="sxs-lookup"><span data-stu-id="80d3e-115">Output</span></span>  
  
```  
Method 'MethodWithCer', while executing within a constrained execution region, makes a call  
at IL offset 0x0024 to 'VirtualMethod', which is virtual and cannot be prepared automatically  
at compile time. The caller must ensure this method is prepared explicitly at  
runtime before entering the constrained execution region.  
method name="VirtualMethod"  
declaringType name="VirtualCERCall+MyClass"  
  declaringModule name="mda"  
    callsite name="MethodWithCer" offset="0x0024"  
```  
  
## <a name="configuration"></a><span data-ttu-id="80d3e-116">구성</span><span class="sxs-lookup"><span data-stu-id="80d3e-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    < VirtualCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="80d3e-117">예</span><span class="sxs-lookup"><span data-stu-id="80d3e-117">Example</span></span>  
  
```  
class MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    virtual void VirtualMethod()  
    {  
        ...  
    }  
}  
  
class MyDerivedClass : MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    override void VirtualMethod()  
    {  
        ...  
    }  
}  
  
void MethodWithCer(MyClass object)  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    try  
    {  
        ...  
    }  
    finally  
    {  
        // Start of the CER.  
  
        // Cannot tell at analysis time whether object is a MyClass  
        // or a MyDerivedClass, so we do not know which version of   
        // VirtualMethod we are going to call.  
        object.VirtualMethod();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="80d3e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80d3e-118">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="80d3e-119">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="80d3e-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="80d3e-120">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="80d3e-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
