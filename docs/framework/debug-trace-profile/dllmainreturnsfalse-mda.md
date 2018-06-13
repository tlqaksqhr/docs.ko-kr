---
title: dllMainReturnsFalse MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4987b025450f2207a01a472a0c39fc6da2de0782
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33386495"
---
# <a name="dllmainreturnsfalse-mda"></a><span data-ttu-id="96cac-102">dllMainReturnsFalse MDA</span><span class="sxs-lookup"><span data-stu-id="96cac-102">dllMainReturnsFalse MDA</span></span>
<span data-ttu-id="96cac-103">DLL_PROCESS_ATTACH로 인해 호출된 사용자 어셈블리의 관리되는 `DllMain` 함수가 FALSE를 반환하면 `dllMainReturnsFalse` MDA(관리 디버깅 도우미)가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="96cac-103">The `dllMainReturnsFalse` managed debugging assistant (MDA) is activated if the managed `DllMain` function of a user assembly, called with reason DLL_PROCESS_ATTACH, returns FALSE.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="96cac-104">증상</span><span class="sxs-lookup"><span data-stu-id="96cac-104">Symptoms</span></span>  
 <span data-ttu-id="96cac-105">`DllMain` 함수가 FALSE를 반환했고 이는 함수가 제대로 실행되지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="96cac-105">The `DllMain` function returned FALSE, indicating that it did not execute properly.</span></span> <span data-ttu-id="96cac-106">`DllMain` 함수에는 일반적으로 중요한 초기화 코드가 포함되므로 이로 인해 결정되지 않은 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96cac-106">This can cause undetermined issues because `DllMain` functions typically contain important initialization code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="96cac-107">원인</span><span class="sxs-lookup"><span data-stu-id="96cac-107">Cause</span></span>  
 <span data-ttu-id="96cac-108">로드 시 DLL 초기화에 대한 DLL_PROCESS_ATTACH로 인해 `DllMain` 함수가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="96cac-108">The `DllMain` function is called with reason DLL_PROCESS_ATTACH for DLL initialization upon load.</span></span> <span data-ttu-id="96cac-109">함수가 FALSE를 반환하면 DLL 초기화가 실패했음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="96cac-109">If it returns FALSE, it means that DLL initialization failed.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="96cac-110">해결</span><span class="sxs-lookup"><span data-stu-id="96cac-110">Resolution</span></span>  
 <span data-ttu-id="96cac-111">실패한 DLL의 `DllMain` 함수 코드를 분석하고 초기화 실패의 원인을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="96cac-111">Analyze the code of the `DllMain` function of the failed DLL and identify the cause of the initialization failure.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="96cac-112">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="96cac-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="96cac-113">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96cac-113">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="96cac-114">`DllMain`의 반환 값에 대한 데이터만 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="96cac-114">It only reports data about the return value for `DllMain`.</span></span>  
  
## <a name="output"></a><span data-ttu-id="96cac-115">출력</span><span class="sxs-lookup"><span data-stu-id="96cac-115">Output</span></span>  
 <span data-ttu-id="96cac-116">DLL_PROCESS_ATTACH로 인해 호출되는 `DllMain` 함수가 FALSE를 반환했음을 나타내는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="96cac-116">A message indicating that a `DllMain` function, called for reason DLL_PROCESS_ATTACH, returned FALSE.</span></span> <span data-ttu-id="96cac-117">이 MDA는 `DllMain`이 관리 코드에서 구현된 경우에만 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="96cac-117">Note that this MDA is activated only if `DllMain` is implemented in managed code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="96cac-118">구성</span><span class="sxs-lookup"><span data-stu-id="96cac-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="96cac-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96cac-119">See Also</span></span>  
 [<span data-ttu-id="96cac-120">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="96cac-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
