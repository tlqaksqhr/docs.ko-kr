---
title: failedQI MDA
ms.date: 03/30/2017
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60fd5c29f716aa55f35c520794fbc9a0f673b9f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33387174"
---
# <a name="failedqi-mda"></a><span data-ttu-id="1ec78-102">failedQI MDA</span><span class="sxs-lookup"><span data-stu-id="1ec78-102">failedQI MDA</span></span>
<span data-ttu-id="1ec78-103">`failedQI` MDA(관리 디버깅 도우미)는 런타임이 RCW(런타임 호출 가능 래퍼)를 대신하여 COM 인터페이스 포인터에서 `QueryInterface`를 호출할 때 활성화되며 `QueryInterface` 호출이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec78-103">The `failedQI` managed debugging assistant (MDA) is activated when the runtime calls `QueryInterface` on a COM interface pointer on behalf of a runtime callable wrapper (RCW), and the `QueryInterface` call fails.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="1ec78-104">증상</span><span class="sxs-lookup"><span data-stu-id="1ec78-104">Symptoms</span></span>  
 <span data-ttu-id="1ec78-105">RCW에 대한 캐스팅이 실패하거나 RCW에서의 COM 호출이 예기치 않게 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec78-105">A cast on an RCW fails, or a call to COM from an RCW fails unexpectedly.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="1ec78-106">원인</span><span class="sxs-lookup"><span data-stu-id="1ec78-106">Cause</span></span>  
  
-   <span data-ttu-id="1ec78-107">잘못된 컨텍스트에서 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec78-107">The call is made from the wrong context.</span></span>  
  
-   <span data-ttu-id="1ec78-108">잘못된 컨텍스트에서 호출이 시도되었기 때문에 등록된 프록시가 `QueryInterface` 호출에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec78-108">The registered proxy is failing the `QueryInterface` call because the call was attempted in the wrong context.</span></span>  
  
-   <span data-ttu-id="1ec78-109">OLE 소유 프록시에서 실패 HRESULT가 반환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1ec78-109">An OLE-owned proxy returned a failure HRESULT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="1ec78-110">해결</span><span class="sxs-lookup"><span data-stu-id="1ec78-110">Resolution</span></span>  
 <span data-ttu-id="1ec78-111">COM 규칙에 MSDN 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ec78-111">See the MSDN documentation on COM rules.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="1ec78-112">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="1ec78-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="1ec78-113">`QueryInterface` 호출이 실패하는 경우 컨텍스트가 전환되고 `QueryInterface` 호출이 다시 시도되어 잘못된 컨텍스트가 원인인지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1ec78-113">If a `QueryInterface` call fails, the context is switched and the `QueryInterface` call is attempted again to see if an incorrect context was at fault.</span></span>  
  
## <a name="output"></a><span data-ttu-id="1ec78-114">출력</span><span class="sxs-lookup"><span data-stu-id="1ec78-114">Output</span></span>  
 <span data-ttu-id="1ec78-115">인터페이스의 관리되는 이름, 인터페이스의 GUID 및 실패 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="1ec78-115">The managed name of the interface, the GUID of the interface, and the HRESULT of the failure.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="1ec78-116">구성</span><span class="sxs-lookup"><span data-stu-id="1ec78-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ec78-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ec78-117">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="1ec78-118">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="1ec78-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="1ec78-119">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="1ec78-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
