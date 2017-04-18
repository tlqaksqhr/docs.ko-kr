---
title: "How to: Write a Simple Parallel.ForEach Loop | Microsoft Docs"
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
  - "foreach, parallel version"
  - "parallel programming, foreach"
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# How to: Write a Simple Parallel.ForEach Loop
이 예제에서는 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> 루프를 사용하여 <xref:System.Collections.IEnumerable?displayProperty=fullName> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 데이터 소스에 대한 데이터 병렬 처리가 가능하게 하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 문서에서는 람다 식을 사용하여 PLINQ에 대리자를 정의합니다.  C\# 또는 Visual Basic의 람다 식에 익숙하지 않으면 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)을 참조하십시오.  
  
## 예제  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 루프는 <xref:System.Threading.Tasks.Parallel.For%2A> 루프와 비슷하게 작동합니다.  즉, 소스 컬렉션이 분할되고 시스템 환경에 따라 작업이 여러 스레드에 예약됩니다.  시스템의 프로세서가 많을수록 병렬 메서드의 실행 속도가 빨라집니다.  소스 크기와 수행되는 작업의 종류에 따라 일부 소스 컬렉션의 경우에는 순차 루프가 더 빠를 수도 있습니다.  성능에 대한 자세한 내용은 [Potential Pitfalls in Data and Task Parallelism](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)를 참조하십시오.  
  
 병렬 루프에 대한 자세한 내용은 [How to: Write a Simple Parallel.For Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md)을 참조하십시오.  
  
 제네릭이 아닌 컬렉션과 함께 <xref:System.Threading.Tasks.Parallel.ForEach%2A>를 사용하려면 다음 예제와 같이 <xref:System.Linq.Enumerable.Cast%2A> 확장 메서드를 사용하여 컬렉션을 제네릭 컬렉션으로 변환하면 됩니다.  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 PLINQ\(병렬 LINQ\)를 사용하여 <xref:System.Collections.Generic.IEnumerable%601> 데이터 소스의 처리를 병렬화할 수도 있습니다.  PLINQ를 사용할 경우 선언적 쿼리 구문을 사용하여 루프 동작을 표현할 수 있습니다.  자세한 내용은 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)을 참조하십시오.  
  
## 코드 컴파일  
  
-   이 코드를 복사하여 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 2010 콘솔 응용 프로그램 프로젝트에 붙여넣습니다.  
  
-   System.Drawing.dll에 대한 참조를 추가합니다.  
  
-   F5 키를 누릅니다.  
  
## 참고 항목  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)   
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)