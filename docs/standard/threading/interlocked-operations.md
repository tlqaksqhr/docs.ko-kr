---
title: "연동 작업"
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
- cpp
helpviewer_keywords:
- Interlocked class, about Interlocked class
- threading [.NET Framework], Interlocked class
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c10c1188820b7a270baa0c51696974f93a8a2990
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="interlocked-operations"></a>연동 작업
<xref:System.Threading.Interlocked> 클래스는 여러 스레드에서 공유하는 변수에 대한 액세스를 동기화하는 메서드를 제공합니다. 서로 다른 프로세스의 스레드는 변수가 공유 메모리에 있는 경우 이 메커니즘을 사용할 수 있습니다. 연동 작업은 원자성입니다. 즉, 전체 작업은 동일한 변수의 다른 연동 작업에 의해 중단될 수 없는 장치입니다. 이는 메모리 주소에서 값을 로드한 후 이를 변경하고 저장할 기회를 갖기 전에 스레드를 일시 중단할 수 있는 선점형 다중 스레딩과 함께 운영 체제에서 중요합니다.  
  
 <xref:System.Threading.Interlocked> 클래스는 다음과 같은 작업을 제공합니다.  
  
-   .NET Framework 버전 2.0에서 <xref:System.Threading.Interlocked.Add%2A> 메서드는 변수에 정수 값을 추가하고 변수의 새 값을 반환합니다.  
  
-   .NET Framework 버전 2.0에서 <xref:System.Threading.Interlocked.Read%2A> 메서드는 64비트 정수 값을 원자성 작업으로 읽습니다. 이는 64비트 정수 읽기가 일반적인 원자성 작업이 아닌 32비트 운영 체제에서 유용합니다.  
  
-   <xref:System.Threading.Interlocked.Increment%2A> 및 <xref:System.Threading.Interlocked.Decrement%2A> 메서드는 변수를 증가하거나 감소하고 결과 값을 반환합니다.  
  
-   <xref:System.Threading.Interlocked.Exchange%2A> 메서드는 지정된 변수의 값에 대한 원자성 교환을 수행하고 해당 값을 반환하여 새 값으로 바꿉니다. .NET Framework 버전 2.0에서 이 메서드의 제네릭 오버로드는 모든 참조 형식의 변수에서 이 교환을 수행하는 데 사용할 수 있습니다. <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>을 참조하세요.  
  
-   <xref:System.Threading.Interlocked.CompareExchange%2A> 메서드도 두 값을 교환하지만 비교 결과에 대해 불확정합니다. .NET Framework 버전 2.0에서 이 메서드의 제네릭 오버로드는 모든 참조 형식의 변수에서 이 교환을 수행하는 데 사용할 수 있습니다. <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>을 참조하세요.  
  
 최신 프로세서에서 <xref:System.Threading.Interlocked> 클래스의 메서드는 일반적으로 단일 명령으로 구현될 수 있습니다. 따라서 고성능 동기화를 제공하며 스핀 잠금과 같은 더 높은 수준의 동기화 메커니즘을 빌드하는 데 사용될 수 있습니다.  
  
 조합에서 <xref:System.Threading.Monitor> 및 <xref:System.Threading.Interlocked> 클래스를 사용하는 예제는 [Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)를 참조하세요.  
  
## <a name="compareexchange-example"></a>CompareExchange 예제  
 <xref:System.Threading.Interlocked.CompareExchange%2A> 메서드를 사용하여 단순 증가 및 감소보다 복잡한 계산을 보호할 수 있습니다. 다음 예제에서는 부동 소수점 숫자로 저장되는 누계에 추가하는 스레드로부터 안전한 메서드를 보여줍니다. (정수의 경우 <xref:System.Threading.Interlocked.Add%2A> 메서드는 더욱 간단한 솔루션입니다. ) 전체 코드 예제는 단정밀도 및 배정밀도 부동 소수점 인수(<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> 및 <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>)를 사용하는 <xref:System.Threading.Interlocked.CompareExchange%2A>의 오버로드를 참조하세요.  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## <a name="untyped-overloads-of-exchange-and-compareexchange"></a>형식화되지 않은 Exchange 및 CompareExchange의 오버로드  
 <xref:System.Threading.Interlocked.Exchange%2A> 및 <xref:System.Threading.Interlocked.CompareExchange%2A> 메서드에는 <xref:System.Object> 형식의 인수를 사용하는 오버로드가 있습니다. 이러한 각 오버로드의 첫 번째 인수는 `ref Object`(Visual Basic의 경우 `ByRef … As Object`)이며 형식 안전성을 위해서는 이 인수로 전달되는 변수를 <xref:System.Object>로 엄격하게 형식을 지정해야 합니다. 이러한 메서드를 호출할 때 <xref:System.Object> 형식으로 첫 번째 인수를 간단하게 캐스트할 수 없습니다.  
  
> [!NOTE]
>  .NET Framework 버전 2.0에서 <xref:System.Threading.Interlocked.Exchange%2A> 및 <xref:System.Threading.Interlocked.CompareExchange%2A> 메서드의 일반 오버로드를 사용하여 강력한 형식의 변수를 교환합니다.  
  
 다음 코드 예제에서는 .NET Framework 버전 1.0 또는 1.1에서 구현될 수 있는 것처럼 한 번만 설정될 수 있는 `ClassA` 형식의 속성을 보여줍니다.  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Interlocked>  
 <xref:System.Threading.Monitor>  
 [스레딩](../../../docs/standard/threading/index.md)  
 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md)
