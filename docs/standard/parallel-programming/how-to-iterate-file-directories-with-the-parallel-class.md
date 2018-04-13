---
title: '방법: 병렬 클래스를 사용하여 파일 디렉터리 열거'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to iterate directories
ms.assetid: 555e9f48-f53d-4774-9bcf-3e965c732ec5
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3ac1af7922e1bbd81f4dfcee256f5c8892294003
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-iterate-file-directories-with-the-parallel-class"></a><span data-ttu-id="dfccb-102">방법: 병렬 클래스를 사용하여 파일 디렉터리 열거</span><span class="sxs-lookup"><span data-stu-id="dfccb-102">How to: Iterate File Directories with the Parallel Class</span></span>
<span data-ttu-id="dfccb-103">대부분의 경우 파일 반복은 쉽게 병렬 처리할 수 있는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-103">In many cases, file iteration is an operation that can be easily parallelized.</span></span> <span data-ttu-id="dfccb-104">[방법: PLINQ를 사용하여 파일 디렉터리 반복](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md) 항목은 많은 시나리오에서 이 작업을 수행하는 가장 쉬운 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-104">The topic [How to: Iterate File Directories with PLINQ](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md) shows the easiest way to perform this task for many scenarios.</span></span> <span data-ttu-id="dfccb-105">그러나 코드가 파일 시스템에 액세스할 때 발생할 수 있는 많은 예외 형식을 처리해야 할 경우 복잡해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-105">However, complications can arise when your code has to deal with the many types of exceptions that can arise when accessing the file system.</span></span> <span data-ttu-id="dfccb-106">다음 예제는 문제에 대한 하나의 접근 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-106">The following example shows one approach to the problem.</span></span> <span data-ttu-id="dfccb-107">이 방법은 스택 기반 반복을 사용하여 지정된 디렉터리에서 모든 파일과 폴더를 트래버스하고 코드에서 다양한 예외를 catch하여 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-107">It uses a stack-based iteration to traverse all files and folders under a specified directory, and it enables your code to catch and handle various exceptions.</span></span> <span data-ttu-id="dfccb-108">물론 예외를 처리하는 방법은 사용자가 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-108">Of course, the way that you handle the exceptions is up to you.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfccb-109">예</span><span class="sxs-lookup"><span data-stu-id="dfccb-109">Example</span></span>  
 <span data-ttu-id="dfccb-110">다음 예제에서는 디렉터리를 순차적으로 반복하지만 파일을 병렬로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-110">The following example iterates the directories sequentially, but processes the files in parallel.</span></span> <span data-ttu-id="dfccb-111">이 방법은 파일 대 디렉터리 비율이 큰 경우 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-111">This is probably the best approach when you have a large file-to-directory ratio.</span></span> <span data-ttu-id="dfccb-112">또한 디렉터리 반복을 병렬 처리하고 각 파일에 순차적으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-112">It is also possible to parallelize the directory iteration, and access each file sequentially.</span></span> <span data-ttu-id="dfccb-113">많은 프로세서를 사용하는 컴퓨터를 특별히 대상으로 지정하지 않는 한 두 루프를 모두 병렬 처리하는 것은 효율적이지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-113">It is probably not efficient to parallelize both loops unless you are specifically targeting a machine with a large number of processors.</span></span> <span data-ttu-id="dfccb-114">그러나 모든 경우처럼 응용 프로그램을 철저히 테스트하여 가장 적합한 방법을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-114">However, as in all cases, you should test your application thoroughly to determine the best approach.</span></span>  
  
 [!code-csharp[TPL_Parallel#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_file.cs#08)]
 [!code-vb[TPL_Parallel#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/fileiteration08.vb#08)]  
  
 <span data-ttu-id="dfccb-115">이 예제에서 파일 I/O는 동기적으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-115">In this example, the file I/O is performed synchronously.</span></span> <span data-ttu-id="dfccb-116">큰 파일이나 느린 네트워크 연결을 처리할 경우에는 파일에 비동기적으로 액세스하는 것이 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-116">When dealing with large files or slow network connections, it might be preferable to access the files asynchronously.</span></span> <span data-ttu-id="dfccb-117">비동기 I/O 기술을 병렬 반복과 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-117">You can combine asynchronous I/O techniques with parallel iteration.</span></span> <span data-ttu-id="dfccb-118">자세한 내용은 [TPL 및 일반적인 .NET 비동기 프로그래밍](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dfccb-118">For more information, see [TPL and Traditional .NET Framework Asynchronous Programming](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md).</span></span>  
  
 <span data-ttu-id="dfccb-119">이 예제에서는 지역 `fileCount` 변수를 사용하여 처리된 총 파일 수를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-119">The example uses the local `fileCount` variable to maintain a count of the total number of files processed.</span></span> <span data-ttu-id="dfccb-120">이 변수가 여러 작업에서 동시에 액세스될 수 있기 때문에 이 변수에 대한 액세스는 <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType> 메서드를 호출하여 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-120">Because the variable might be accessed concurrently by multiple tasks, access to it is synchronized by calling the <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="dfccb-121">기본 스레드에서 예외가 throw될 경우 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 메서드를 통해 시작되는 스레드는 계속 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-121">Note that if an exception is thrown on the main thread, the threads that are started by the <xref:System.Threading.Tasks.Parallel.ForEach%2A> method might continue to run.</span></span> <span data-ttu-id="dfccb-122">이러한 스레드를 중지하려면 예외 처리기에서 부울 변수를 설정하고 병렬 루프의 각 반복에서 해당 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-122">To stop these threads, you can set a Boolean variable in your exception handlers, and check its value on each iteration of the parallel loop.</span></span> <span data-ttu-id="dfccb-123">값이 예외가 throw되었음을 나타내는 경우 <xref:System.Threading.Tasks.ParallelLoopState> 변수를 사용하여 루프에서 중지하거나 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="dfccb-123">If the value indicates that an exception has been thrown, use the <xref:System.Threading.Tasks.ParallelLoopState> variable to stop or break from the loop.</span></span> <span data-ttu-id="dfccb-124">자세한 내용은 [방법: Parallel.For 루프에서 중지 또는 중단](http://msdn.microsoft.com/library/de52e4f1-9346-4ad5-b582-1a4d54dc7f7e)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dfccb-124">For more information, see [How to: Stop or Break from a Parallel.For Loop](http://msdn.microsoft.com/library/de52e4f1-9346-4ad5-b582-1a4d54dc7f7e).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfccb-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dfccb-125">See Also</span></span>  
 [<span data-ttu-id="dfccb-126">데이터 병렬 처리</span><span class="sxs-lookup"><span data-stu-id="dfccb-126">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
