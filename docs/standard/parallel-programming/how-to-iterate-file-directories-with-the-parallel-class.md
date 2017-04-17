---
title: "방법: 병렬 클래스를 사용하여 파일 디렉터리 열거 | Microsoft Docs"
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
  - "병렬 루프, 디렉터리 반복 방법"
ms.assetid: 555e9f48-f53d-4774-9bcf-3e965c732ec5
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 병렬 클래스를 사용하여 파일 디렉터리 열거
대부분의 경우 파일 반복은 쉽게 병렬 처리할 수 있는 작업입니다.  [How to: Iterate File Directories with PLINQ](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md) 항목에서는 대부분의 일반 시나리오에서 이 작업을 가장 쉽게 수행할 수 있는 방법을 보여 줍니다.  그러나 코드에서 파일 시스템에 액세스할 때 발생할 수 있는 여러 종류의 예외를 처리해야 하는 경우 문제가 발생할 수 있습니다.  다음 예제에서는 문제를 해결할 수 있는 한 가지 방법을 보여 줍니다.  이 예제에서는 스택 기반 반복을 사용하여 지정된 디렉터리 아래의 모든 폴더와 파일을 트래버스하고 코드에서 다양한 예외를 catch하여 처리할 수 있도록 설정합니다.  물론 예외를 처리하는 방법은 사용자가 선택할 수 있습니다.  
  
## 예제  
 다음 예제는 디렉터리를 순차적으로 반복하지만 동시에 파일을 처리합니다.  파일과 디렉터리 간 비율이 큰 경우 이 방법이 가장 좋은 방법일 수 있습니다.  이 방법에서는 디렉터리 반복을 병렬 처리하고 각 파일에 순차적으로 액세스할 수도 있습니다.  특별히 많은 수의 프로세서가 포함되어 있는 컴퓨터를 대상으로 하지 않는 경우 두 루프를 모두 병렬 처리하는 것은 효율적이지 않을 수 있습니다.  그러나 모든 경우 응용 프로그램을 완벽하게 테스트하여 가장 좋은 방법을 결정해야 합니다.  
  
 [!code-csharp[TPL_Parallel#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_file.cs#08)]
 [!code-vb[TPL_Parallel#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/fileiteration08.vb#08)]  
  
 이 예제에서는 파일 I\/O가 동기적으로 수행됩니다.  큰 파일 또는 느린 네트워크 연결을 처리할 때는 파일에 비동기적으로 액세스하는 것이 좋을 수 있습니다.  병렬 반복에 비동기 I\/O 방법을 결합할 수 있습니다.  자세한 내용은 [TPL and Traditional .NET Framework Asynchronous Programming](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)을 참조하십시오.  
  
 이 예제는 처리하는 파일의 총 개수를 유지하기 위해 로컬 `fileCount` 를 사용합니다.  변수가 여러 작업에 의해 동시에 액세스 될 수 있기 때문에 액세스는 <xref:System.Threading.Interlocked.Add%2A?displayProperty=fullName> 메서드를 호출하여 동기화합니다.  
  
 주 스레드에서 예외가 throw되는 경우 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 메서드에 의해 시작된 스레드가 계속해서 실행될 수 있습니다.  예외 처리기에서 부울 변수를 설정하고 병렬 루프의 각 반복에서 해당 값을 확인하여 이러한 스레드를 중지할 수 있습니다.  값이 예외가 throw되었음을 나타내는 경우 <xref:System.Threading.Tasks.ParallelLoopState> 변수를 사용하여 루프를 중지하거나 루프에서 빠져 나옵니다.  자세한 내용은 [How to: Stop or Break from a Parallel.For Loop](http://msdn.microsoft.com/ko-kr/de52e4f1-9346-4ad5-b582-1a4d54dc7f7e)을 참조하십시오.  
  
## 참고 항목  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)