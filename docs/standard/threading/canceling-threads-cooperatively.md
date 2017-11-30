---
title: "스레드 함께 취소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 482f48b347af1a4f76231abcb15abc2f4dba168b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="f275f-102">스레드 함께 취소</span><span class="sxs-lookup"><span data-stu-id="f275f-102">Canceling Threads Cooperatively</span></span>
<span data-ttu-id="f275f-103">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]이전에는 .NET Framework에서 시작된 스레드를 동시에 취소하는 기본 제공 방법이 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="f275f-103">Prior to the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="f275f-104">그러나 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], 취소를 사용할 수 있습니다 하는 것 처럼 스레드를 취소할 취소 토큰을 사용할 수 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 개체 또는 PLINQ 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f275f-104">However, in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use cancellation tokens to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="f275f-105">하지만 <xref:System.Threading.Thread?displayProperty=nameWithType> 클래스는 취소 토큰에 대 한 기본 제공 지원을 제공 하지 않으면, 사용 하 여 스레드 프로시저에는 토큰을 전달할 수 있습니다는 <xref:System.Threading.Thread> 사용 하는 생성자는 <xref:System.Threading.ParameterizedThreadStart> 위임 합니다.</span><span class="sxs-lookup"><span data-stu-id="f275f-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="f275f-106">다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f275f-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="f275f-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f275f-107">See Also</span></span>  
 [<span data-ttu-id="f275f-108">스레드 및 스레딩 사용</span><span class="sxs-lookup"><span data-stu-id="f275f-108">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
