---
title: "스레드로부터 안전한 컬렉션 사용 시기 | Microsoft Docs"
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
  - "스레드로부터 안전한 컬렉션, 업그레이드 시기"
ms.assetid: a9babe97-e457-4ff3-b528-a1bc940d5320
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# 스레드로부터 안전한 컬렉션 사용 시기
[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]에는 다중 스레드에 의한 추가 및 제거 작업을 지원하도록 디자인된 새로운 컬렉션 형식 5개가 도입되어 있습니다.  스레드 보안을 달성하기 위해 이러한 새 형식에서는 다양한 유형의 효율적인 잠금 동기화 메커니즘 및 잠금 없는 동기화 메커니즘을 사용합니다.  동기화는 작업의 오버헤드를 증가시킵니다.  오버헤드의 양은 사용되는 동기화의 유형, 수행되는 작업의 유형 및 컬렉션에 동시에 액세스하려고 하는 스레드의 수 같은 기타 요인에 의해 달라집니다.  
  
 일부 시나리오에서 동기화 오버헤드는 무시할 만한 수준이며 동기화를 통해 다중 스레드 형식은 외부 잠금으로 보호되는 스레드로부터 안전하지 않은 형식보다 매우 빠르게 작동하고 훨씬 폭넓게 확장될 수 있습니다.  그러나 다른 시나리오에서는 오버헤드로 인해 스레드로부터 안전한 형식의 작동 및 확장 속도가 외부에서 잠긴 스레드로부터 안전하지 않은 버전의 형식과 동일하거나 낮을 수 있습니다.  
  
 다음 단원에서는 스레드로부터 안전한 컬렉션을 어느 경우에 사용하고 사용자 제공 잠금이 있는 스레드로부터 안전하지 않은 컬렉션을 어느 경우에 사용할지 설명하는 일반적 지침을 읽기 및 쓰기 작업을 중심으로 제공합니다.  성능은 여러 요인에 의해 달라질 수 있으므로 이 지침은 구체적이지 않으며 모든 상황에서 항상 올바른 것은 아닙니다.  성능이 가장 중요한 고려 사항인 경우에는 대표적인 컴퓨터 구성 및 부하를 기반으로 성능을 측정하여 사용할 컬렉션 형식을 결정하는 것이 가장 좋은 방법입니다.  이 문서에서 사용되는 용어의 의미는 다음과 같습니다.  
  
 *순수 생산자\-소비자 시나리오*  
 지정된 모든 스레드가 요소를 추가하거나 제거하지만 추가와 제거를 함께 수행하지는 않습니다.  
  
 *혼합된 생산자\-소비자 시나리오*  
 지정된 모든 스레드가 요소를 추가 및 제거합니다.  
  
 *속도 향상*  
 동일한 시나리오에서 다른 형식보다 속도가 빠른 알고리즘 성능입니다.  
  
 *확장성*  
 컴퓨터의 코어 수에 비례하는 성능상의 증가를 의미합니다.  확장하는 알고리즘은 2개의 코어보다 8개의 코어에서 더 빠르게 수행됩니다.  
  
## ConcurrentQueue\(T\) vs. Queue\(T\)  
 명령의 수가 적지 않아 각 요소에 대한 처리 시간이 매우 짧은 순수 생산자\-소비자 시나리오에서는 외부 잠금이 있는 <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>에 비해 <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>이 성능상 약간의 이점을 제공할 수 있습니다.  이 시나리오에서는 하나의 전용 스레드가 큐를 채우고 다른 전용 스레드가 큐를 비우는 경우에 <xref:System.Collections.Concurrent.ConcurrentQueue%601>이 최상의 성능을 발휘한다는 규칙이 성립합니다.  이 규칙을 적용하지 않으면 <xref:System.Collections.Generic.Queue%601>은 여러 코어가 있는 컴퓨터에서도 <xref:System.Collections.Concurrent.ConcurrentQueue%601>보다 약간 빠르게 작동할 수 있습니다.  
  
 처리 시간이 500FLOPS\(부동 소수점 연산\) 이상일 경우 두 스레드에 관한 이 규칙이 <xref:System.Collections.Concurrent.ConcurrentQueue%601>에 적용되지 않으므로 매우 우수한 확장성을 갖게 됩니다.  이 시나리오에서 <xref:System.Collections.Generic.Queue%601>의 확장성은 높지 않습니다.  
  
 혼합된 생산자\-소비자 시나리오의 경우 처리 시간이 매우 짧으면 외부 잠금이 있는 <xref:System.Collections.Generic.Queue%601>의 확장성은 <xref:System.Collections.Concurrent.ConcurrentQueue%601>보다 우수합니다.  그러나 처리 시간이 500FLOPS 이상일 경우에는 <xref:System.Collections.Concurrent.ConcurrentQueue%601>의 확장성이 더 낫습니다.  
  
