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
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 122058b7e826e27fe6c60c5b07610f7c63e64f78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="interlocked-operations"></a>연동 작업
<xref:System.Threading.Interlocked> 클래스는 다중 스레드에서 공유 하는 변수에 대 한 액세스를 동기화 하는 메서드를 제공 합니다. 서로 다른 프로세스의 스레드는 변수가 공유 메모리에 있는 경우 이 메커니즘을 사용할 수 있습니다. 연동 작업은 원자성입니다. 즉, 전체 작업은 동일한 변수의 다른 연동 작업에 의해 중단될 수 없는 장치입니다. 이는 메모리 주소에서 값을 로드한 후 이를 변경하고 저장할 기회를 갖기 전에 스레드를 일시 중단할 수 있는 선점형 다중 스레딩과 함께 운영 체제에서 중요합니다.  
  
 <xref:System.Threading.Interlocked> 클래스는 다음 작업을 제공 합니다.  
  
-   .NET Framework 버전 2.0에에서는 <xref:System.Threading.Interlocked.Add%2A> 메서드 변수에 정수 값을 추가 하 고 변수의 새 값을 반환 합니다.  
  
-   .NET Framework 버전 2.0에에서는 <xref:System.Threading.Interlocked.Read%2A> 메서드 원자 단위 연산으로 64 비트 정수 값을 읽습니다. 이는 64비트 정수 읽기가 일반적인 원자성 작업이 아닌 32비트 운영 체제에서 유용합니다.  
  
-   <xref:System.Threading.Interlocked.Increment%2A> 및 <xref:System.Threading.Interlocked.Decrement%2A> 메서드 증가 또는 감소 변수 및 결과 값을 반환 합니다.  
  
-   <xref:System.Threading.Interlocked.Exchange%2A> 메서드는 지정 된 변수를 해당 값을 반환 하 고 새 값으로 바꿀 원자 값의 교환을 수행 합니다. .NET Framework 버전 2.0에서 이 메서드의 제네릭 오버로드는 모든 참조 형식의 변수에서 이 교환을 수행하는 데 사용할 수 있습니다. <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>을 참조하세요.  
  
-   <xref:System.Threading.Interlocked.CompareExchange%2A> 메서드도 두 개의 교환 설정 비교의 결과에 따라 하지만 값입니다. .NET Framework 버전 2.0에서 이 메서드의 제네릭 오버로드는 모든 참조 형식의 변수에서 이 교환을 수행하는 데 사용할 수 있습니다. <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>을 참조하세요.  
  
 최신 프로세서에서는의 메서드는 <xref:System.Threading.Interlocked> 클래스 단일 명령으로 종종 구현할 수 있습니다. 따라서 고성능 동기화를 제공하며 스핀 잠금과 같은 더 높은 수준의 동기화 메커니즘을 빌드하는 데 사용될 수 있습니다.  
  
 사용 하는 예제에 대 한는 <xref:System.Threading.Monitor> 및 <xref:System.Threading.Interlocked> 조합에서 클래스 참조 [모니터](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)합니다.  
  
## <a name="compareexchange-example"></a>CompareExchange 예제  
 <xref:System.Threading.Interlocked.CompareExchange%2A> 간단한 증가 및 감소 보다 좀 더 복잡 한 계산을 보호 하기 위해 메서드를 사용할 수 있습니다. 다음 예제에서는 부동 소수점 숫자로 저장되는 누계에 추가하는 스레드로부터 안전한 메서드를 보여 줍니다. (정수에 대 한는 <xref:System.Threading.Interlocked.Add%2A> 메서드는 보다 간단한 솔루션입니다.) 전체 코드 예제를 보려면 오버 로드 <xref:System.Threading.Interlocked.CompareExchange%2A> 단 정밀도 및 배정밀도 부동 소수점 인수를 사용 하는 (<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> 및 <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>).  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## <a name="untyped-overloads-of-exchange-and-compareexchange"></a>형식화되지 않은 Exchange 및 CompareExchange의 오버로드  
 <xref:System.Threading.Interlocked.Exchange%2A> 및 <xref:System.Threading.Interlocked.CompareExchange%2A> 메서드는 형식의 인수를 사용 하는 오버 로드를 갖고 <xref:System.Object>합니다. 이러한 각 오버이 로드의 첫 번째 인수는 `ref Object` (`ByRef … As Object` Visual basic에서), 형식 안전성 요구로 엄격 하 게 입력 하려면이 인수에 전달 된 변수 및 <xref:System.Object>; 입력의 첫 번째 인수를 간단 하 게 캐스팅할 수 없습니다 <xref:System.Object> 이러한 메서드를 호출할 때입니다.  
  
> [!NOTE]
>  .NET Framework 버전 2.0에서에서 제네릭 오버 로드를 사용 하 여는 <xref:System.Threading.Interlocked.Exchange%2A> 및 <xref:System.Threading.Interlocked.CompareExchange%2A> 강력 하 게 교환 하는 메서드를 형식화 된 변수입니다.  
  
 다음 코드 예제에서는 .NET Framework 버전 1.0 또는 1.1에서 구현될 수 있는 것처럼 한 번만 설정될 수 있는 `ClassA` 형식의 속성을 보여 줍니다.  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Interlocked>  
 <xref:System.Threading.Monitor>  
 [스레딩](../../../docs/standard/threading/index.md)  
 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md)
