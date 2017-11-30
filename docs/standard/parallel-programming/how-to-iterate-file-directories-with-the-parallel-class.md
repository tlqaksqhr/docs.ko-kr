---
title: "방법: 병렬 클래스를 사용하여 파일 디렉터리 열거"
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
helpviewer_keywords: parallel loops, how to iterate directories
ms.assetid: 555e9f48-f53d-4774-9bcf-3e965c732ec5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c21aadf70eaccafc8c8ec9c4efefff1c66abc6b5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-iterate-file-directories-with-the-parallel-class"></a><span data-ttu-id="62c2b-102">방법: 병렬 클래스를 사용하여 파일 디렉터리 열거</span><span class="sxs-lookup"><span data-stu-id="62c2b-102">How to: Iterate File Directories with the Parallel Class</span></span>
<span data-ttu-id="62c2b-103">대부분의 경우에서 파일 반복 하는 작업 쉽게 병렬 처리할 수입니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-103">In many cases, file iteration is an operation that can be easily parallelized.</span></span> <span data-ttu-id="62c2b-104">항목 [하는 방법: PLINQ 사용 하 여 파일 디렉터리 반복](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md) 대부분의 시나리오에이 작업을 수행 하는 가장 쉬운 방법은 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-104">The topic [How to: Iterate File Directories with PLINQ](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md) shows the easiest way to perform this task for many scenarios.</span></span> <span data-ttu-id="62c2b-105">그러나 코드에 여러 종류의 파일 시스템에 액세스할 때 발생할 수 있는 예외를 처리 하는 경우 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-105">However, complications can arise when your code has to deal with the many types of exceptions that can arise when accessing the file system.</span></span> <span data-ttu-id="62c2b-106">다음 예제에서는 문제에는 한 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-106">The following example shows one approach to the problem.</span></span> <span data-ttu-id="62c2b-107">스택 기반 반복을 사용 하 여 모든 파일 및 지정된 된 디렉터리 아래에 폴더를 이동 하 고 코드를 catch 하 고 다양 한 예외를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-107">It uses a stack-based iteration to traverse all files and folders under a specified directory, and it enables your code to catch and handle various exceptions.</span></span> <span data-ttu-id="62c2b-108">물론, 예외를 처리 하는 방식과 합니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-108">Of course, the way that you handle the exceptions is up to you.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62c2b-109">예제</span><span class="sxs-lookup"><span data-stu-id="62c2b-109">Example</span></span>  
 <span data-ttu-id="62c2b-110">다음 예제에서는 디렉터리를 순차적으로 반복하지만 파일을 병렬로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-110">The following example iterates the directories sequentially, but processes the files in parallel.</span></span> <span data-ttu-id="62c2b-111">이것이 가장 좋은 방법이 있으면 큰 디렉터리에 파일 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-111">This is probably the best approach when you have a large file-to-directory ratio.</span></span> <span data-ttu-id="62c2b-112">디렉터리 반복을 병렬화 하 여 순차적으로 각 파일에 액세스할 수 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-112">It is also possible to parallelize the directory iteration, and access each file sequentially.</span></span> <span data-ttu-id="62c2b-113">많은 수의 프로세서를 사용 하는 컴퓨터가 구체적으로 대상으로 하는 경우가 아니면 두 루프를 병렬화 하 효율적 되지 않았을 수입니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-113">It is probably not efficient to parallelize both loops unless you are specifically targeting a machine with a large number of processors.</span></span> <span data-ttu-id="62c2b-114">그러나 모든 경우에서와 같이 철저 하 게 하는 최선의 방법을 결정 하는 응용 프로그램을 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-114">However, as in all cases, you should test your application thoroughly to determine the best approach.</span></span>  
  
 [!code-csharp[TPL_Parallel#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_file.cs#08)]
 [!code-vb[TPL_Parallel#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/fileiteration08.vb#08)]  
  
 <span data-ttu-id="62c2b-115">이 예제에서는 파일 I/O는 동기적으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-115">In this example, the file I/O is performed synchronously.</span></span> <span data-ttu-id="62c2b-116">큰 파일 또는 느린 네트워크 연결을 처리할 때는 파일에 비동기적으로 액세스 하는 것이 좋습니다 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-116">When dealing with large files or slow network connections, it might be preferable to access the files asynchronously.</span></span> <span data-ttu-id="62c2b-117">비동기 I/O 기법 병렬 반복 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-117">You can combine asynchronous I/O techniques with parallel iteration.</span></span> <span data-ttu-id="62c2b-118">자세한 내용은 [TPL 및 일반적인 .NET 비동기 프로그래밍](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="62c2b-118">For more information, see [TPL and Traditional .NET Framework Asynchronous Programming](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md).</span></span>  
  
 <span data-ttu-id="62c2b-119">이 예제에서는 지역 `fileCount` 변수를 사용하여 처리된 총 파일 수를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-119">The example uses the local `fileCount` variable to maintain a count of the total number of files processed.</span></span> <span data-ttu-id="62c2b-120">이 변수가 여러 작업에서 동시에 액세스될 수 있기 때문에 이 변수에 대한 액세스는 <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType> 메서드를 호출하여 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-120">Because the variable might be accessed concurrently by multiple tasks, access to it is synchronized by calling the <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="62c2b-121">주 예외가 throw 되 면 스레드가에 의해 시작 된 스레드는 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 메서드가 계속 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-121">Note that if an exception is thrown on the main thread, the threads that are started by the <xref:System.Threading.Tasks.Parallel.ForEach%2A> method might continue to run.</span></span> <span data-ttu-id="62c2b-122">이러한 스레드를 중지 하려면 예외 처리기의 부울 변수를 설정할 수 있으며 병렬 루프의 각 반복에 해당 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-122">To stop these threads, you can set a Boolean variable in your exception handlers, and check its value on each iteration of the parallel loop.</span></span> <span data-ttu-id="62c2b-123">사용 하 여 값에는 예외가 throw 되었음을 나타내는 경우는 <xref:System.Threading.Tasks.ParallelLoopState> 루프에서 중지 또는 중단 하는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-123">If the value indicates that an exception has been thrown, use the <xref:System.Threading.Tasks.ParallelLoopState> variable to stop or break from the loop.</span></span> <span data-ttu-id="62c2b-124">자세한 내용은 참조 [하는 방법: Parallel.For 루프에서 중지 또는 중단](http://msdn.microsoft.com/en-us/de52e4f1-9346-4ad5-b582-1a4d54dc7f7e)합니다.</span><span class="sxs-lookup"><span data-stu-id="62c2b-124">For more information, see [How to: Stop or Break from a Parallel.For Loop](http://msdn.microsoft.com/en-us/de52e4f1-9346-4ad5-b582-1a4d54dc7f7e).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62c2b-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62c2b-125">See Also</span></span>  
 [<span data-ttu-id="62c2b-126">데이터 병렬 처리</span><span class="sxs-lookup"><span data-stu-id="62c2b-126">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
