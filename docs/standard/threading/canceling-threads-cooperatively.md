---
title: 스레드 함께 취소
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3edd0f9c991df8d8d70b14f4439c5c477e8f1401
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581344"
---
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="27dd6-102">스레드 함께 취소</span><span class="sxs-lookup"><span data-stu-id="27dd6-102">Canceling Threads Cooperatively</span></span>
<span data-ttu-id="27dd6-103">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]이전에는 .NET Framework에서 시작된 스레드를 동시에 취소하는 기본 제공 방법이 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="27dd6-103">Prior to the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="27dd6-104">그러나 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서는 취소 토큰을 사용하여 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 개체 또는 PLINQ 쿼리를 취소할 수 있는 것처럼 스레드를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27dd6-104">However, in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use cancellation tokens to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="27dd6-105"><xref:System.Threading.Thread?displayProperty=nameWithType> 클래스는 취소 토큰에 대한 기본 제공 지원을 제공하지 않지만 <xref:System.Threading.Thread> 대리자를 받아들이는 <xref:System.Threading.ParameterizedThreadStart> 생성자를 사용하여 스레드 프로시저에 토큰을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27dd6-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="27dd6-106">다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="27dd6-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="27dd6-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27dd6-107">See Also</span></span>  
 [<span data-ttu-id="27dd6-108">스레드 및 스레딩 사용</span><span class="sxs-lookup"><span data-stu-id="27dd6-108">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
