---
title: pInvokeLog MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9c4842d838fd5b4fee29187f118c784c55e0eb13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="9d157-102">pInvokeLog MDA</span><span class="sxs-lookup"><span data-stu-id="9d157-102">pInvokeLog MDA</span></span>
<span data-ttu-id="9d157-103">`pInvokeLog` MDA(관리 디버깅 도우미)는 실행 중에 사용되는 고유한 각 플랫폼 호출을 위해 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d157-103">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="9d157-104">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="9d157-104">Effect on the Runtime</span></span>  
 <span data-ttu-id="9d157-105">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d157-105">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="9d157-106">출력</span><span class="sxs-lookup"><span data-stu-id="9d157-106">Output</span></span>  
 <span data-ttu-id="9d157-107">실행 중에 사용된 플랫폼 호출 시그니처를 나타내는 메시지.</span><span class="sxs-lookup"><span data-stu-id="9d157-107">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="9d157-108">구성</span><span class="sxs-lookup"><span data-stu-id="9d157-108">Configuration</span></span>  
 <span data-ttu-id="9d157-109">일치하는 각 요소는 플랫폼 호출을 수행하는 .dll 파일을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="9d157-109">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeLog>  
      <filter>  
        <match dllName="user32.dll"/>  
        <match dllName="kernel32.dll"/>  
      </filter>  
    </pInvokeLog>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d157-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d157-110">See Also</span></span>  
 [<span data-ttu-id="9d157-111">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="9d157-111">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="9d157-112">관리되지 않는 DLL 함수 사용</span><span class="sxs-lookup"><span data-stu-id="9d157-112">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
