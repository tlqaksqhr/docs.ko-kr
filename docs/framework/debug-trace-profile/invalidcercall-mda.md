---
title: invalidCERCall MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- invalid CER calls
- InvalidCERCall MDA
- MDAs (managed debugging assistants), CER calls
- constrained execution regions
- CER calls
- managed debugging assistants (MDAs), CER calls
ms.assetid: c4577410-602e-44e5-9dab-fea7c55bcdfe
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0c051e1513f8e8ad1735085cb93f106b4fb9b0d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="invalidcercall-mda"></a><span data-ttu-id="ac7ad-102">invalidCERCall MDA</span><span class="sxs-lookup"><span data-stu-id="ac7ad-102">invalidCERCall MDA</span></span>
<span data-ttu-id="ac7ad-103">`invalidCERCall` MDA(관리 디버깅 도우미)는 안정성 계약 또는 지나치게 약한 계약이 없는 메서드에 대한 호출이 CER(제약이 있는 실행 영역) 그래프 내에 있으면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-103">The `invalidCERCall` managed debugging assistant (MDA) is activated when there is a call within the constrained execution region (CER) graph to a method that has no reliability contract or an excessively weak contract.</span></span> <span data-ttu-id="ac7ad-104">약한 계약은 가장 나쁜 사례 상태 손상이 호출에 전달된 인스턴스보다 큰 범위에 관련됨을 선언하는 계약입니다. 즉, <xref:System.AppDomain> 또는 프로세스 상태가 손상될 수 있거나 CER 내에서 호출될 때 결과가 항상 결정적으로 계산 가능한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-104">A weak contract is a contract that declares that the worst case state corruption is of greater scope than the instance passed to the call, that is, the <xref:System.AppDomain> or process state may become corrupted or that its result is not always deterministically computable when called within a CER.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ac7ad-105">증상</span><span class="sxs-lookup"><span data-stu-id="ac7ad-105">Symptoms</span></span>  
 <span data-ttu-id="ac7ad-106">CER에서 코드를 실행할 경우 예기치 않은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-106">Unexpected results when executing code in a CER.</span></span> <span data-ttu-id="ac7ad-107">증상은 구체적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-107">The symptoms are not specific.</span></span> <span data-ttu-id="ac7ad-108">불안정한 메서드에 대한 호출 시, 런타임이 해당 메서드를 미리 준비하거나 런타임에 <xref:System.Threading.ThreadAbortException> 예외로부터 보호하지 않았기 때문에 예기치 않은 <xref:System.OutOfMemoryException>, <xref:System.Threading.ThreadAbortException> 또는 기타 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-108">They could be an unexpected <xref:System.OutOfMemoryException>, a <xref:System.Threading.ThreadAbortException>, or other exceptions at the call into the unreliable method because the runtime did not prepare it ahead of time or protect it from <xref:System.Threading.ThreadAbortException> exceptions at run time.</span></span> <span data-ttu-id="ac7ad-109">더 큰 위협은 CER의 목표와 다르게 런타임에 메서드에서 발생하는 예외로 인해 <xref:System.AppDomain> 또는 프로세스가 불안정한 상태가 될 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-109">A greater threat is that any exception resulting from the method at run time could leave the <xref:System.AppDomain> or process in an unstable state, which is contrary to the objective of a CER.</span></span> <span data-ttu-id="ac7ad-110">이와 같은 상태 손상을 피하기 위해 CER을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-110">The reason a CER is created is to avoid state corruptions such as this.</span></span> <span data-ttu-id="ac7ad-111">일관된 상태의 정보가 응용 프로그램마다 다르기 때문에 손상된 상태의 증상은 응용 프로그램별로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-111">The symptoms of corrupt state are application specific because the definition of consistent state is different between applications.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ac7ad-112">원인</span><span class="sxs-lookup"><span data-stu-id="ac7ad-112">Cause</span></span>  
 <span data-ttu-id="ac7ad-113">CER 내의 코드가 CER에서 실행할 수 없는 <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute>가 포함되지 않거나 약한 <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute>가 포함된 함수를 호출하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-113">Code within a CER is calling a function with no <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> or with a weak <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> that is not compatible with running in a CER.</span></span>  
  
 <span data-ttu-id="ac7ad-114">안정성 계약 구문에서 약한 계약은 <xref:System.Runtime.ConstrainedExecution.Consistency> 열거형 값을 지정하지 않거나 <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptProcess>, <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptAppDomain> 또는 <xref:System.Runtime.ConstrainedExecution.Cer.None>의 <xref:System.Runtime.ConstrainedExecution.Consistency> 값을 지정하는 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-114">In terms of reliability contract syntax, a weak contract is a contract that does not specify a <xref:System.Runtime.ConstrainedExecution.Consistency> enumeration value or specifies a <xref:System.Runtime.ConstrainedExecution.Consistency> value of <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptProcess>, <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptAppDomain>, or <xref:System.Runtime.ConstrainedExecution.Cer.None>.</span></span> <span data-ttu-id="ac7ad-115">이러한 조건은 호출되는 코드가 일관된 상태를 유지하기 위해 CER에서 다른 코드의 작업을 지연시킬 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-115">Any of these conditions indicates that the code called may impede the efforts of the other code in the CER to maintain consistent state.</span></span>  <span data-ttu-id="ac7ad-116">CER을 사용하면 코드가 매우 결정적인 방식으로 오류를 처리할 수 있으므로 응용 프로그램에 중요한 내부 고정이 유지되고 메모리 부족 예외와 같은 일시적인 오류가 발생해도 코드가 계속 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-116">CERs allow code to treat errors in a very deterministic manner, maintaining internal invariants that are important to the application and allowing it to continue running in the face of transient errors such as out-of-memory exceptions.</span></span>  
  
 <span data-ttu-id="ac7ad-117">이 MDA가 활성화되는 것은 호출자가 예상하지 않았거나 <xref:System.AppDomain> 또는 프로세스가 손상되거나 복구할 수 없게 되는 방식으로 CER에서 호출 중인 메서드가 실패할 수 있는 가능성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-117">The activation of this MDA indicates a possibility the method being called in the CER can fail in a way that the caller did not expect or that leaves the <xref:System.AppDomain> or process state corrupted or unrecoverable.</span></span> <span data-ttu-id="ac7ad-118">물론 호출된 코드는 제대로 실행될 수 있고 문제는 계약이 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-118">Of course, the called code might execute correctly and the problem is simply a missing contract.</span></span> <span data-ttu-id="ac7ad-119">신뢰할 수 있는 코드 작성에 관련된 문제는 확인하기 힘들지만 계약이 없다는 것은 코드가 제대로 실행될 수 없음을 나타내는 좋은 표시기입니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-119">However, the issues involved in writing reliable code are subtle and the absence of a contract is a good indicator the code might not execute correctly.</span></span> <span data-ttu-id="ac7ad-120">계약은 프로그래머가 확실히 코딩했고 이러한 보장이 이후 코드 버전에서 변경되지 않을 것임을 약속함을 나타내는 표시기입니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-120">The contracts are indicators that the programmer has coded reliably and also promises that these guarantees will not change in future revisions of the code.</span></span>  <span data-ttu-id="ac7ad-121">즉, 계약은 단순한 구현 세부 정보가 아니라 의도적인 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-121">That is, the contracts are declarations of intent and not just implementation details.</span></span>  
  
 <span data-ttu-id="ac7ad-122">약하거나 존재하지 않는 계약이 포함된 메서드는 예측할 수 없는 다양한 방식으로 실패할 수 있으므로 런타임은 지연 JIT 컴파일링, 제네릭 사전 채우기 또는 스레드 중단 등을 통해 도입된 메서드에서 예측할 수 없는 자체적인 오류를 제거하려고 시도하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-122">Because any method with a weak or nonexistent contract can potentially fail in many unpredictable ways, the runtime does not attempt to remove any of its own unpredictable failures from the method  that are introduced by lazy JIT-compiling, generics dictionary population, or thread aborts, for example.</span></span> <span data-ttu-id="ac7ad-123">즉, 이 MDA가 활성화되면 이것은 런타임이 호출되는 메서드를 정의되는 CER에 포함하지 않았고 이 하위 트리를 계속 준비하면 잠재적인 오류를 마스킹할 수 있기 때문에 호출 그래프가 이 노드에서 종료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-123">That is, when this MDA is activated, it indicates that the runtime did not include the called method in the CER being defined; the call graph was terminated at this node because continuing to prepare this subtree would help mask the potential error.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ac7ad-124">해결</span><span class="sxs-lookup"><span data-stu-id="ac7ad-124">Resolution</span></span>  
 <span data-ttu-id="ac7ad-125">해당 함수 호출을 사용하지 않거나 유효한 안정성 계약을 함수에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-125">Add a valid reliability contract to the function or avoid using that function call.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ac7ad-126">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="ac7ad-126">Effect on the Runtime</span></span>  
 <span data-ttu-id="ac7ad-127">CER에서 약한 계약을 호출하면 작업을 완료하기 위해 CER이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-127">The effect of calling a weak contract from a CER could be the CER failure to complete its operations.</span></span> <span data-ttu-id="ac7ad-128">이로 인해 <xref:System.AppDomain> 프로세스 상태가 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-128">This could lead to corruption of the <xref:System.AppDomain> process state.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ac7ad-129">출력</span><span class="sxs-lookup"><span data-stu-id="ac7ad-129">Output</span></span>  
 <span data-ttu-id="ac7ad-130">이 MDA의 샘플 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7ad-130">The following is sample output from this MDA.</span></span>  
  
 `Method 'MethodWithCer', while executing within a constrained execution region, makes a call at IL offset 0x000C to 'MethodWithWeakContract', which does not have a sufficiently strong reliability contract and might cause non-deterministic results.`  
  
## <a name="configuration"></a><span data-ttu-id="ac7ad-131">구성</span><span class="sxs-lookup"><span data-stu-id="ac7ad-131">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac7ad-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac7ad-132">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>  
 <xref:System.Runtime.ConstrainedExecution>  
 [<span data-ttu-id="ac7ad-133">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="ac7ad-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
