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
# <a name="canceling-threads-cooperatively"></a>스레드 함께 취소
[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]이전에는 .NET Framework에서 시작된 스레드를 동시에 취소하는 기본 제공 방법이 없었습니다. 그러나 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], 취소를 사용할 수 있습니다 하는 것 처럼 스레드를 취소할 취소 토큰을 사용할 수 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 개체 또는 PLINQ 쿼리 합니다. 하지만 <xref:System.Threading.Thread?displayProperty=nameWithType> 클래스는 취소 토큰에 대 한 기본 제공 지원을 제공 하지 않으면, 사용 하 여 스레드 프로시저에는 토큰을 전달할 수 있습니다는 <xref:System.Threading.Thread> 사용 하는 생성자는 <xref:System.Threading.ParameterizedThreadStart> 위임 합니다. 다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>참고 항목  
 [스레드 및 스레딩 사용](../../../docs/standard/threading/using-threads-and-threading.md)
