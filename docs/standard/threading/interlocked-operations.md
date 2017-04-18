---
title: "Interlocked Operations | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Interlocked class, about Interlocked class"
  - "threading [.NET Framework], Interlocked class"
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Interlocked Operations
<xref:System.Threading.Interlocked> 클래스는 여러 스레드가 공유하는 변수에 대한 액세스를 동기화하는 메서드를 제공합니다.  변수가 공유 메모리에 있으면 다른 프로세스의 스레드도 이 메커니즘을 사용할 수 있습니다.  연동 작업은 원자성을 가집니다. 즉, 전체 작업은 동일한 변수를 공유하는 다른 연동 작업에 의해 중단될 수 없는 하나의 단위입니다.  이는 선점형 다중 스레딩을 제공하는 운영 체제에서 중요합니다. 이러한 운영 체제에서 스레드는 메모리 주소로부터 값을 로드한 후 이를 변경하여 저장하기 전에 일시 중단될 수 있습니다.  
  
 <xref:System.Threading.Interlocked> 클래스는 다음과 같은 작업을 제공합니다.  
  
-   .NET Framework 버전 2.0에서 <xref:System.Threading.Interlocked.Add%2A> 메서드는 정수 값을 변수에 추가하고 변수의 새 값을 반환합니다.  
  
-   .NET Framework 버전 2.0에서 <xref:System.Threading.Interlocked.Read%2A> 메서드는 64비트 정수 값을 원자 연산으로 읽습니다.  이는 32비트 운영 체제에서 유용하며 이 운영 체제에서 64비트 정수를 읽는 것은 일반적으로 원자 연산이 아닙니다.  
  
-   <xref:System.Threading.Interlocked.Increment%2A> 및 <xref:System.Threading.Interlocked.Decrement%2A> 메서드는 변수를 증가 또는 감소시킨 다음 결과 값을 반환합니다.  
  
-   <xref:System.Threading.Interlocked.Exchange%2A> 메서드는 값을 반환하고 이를 새 값으로 바꾸면서 지정된 변수에서 값의 원자 교환을 수행합니다.  .NET Framework 버전 2.0에서 이러한 메서드의 제네릭 오버로드는 참조 형식의 변수에서 이러한 교환을 수행하는 데 사용할 수 있습니다.  <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>를 참조하십시오.  
  
-   <xref:System.Threading.Interlocked.CompareExchange%2A> 메서드는 두 값을 교환하기도 하지만 비교 결과에 따라 달라집니다.  .NET Framework 버전 2.0에서 이러한 메서드의 제네릭 오버로드는 참조 형식의 변수에서 이러한 교환을 수행하는 데 사용할 수 있습니다.  <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>를 참조하십시오.  
  
 최신 프로세서에서는 <xref:System.Threading.Interlocked> 클래스의 메서드를 한 개의 명령으로 구현할 수도 있습니다.  따라서 이러한 메서드는 고성능 동기화를 제공하며 스핀 잠금과 같은 보다 높은 수준의 동기화 메커니즘을 빌드하는 데 사용할 수 있습니다.  
  
 <xref:System.Threading.Monitor> 및 <xref:System.Threading.Interlocked> 클래스를 함께 사용하는 예제를 보려면 [Monitor](../Topic/Monitors.md)를 참조하십시오.  
  
## CompareExchange 예제  
 <xref:System.Threading.Interlocked.CompareExchange%2A> 메서드를 사용하여 단순한 증가 및 감소보다 훨씬 더 복잡한 계산을 보호할 수 있습니다.  다음 예제에서는 부동 소수점 숫자로 저장되는 누계에 추가되는 스레드로부터 안전한 메서드를 보여 줍니다. 정수의 경우 <xref:System.Threading.Interlocked.Add%2A> 메서드가 더 간단한 솔루션입니다. 전체 코드 예제에 대해서는 단정밀도 및 배정밀도 부동 소수점 인수\(<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> 및 <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>\)를 갖는 <xref:System.Threading.Interlocked.CompareExchange%2A>의 오버로드를 참조하십시오.  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## Exchange 및 CompareExchange의 형식화되지 않은 오버로드  
 <xref:System.Threading.Interlocked.Exchange%2A> 및 <xref:System.Threading.Interlocked.CompareExchange%2A> 메서드에는 <xref:System.Object> 형식의 인수를 사용하는 오버로드가 있습니다.  이러한 각 오버로드의 첫 번째 인수는 `ref Object`\(Visual Basic에서는 `ByRef … As Object`\)이며 형식 안전성을 위해 이 인수로 전달되는 변수는 <xref:System.Object>로 강력하게 형식화되어야 합니다. 사용자는 이러한 메서드를 호출할 때 첫 번째 인수를 <xref:System.Object> 형식으로 간단하게 캐스팅할 수 없습니다.  
  
> [!NOTE]
>  .NET Framework 버전 2.0에서 <xref:System.Threading.Interlocked.Exchange%2A> 및 <xref:System.Threading.Interlocked.CompareExchange%2A> 메서드의 제네릭 오버로드를 사용하여 강력하게 형식화된 변수를 교환합니다.  
  
 다음 코드 예제에서는 .NET Framework 버전 1.0 또는 1.1에서 구현될 수 있는 것처럼 한 번만 설정될 수 있는 `ClassA` 형식의 속성을 보여 줍니다.  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## 참고 항목  
 <xref:System.Threading.Interlocked>   
 <xref:System.Threading.Monitor>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)