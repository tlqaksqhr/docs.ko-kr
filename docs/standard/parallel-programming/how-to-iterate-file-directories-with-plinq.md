---
title: "How to: Iterate File Directories with PLINQ | Microsoft Docs"
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
  - "PLINQ queries, how to iterate directories"
ms.assetid: 354e8ce3-35c4-431c-99ca-7661d1f3901b
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Iterate File Directories with PLINQ
이 예제에서는 파일 디렉터리에 대해 작업을 병렬화하는 간단한 두 가지 방법을 보여 줍니다.  첫 번째 쿼리에서는 <xref:System.IO.Directory.GetFiles%2A> 메서드를 사용하여 디렉터리 및 모든 하위 디렉터리에 있는 파일 이름 배열을 채웁니다.  이 메서드는 전체 배열이 채워질 때까지 반환하지 않으므로 작업의 시작 부분에서 지연이 발생할 수 있습니다.  그러나 배열이 채워진 후 PLINQ는 아주 빨리 작업을 병렬로 처리할 수 있습니다.  
  
 두 번째 쿼리에서는 바로 결과를 반환하기 시작하는 정적 <xref:System.IO.Directory.EnumerateDirectories%2A> 및 <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> 메서드를 사용합니다.  이 방법은 처리 시간을 첫 번째 예제와 비교해 볼 때 여러 요인에 따라 달라질 수 있지만 큰 디렉터리 트리에 대해 반복하는 경우 첫 번째 예제보다 더 빠를 수 있습니다.  
  
> [!WARNING]
>  이 예제들은 사용법을 보여 주기 위한 것이며, 이에 상응하는 순차 LINQ to Objects 쿼리보다 실행 속도가 느릴 수 있습니다.  속도 향상에 대한 자세한 내용은 [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 트리의 모든 디렉터리에 대한 액세스 권한이 있고 파일 크기가 아주 크지 않고 액세스 시간이 길지 않은 간단한 시나리오에서 파일 디렉터리에 대해 반복하는 방법을 보여 줍니다.  이 방법을 사용할 경우 파일 이름 배열이 생성되고 있는 동안 시작 부분에서 지연 시간이 발생합니다.  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## 예제  
 다음 예제에서는 트리의 모든 디렉터리에 대한 액세스 권한이 있고 파일 크기가 아주 크지 않고 액세스 시간이 길지 않은 간단한 시나리오에서 파일 디렉터리에 대해 반복하는 방법을 보여 줍니다.  이 방법을 사용하면 이전 예제보다 빨리 결과기 생성되기 시작합니다.  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 <xref:System.IO.Directory.GetFiles%2A>를 사용할 때 트리의 모든 디렉터리에 대한 충분한 권한이 있어야 합니다.  그렇지 않으면 예외가 throw되고 결과가 반환되지 않습니다.  PLINQ 쿼리에서 <xref:System.IO.Directory.EnumerateDirectories%2A>를 사용할 때 반복을 계속할 수 있도록 정상적인 방법으로 I\/O 예외를 처리하는 것이 문제가 될 수 있습니다.  코드를 통해 I\/O 또는 무단 액세스 예외를 처리해야 하는 경우 [방법: 병렬 클래스를 사용하여 파일 디렉터리 열거](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-the-parallel-class.md)에 설명된 방법을 고려해야 합니다.  
  
 예를 들어 I\/O 지연이 네트워크를 통한 파일 I\/O와 관련된 문제인 경우 [TPL and Traditional .NET Framework Asynchronous Programming](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) 및 이  [blog post](http://go.microsoft.com/fwlink/?LinkID=186458)에 설명된 비동기 I\/O 방법 중 하나를 사용해 보십시오.  
  
## 참고 항목  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)