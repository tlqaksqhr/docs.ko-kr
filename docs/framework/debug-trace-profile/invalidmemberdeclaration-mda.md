---
title: invalidMemberDeclaration MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d4f625cbc7d7c46eee5b2eb8d7e47d4a5754fc26
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="c8e4c-102">invalidMemberDeclaration MDA</span><span class="sxs-lookup"><span data-stu-id="c8e4c-102">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="c8e4c-103">`invalidMemberDeclaration` MDA(관리 디버깅 도우미)는 COM에서 호출할 멤버의 매개 변수를 마샬링하는 방법을 결정하는 동안 발생 하는 오류를 보고하기 위해 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8e4c-103">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="c8e4c-104">증상</span><span class="sxs-lookup"><span data-stu-id="c8e4c-104">Symptoms</span></span>  
 <span data-ttu-id="c8e4c-105">호출된 관리되는 메서드 없이 실패 HRESULT가 COM에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8e4c-105">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="c8e4c-106">원인</span><span class="sxs-lookup"><span data-stu-id="c8e4c-106">Cause</span></span>  
 <span data-ttu-id="c8e4c-107">이는 매개 변수 중 하나의 호환되지 않는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성 때문일 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="c8e4c-107">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="c8e4c-108">해결</span><span class="sxs-lookup"><span data-stu-id="c8e4c-108">Resolution</span></span>  
 <span data-ttu-id="c8e4c-109">매개 변수에서 유효한 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e4c-109">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="c8e4c-110">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="c8e4c-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="c8e4c-111">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e4c-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="c8e4c-112">출력</span><span class="sxs-lookup"><span data-stu-id="c8e4c-112">Output</span></span>  
 <span data-ttu-id="c8e4c-113">멤버 이름, 형식 이름 및 오류 메시지를 포함하는 정보 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="c8e4c-113">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="c8e4c-114">구성</span><span class="sxs-lookup"><span data-stu-id="c8e4c-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8e4c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8e4c-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="c8e4c-116">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="c8e4c-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="c8e4c-117">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="c8e4c-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
