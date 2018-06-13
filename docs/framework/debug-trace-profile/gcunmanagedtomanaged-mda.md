---
title: gcUnmanagedToManaged MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GC unmanaged to managed
- transitioning threads unmanaged to managed code
- GcUnmanagedToManaged MDA
- threading [.NET Framework], garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
- unmanaged to managed garbage collection
ms.assetid: 103eb3a3-1cf0-4406-8a9a-a7798fdc22d1
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dfaa77adef7cdc21b1ad8abaca1439361a33d4b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33386628"
---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="c6c72-102">gcUnmanagedToManaged MDA</span><span class="sxs-lookup"><span data-stu-id="c6c72-102">gcUnmanagedToManaged MDA</span></span>
<span data-ttu-id="c6c72-103">`gcUnmanagedToManaged` MDA(관리 디버깅 도우미)는 위협이 비관리 코드에서 관리 코드로 전환될 때마다 가비지 수집을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c6c72-103">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="c6c72-104">증상</span><span class="sxs-lookup"><span data-stu-id="c6c72-104">Symptoms</span></span>  
 <span data-ttu-id="c6c72-105">COM 및 플랫폼 호출을 사용하여 관리되지 않는 사용자 구성 요소를 실행하는 응용 프로그램은 CLR에서 비결정적 액세스 위반을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c6c72-105">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="c6c72-106">원인</span><span class="sxs-lookup"><span data-stu-id="c6c72-106">Cause</span></span>  
 <span data-ttu-id="c6c72-107">응용 프로그램이 관리되지 않는 사용자 구성 요소를 실행하는 경우 해당 구성 요소로 인해 가비지 수집된 힙이 손상되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c72-107">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="c6c72-108">이 경우 가비지 수집기가 개체 그래프를 검색하려고 하면 CLR에서 액세스 위반이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c72-108">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="c6c72-109">해결</span><span class="sxs-lookup"><span data-stu-id="c6c72-109">Resolution</span></span>  
 <span data-ttu-id="c6c72-110">이 도우미를 사용하도록 설정하면 관리되는 각 전환 전에 가비지 수집이 강제로 수행되어 관리되지 않는 구성 요소로 인해 가비지 수집된 힙이 손상되는 시간과 액세스 위반이 발생하는 시간 사이의 간격이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="c6c72-110">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="c6c72-111">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="c6c72-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="c6c72-112">위협이 비관리 코드에서 관리 코드로 전환될 때마다 가비지 수집을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c6c72-112">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="c6c72-113">출력</span><span class="sxs-lookup"><span data-stu-id="c6c72-113">Output</span></span>  
 <span data-ttu-id="c6c72-114">이 MDA는 출력을 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c72-114">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="c6c72-115">구성</span><span class="sxs-lookup"><span data-stu-id="c6c72-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6c72-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6c72-116">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="c6c72-117">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="c6c72-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="c6c72-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="c6c72-118">gcManagedToUnmanaged</span></span>](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)  
 [<span data-ttu-id="c6c72-119">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="c6c72-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
