---
title: '방법: 간단한 Parallel.ForEach 루프 작성'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e3fb5fd807971aed014ba98cbb207c4483b93f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a>방법: 간단한 Parallel.ForEach 루프 작성
이 예제는 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 루프를 사용하여 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 데이터 소스에 대해 데이터 병렬 처리를 사용하는 방법을 보여줍니다.  
  
> [!NOTE]
>  이 문서에서는 람다 식을 사용하여 PLINQ에 대리자를 정의합니다. C# 또는 Visual Basic의 람다 식을 잘 모르는 경우 [PLINQ 및 TPL의 람다 식](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)을 참조하세요.  
  
## <a name="example"></a>예  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 루프는 <xref:System.Threading.Tasks.Parallel.For%2A> 루프처럼 작동합니다. 소스 컬렉션은 파티셔닝되고 작업은 시스템 환경을 기반으로 여러 스레드에서 예약됩니다. 시스템에 프로세서가 많을수록 병렬 메서드가 더 빠르게 실행됩니다. 일부 소스 컬렉션의 경우, 소스의 크기 및 수행되는 작업의 종류에 따라 순차 루프가 더 빠를 수 있습니다. 성능에 대한 자세한 내용은 [데이터 및 작업 병렬 처리에서 발생할 수 있는 문제](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)를 참조하세요.  
  
 병렬 루프에 대한 자세한 내용은 [방법: 간단한 Parallel.For 루프 작성](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md)을 참조하세요.  
  
 제네릭이 아닌 컬렉션에 <xref:System.Threading.Tasks.Parallel.ForEach%2A>를 사용하려면 다음 예제와 같이 <xref:System.Linq.Enumerable.Cast%2A> 확장 메서드를 사용하여 컬렉션을 일반 컬렉션으로 변환할 수 있습니다.  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 병렬 LINQ(PLINQ)를 사용하여 <xref:System.Collections.Generic.IEnumerable%601> 데이터 소스의 처리를 병렬 처리할 수도 있습니다. PLINQ를 통해 선언 쿼리 구문을 사용하여 루프 동작을 표현할 수 있습니다. 자세한 내용은 [PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)를 참조하세요.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   이 코드를 복사하여 Visual Studio 2010 콘솔 응용 프로그램 프로젝트에 붙여넣습니다.  
  
-   System.Drawing.dll에 참조를 추가합니다.  
  
-   F5 키를 누릅니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 병렬 처리](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [병렬 프로그래밍](../../../docs/standard/parallel-programming/index.md)  
 [PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
