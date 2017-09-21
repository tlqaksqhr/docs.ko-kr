---
title: "방법: ConcurrentBag을 사용하여 개체 풀 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
caps.latest.revision: 5
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3e26e5954c886d52debbf3e2d41260767b94dc74
ms.contentlocale: ko-kr
ms.lasthandoff: 09/19/2017

---
# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a>방법: ConcurrentBag을 사용하여 개체 풀 만들기
이 예제에서는 CurrentBag을 사용하여 개체 풀을 구현하는 방법을 보여 줍니다. 클래스에 여러 인스턴스가 필요하고 클래스를 만들거나 삭제하는 데 비용이 많이 드는 경우 개체 풀을 사용하면 응용 프로그램 성능을 향상시킬 수 있습니다. 클라이언트 프로그램에서 새 개체를 요청하면 먼저 개체 풀이 이미 풀에 만들어져 반환된 개체를 제공하려고 시도합니다. 제공될 개체가 없는 경우에만 새 개체가 만들어집니다.  
  
 <xref:System.Collections.Concurrent.ConcurrentBag%601>는 특히 한 스레드에서 항목의 추가와 제거를 모두 수행할 때 추가하고 제거하는 속도가 빠르기 때문에 개체를 저장하는 데 사용됩니다. <xref:System.Collections.Concurrent.ConcurrentQueue%601> 및 <xref:System.Collections.Concurrent.ConcurrentStack%601>와 같이 모음 데이터 구조가 구현하는 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>를 중심으로 구축되도록 이 예제를 강화할 수 있습니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## <a name="see-also"></a>참고 항목  
 [스레드로부터 안전한 컬렉션](../../../../docs/standard/collections/thread-safe/index.md)

