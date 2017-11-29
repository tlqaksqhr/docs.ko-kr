---
title: openGenericCERCall MDA
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
- open generic CER calls
- constrained execution regions
- openGenericCERCall MDA
- CER calls
- managed debugging assistants (MDAs), CER calls
- generics [.NET Framework], open generic CER calls
ms.assetid: da3e4ff3-2e67-4668-9720-fa776c97407e
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f82760eaeb051f2006a8baf11ac77c485d007758
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="opengenericcercall-mda"></a><span data-ttu-id="33afd-102">openGenericCERCall MDA</span><span class="sxs-lookup"><span data-stu-id="33afd-102">openGenericCERCall MDA</span></span>
<span data-ttu-id="33afd-103">루트 메서드에서 제네릭 형식 변수를 사용하는 제약이 있는 실행 지역(CER) 그래프가 JIT 컴파일 또는 네이티브 이미지 생성 시에 처리되며 제네릭 형식 변수 중 하나 이상의 개체 참조 형식임을 경고하기 위해 `openGenericCERCall` 관리 디버깅 도우미가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="33afd-103">The `openGenericCERCall` managed debugging assistant is activated to warn that a constrained execution region (CER) graph with generic type variables at the root method is being processed at JIT-compilation or native image generation time and at least one of the generic type variables is an object reference type.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="33afd-104">증상</span><span class="sxs-lookup"><span data-stu-id="33afd-104">Symptoms</span></span>  
 <span data-ttu-id="33afd-105">스레드가 중단되거나 응용 프로그램 도메인이 언로드되면 CER 코드가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33afd-105">CER code does not run when a thread is aborted or when an application domain is unloaded.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="33afd-106">원인</span><span class="sxs-lookup"><span data-stu-id="33afd-106">Cause</span></span>  
 <span data-ttu-id="33afd-107">결과적으로 생성되는 코드는 공유되며 각 개체 참조 형식 변수는 임의 개체 참조 형식일 수 있으므로 JIT 컴파일 시 개체 참조 형식을 포함하는 인스턴스는 대표일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="33afd-107">At JIT-compilation time, an instantiation containing an object reference type is only representative because the resultant code is shared, and each of the object reference type variables might be any object reference type.</span></span> <span data-ttu-id="33afd-108">따라서 런타임 리소스를 미리 준비하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33afd-108">This can prevent the preparation of some run-time resources ahead of time.</span></span>  
  
 <span data-ttu-id="33afd-109">특히 제네릭 형식 변수를 사용하는 메서드는 백그라운드에서 리소스 할당을 지연시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33afd-109">In particular, methods with generic type variables can lazily allocate resources in the background.</span></span> <span data-ttu-id="33afd-110">이러한 항목은 제네릭 사전 항목이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="33afd-110">These are referred to as generic dictionary entries.</span></span> <span data-ttu-id="33afd-111">예를 들어, `T`가 제네릭 형식 변수인 `List<T> list = new List<T>();` 문의 경우 런타임 시 인스턴스를 검색하고 정확하게 생성해야 할 수도 있습니다(예: `List<Object>, List<String>` 등).</span><span class="sxs-lookup"><span data-stu-id="33afd-111">For instance, for the statement `List<T> list = new List<T>();` where `T` is a generic type variable the runtime must look up and possibly create the exact instantiation at run time, for example, `List<Object>, List<String>`,and so forth.</span></span> <span data-ttu-id="33afd-112">메모리 부족과 같이 개발자가 제어할 수 없는 다양한 이유 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33afd-112">This can fail for a variety of reasons beyond the developer's control, such as running out of memory.</span></span>  
  
 <span data-ttu-id="33afd-113">이 MDA는 정확한 인스턴스가 있을 때가 아니라 JIT 컴파일 시에만 활성화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33afd-113">This MDA should only be activated at JIT-compilation time, not when there is an exact instantiation.</span></span>  
  
 <span data-ttu-id="33afd-114">이 MDA가 활성화되면 잘못된 인스턴스에 대해 CER이 작동하지 않는 증상이 발생할 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="33afd-114">When this MDA is activated, the likely symptoms are that CERs are not functional for the bad instantiations.</span></span> <span data-ttu-id="33afd-115">실제로 MDA를 활성화하게 한 환경에서 런타임 시 CER을 구현하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="33afd-115">In fact, the runtime has not attempted to implement a CER under the circumstances that caused the MDA to be activated.</span></span> <span data-ttu-id="33afd-116">따라서 개발자가 CER의 공유 인스턴스를 사용하는 경우, 의도된 CER 지역 내의 JIT 컴파일 오류, 제네릭 형식 로딩 오류 또는 스레드 중단이 발견되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33afd-116">So if the developer uses a shared instantiation of the CER, then JIT-compilation errors, generics type loading errors, or thread aborts within the region of the intended CER are not caught.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="33afd-117">해결</span><span class="sxs-lookup"><span data-stu-id="33afd-117">Resolution</span></span>  
 <span data-ttu-id="33afd-118">CER을 포함할 수 있는 메서드의 개체 참조 형식인 제네릭 형식 변수를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="33afd-118">Do not use generic type variables that are of object reference type for methods that may contain a CER.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="33afd-119">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="33afd-119">Effect on the Runtime</span></span>  
 <span data-ttu-id="33afd-120">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33afd-120">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="33afd-121">출력</span><span class="sxs-lookup"><span data-stu-id="33afd-121">Output</span></span>  
 <span data-ttu-id="33afd-122">다음은 이 MDA의 출력 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="33afd-122">The following is a sample of output from this MDA.</span></span>  
  
 `Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.`  
  
 `The caller must ensure this method is prepared explicitly at run time prior to execution.`  
  
 `method name="GenericMethodWithCer"`  
  
 `declaringType name="OpenGenericCERCall"`  
  
## <a name="configuration"></a><span data-ttu-id="33afd-123">구성</span><span class="sxs-lookup"><span data-stu-id="33afd-123">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <openGenericCERCall/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="33afd-124">예제</span><span class="sxs-lookup"><span data-stu-id="33afd-124">Example</span></span>  
 <span data-ttu-id="33afd-125">CER 코드가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33afd-125">The CER code is not executed.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Runtime.CompilerServices;  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        CallGenericMethods();  
    }  
    static void CallGenericMethods()  
    {  
        // This call is correct. The instantiation of the method  
        // contains only nonreference types.  
        MyClass.GenericMethodWithCer<int>();  
  
        // This call is incorrect. A shared version of the method that  
        // cannot be completely analyzed will be JIT-compiled. The   
        // MDA will be activated at JIT-compile time, not at run time.  
        MyClass.GenericMethodWithCer<String>();  
    }  
}  
  
    class MyClass  
{  
    public static void GenericMethodWithCer<T>()  
    {  
        RuntimeHelpers.PrepareConstrainedRegions();  
        try  
        {  
  
        }  
        finally  
        {  
            // This is the start of the CER.  
            Console.WriteLine("In finally block.");  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="33afd-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33afd-126">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>  
 <xref:System.Runtime.ConstrainedExecution>  
 [<span data-ttu-id="33afd-127">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="33afd-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