## ConcurrentStack vs. Stack  
 순수 생산자\-소비자 시나리오에서 처리 시간이 매우 짧은 경우 외부 잠금이 있는 <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName> 및 <xref:System.Collections.Generic.Stack%601?displayProperty=fullName>은 푸시하는 하나의 전용 스레드와 팝하는 다른 전용 스레드 모두에 대해 거의 동일한 성능을 제공하게 됩니다.  그러나 스레드 수가 증가하면 경합이 늘어나면서 두 형식 모두 속도가 저하되고 <xref:System.Collections.Generic.Stack%601>의 성능이 <xref:System.Collections.Concurrent.ConcurrentStack%601>보다 뛰어날 수도 있습니다.  처리 시간이 500FLOPS 이상일 경우 두 형식은 거의 동일한 속도로 확장됩니다.  
  
 혼합된 생산자\-소비자 시나리오에서는 작업 부하의 크기와 상관없이 <xref:System.Collections.Concurrent.ConcurrentStack%601>의 속도가 더 빠릅니다.  
  
 <xref:System.Collections.Concurrent.ConcurrentStack%601.PushRange%2A>와 <xref:System.Collections.Concurrent.ConcurrentStack%601.TryPopRange%2A> 를 함께 사용할 경우 액세스 시간을 크게 단축할 수 있습니다.  
  
## ConcurrentDictionary vs. Dictionary  
 여러 스레드를 통해 키 또는 값을 동시에 추가 및 업데이트하는 모든 시나리오에서는 일반적으로 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>를 사용합니다.  자주 업데이트되고 읽기 횟수가 비교적 적은 시나리오에서 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>는 일반적으로 어느 정도의 이점을 제공합니다.  읽기 및 업데이트가 자주 수행되는 시나리오의 경우 컴퓨터에서 코어 수에 상관없이 일반적으로 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>가 훨씬 빠른 속도를 제공합니다.  
  
 업데이트가 자주 수행되는 시나리오의 경우에는 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>에서 동시성 수준을 높인 다음 측정을 통해 더 많은 코어가 있는 컴퓨터에서 성능의 증가 여부를 확인할 수 있습니다.  동시성 수준을 변경할 경우 전역적으로 영향을 미치는 작업은 가능한 한 피하는 것이 좋습니다.  
  
 <xref:System.Collections.Generic.Dictionary%602>가 어느 스레드에 의해서도 수정되지 않으면 동기화는 필요하지 않으므로 키 또는 값을 읽기만 하는 경우에는 이 사전이 더 빠릅니다.  
  
## ConcurrentBag  
 순수 생산자\-소비자 시나리오에서 <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName>은 다른 동시 컬렉션 형식보다 느리게 작동할 수 있습니다.  
  
 그러나 혼합된 생산자\-소비자 시나리오에서는 일반적으로 <xref:System.Collections.Concurrent.ConcurrentBag%601>이 작업 부하의 크기와 상관없이 다른 동시 컬렉션 형식보다 속도 및 확장성에서 훨씬 뛰어납니다.  
  
## BlockingCollection  
 경계 및 차단 구문을 사용해야 하는 경우 <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>은 어떠한 사용자 지정 구현보다도 빠르게 작동할 수 있습니다.  또한 취소, 열거 및 예외 처리를 다양하게 지원합니다.  
  
## 참고 항목  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [스레드로부터 안전한 컬렉션](../../../../docs/standard/collections/thread-safe/index.md)   
 [Parallel Programming](../../../../docs/standard/parallel-programming/index.md)