---
title: invalidFunctionPointerInDelegate MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- invalidFunctionPointerInDelegate MDA
- managed debugging assistants (MDAs), invalid function pointer to delegates
- MDAs (managed debugging assistants), invalid function pointer to delegates
- function pointers, invalid
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- invalid function pointers
ms.assetid: 99ae44f1-783e-49a9-9009-24f54bbd0f09
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9bfd63890369d51fb42871e06807483b6e713d81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="8e9ad-102">invalidFunctionPointerInDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="8e9ad-102">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="8e9ad-103">`invalidFunctionPointerInDelegate` MDA(관리 디버깅 도우미)는 잘못된 함수 포인터가 네이티브 함수 포인터를 통해 대리자를 생성하도록 전달되면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e9ad-103">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8e9ad-104">증상</span><span class="sxs-lookup"><span data-stu-id="8e9ad-104">Symptoms</span></span>  
 <span data-ttu-id="8e9ad-105">함수 포인터를 통해 대리자를 사용할 때 액세스 위반 또는 예기치 않은 메모리 손상이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8e9ad-105">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8e9ad-106">원인</span><span class="sxs-lookup"><span data-stu-id="8e9ad-106">Cause</span></span>  
 <span data-ttu-id="8e9ad-107">잘못된 함수 포인터가 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8e9ad-107">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8e9ad-108">해결 방법</span><span class="sxs-lookup"><span data-stu-id="8e9ad-108">Resolution</span></span>  
 <span data-ttu-id="8e9ad-109">유효한 함수 포인터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e9ad-109">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8e9ad-110">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="8e9ad-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="8e9ad-111">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e9ad-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8e9ad-112">출력</span><span class="sxs-lookup"><span data-stu-id="8e9ad-112">Output</span></span>  
 <span data-ttu-id="8e9ad-113">잘못된 함수 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8e9ad-113">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="8e9ad-114">구성</span><span class="sxs-lookup"><span data-stu-id="8e9ad-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e9ad-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e9ad-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="8e9ad-116">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="8e9ad-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="8e9ad-117">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="8e9ad-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
