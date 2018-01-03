---
title: invalidIUnknown MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ff88f8bc544c95a4fe5149cd517d9157d5ac23c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="b3e43-102">invalidIUnknown MDA</span><span class="sxs-lookup"><span data-stu-id="b3e43-102">invalidIUnknown MDA</span></span>
<span data-ttu-id="b3e43-103">`invalidIUnknown` MDA(관리 디버깅 도우미)는 잘못된 `IUnknown` 포인터가 네이티브 코드에서 관리 코드로 전달될 때 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3e43-103">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="b3e43-104">`IUnknown` 인터페이스에 대해 쿼리될 때 `IUnknown`에서 성공을 반환하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e43-104">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="b3e43-105">증상</span><span class="sxs-lookup"><span data-stu-id="b3e43-105">Symptoms</span></span>  
 <span data-ttu-id="b3e43-106">인수 마샬링 중 COM 인터페이스 포인터를 마샬링할 때 예기치 않은 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e43-106">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="b3e43-107">원인</span><span class="sxs-lookup"><span data-stu-id="b3e43-107">Cause</span></span>  
 <span data-ttu-id="b3e43-108">COM 인터페이스의 잘못된 `QueryInterface` 구현이 CLR에 전달되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e43-108">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="b3e43-109">해결</span><span class="sxs-lookup"><span data-stu-id="b3e43-109">Resolution</span></span>  
 <span data-ttu-id="b3e43-110">`QueryInterface` 구현을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e43-110">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="b3e43-111">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="b3e43-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="b3e43-112">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e43-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="b3e43-113">출력</span><span class="sxs-lookup"><span data-stu-id="b3e43-113">Output</span></span>  
 <span data-ttu-id="b3e43-114">오류에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e43-114">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="b3e43-115">구성</span><span class="sxs-lookup"><span data-stu-id="b3e43-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3e43-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3e43-116">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="b3e43-117">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="b3e43-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="b3e43-118">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="b3e43-118">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
