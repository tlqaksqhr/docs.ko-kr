---
title: marshalCleanupError MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- cleanup operations
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- marshaling cleanup error
- MarshalCleanupError MDA
- memory, cleanup errors
ms.assetid: 2f5d9e7c-ae51-4155-a435-54347aa1f091
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c78fedaab26ff7f1da7bccd98c83a90e550d9014
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="marshalcleanuperror-mda"></a><span data-ttu-id="6a124-102">marshalCleanupError MDA</span><span class="sxs-lookup"><span data-stu-id="6a124-102">marshalCleanupError MDA</span></span>
<span data-ttu-id="6a124-103">`marshalCleanupError` MDA(관리 디버깅 도우미)는 네이티브 코드 경계와 관리 코드 경계 간에 데이터 형식을 마샬링하는 데 사용되는 임시 구조 및 메모리를 정리하려고 하는 동안 CLR(공용 언어 런타임)에 오류가 발생하면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a124-103">The `marshalCleanupError` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters an error while attempting to clean up temporary structures and memory used for marshaling data types between native and managed code boundaries.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="6a124-104">증상</span><span class="sxs-lookup"><span data-stu-id="6a124-104">Symptoms</span></span>  
 <span data-ttu-id="6a124-105">네이티브 및 관리 코드 변환을 수행할 때 메모리 누수가 발생하고 런타임 상태(예: 스레드 문화권)가 복원되지 않거나 <xref:System.Runtime.InteropServices.SafeHandle> 정리에서 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6a124-105">A memory leak occurs when making native and managed code transitions, runtime state such as thread culture is not restored, or errors occur in <xref:System.Runtime.InteropServices.SafeHandle> cleanup.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="6a124-106">원인</span><span class="sxs-lookup"><span data-stu-id="6a124-106">Cause</span></span>  
 <span data-ttu-id="6a124-107">임시 구조를 정리하는 동안 예기치 않은 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="6a124-107">An unexpected error occurred while cleaning up temporary structures.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="6a124-108">해결 방법</span><span class="sxs-lookup"><span data-stu-id="6a124-108">Resolution</span></span>  
 <span data-ttu-id="6a124-109">모든 <xref:System.Runtime.InteropServices.SafeHandle> 소멸자, 종료자 및 사용자 지정 마샬러 구현에 오류가 있는지 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="6a124-109">Review all <xref:System.Runtime.InteropServices.SafeHandle> destructor, finalizer, and custom marshaler implementations for errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="6a124-110">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="6a124-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="6a124-111">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a124-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="6a124-112">출력</span><span class="sxs-lookup"><span data-stu-id="6a124-112">Output</span></span>  
 <span data-ttu-id="6a124-113">정리 중에 실패한 작업을 보고하는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="6a124-113">A message reporting the operation that failed during cleanup.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="6a124-114">구성</span><span class="sxs-lookup"><span data-stu-id="6a124-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a124-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a124-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="6a124-116">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="6a124-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="6a124-117">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="6a124-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
