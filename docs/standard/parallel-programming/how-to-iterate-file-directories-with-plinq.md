---
title: "방법: PLINQ를 사용하여 파일 디렉터리 열거"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: PLINQ queries, how to iterate directories
ms.assetid: 354e8ce3-35c4-431c-99ca-7661d1f3901b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 40fd9f64b5702f5205b7817f3de1e0a8709c5a63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-iterate-file-directories-with-plinq"></a><span data-ttu-id="6e3a5-102">방법: PLINQ를 사용하여 파일 디렉터리 열거</span><span class="sxs-lookup"><span data-stu-id="6e3a5-102">How to: Iterate File Directories with PLINQ</span></span>
<span data-ttu-id="6e3a5-103">이 예제에는 파일 디렉터리에 대 한 작업을 병렬화 하는 간단한 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a5-103">This example shows two simple ways to parallelize operations on file directories.</span></span> <span data-ttu-id="6e3a5-104">첫 번째 쿼리에서 사용 하 여는 <xref:System.IO.Directory.GetFiles%2A> 메서드를 디렉터리와 모든 하위 디렉터리에서 파일 이름 배열을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a5-104">The first query uses the <xref:System.IO.Directory.GetFiles%2A> method to populate an array of file names in a directory and all subdirectories.</span></span> <span data-ttu-id="6e3a5-105">이 메서드는 전체 배열이 채워질 때까지 따라서 작업의 시작 부분에 대 한 대기 시간이 발생할 수 있습니다를 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a5-105">This method does not return until the entire array is populated, and therefore it can introduce latency at the beginning of the operation.</span></span> <span data-ttu-id="6e3a5-106">그러나 배열 채워진 후 PLINQ 수 병렬로 처리할 매우 신속 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a5-106">However, after the array is populated, PLINQ can process it in parallel very quickly.</span></span>  
  
 <span data-ttu-id="6e3a5-107">두 번째 쿼리에서 정적을 사용 하 여 <xref:System.IO.Directory.EnumerateDirectories%2A> 및 <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> 즉시 결과 반환 하기 시작 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a5-107">The second query uses the static <xref:System.IO.Directory.EnumerateDirectories%2A> and <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> methods which begin returning results immediately.</span></span> <span data-ttu-id="6e3a5-108">이 방법은 빠를 수 큰 디렉터리 트리를 반복 하는 경우 있지만 처리 시간은 첫 번째 예에 비해 여러 가지 요인에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a5-108">This approach can be faster when you are iterating over large directory trees, although the processing time compared to the first example can depend on many factors.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="6e3a5-109">이 예제는 사용법을 보여 주기 위한 용도가 하 to Objects 쿼리보다 동일한 순차 LINQ 보다 더 빠르게 실행 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a5-109">These examples are intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="6e3a5-110">속도 대 한 자세한 내용은 참조 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a5-110">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e3a5-111">예제</span><span class="sxs-lookup"><span data-stu-id="6e3a5-111">Example</span></span>  
 <span data-ttu-id="6e3a5-112">다음 예제에서는 트리에서 모든 디렉터리에 액세스할 수 있는 파일 크기는 매우 큰 되지 하 고 액세스 시간이 중요 하지 않습니다. 간단한 시나리오에서 파일 디렉터리를 반복 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a5-112">The following example shows how to iterate over file directories in simple scenarios when you have access to all directories in the tree, the file sizes are not very large, and the access times are not significant.</span></span> <span data-ttu-id="6e3a5-113">이 방법은 시작 부분에는 지연 시간이 발생 동안 파일 이름 배열을 생성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a5-113">This approach involves a period of latency at the beginning while the array of file names is being constructed.</span></span>  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## <a name="example"></a><span data-ttu-id="6e3a5-114">예제</span><span class="sxs-lookup"><span data-stu-id="6e3a5-114">Example</span></span>  
 <span data-ttu-id="6e3a5-115">다음 예제에서는 트리에서 모든 디렉터리에 액세스할 수 있는 파일 크기는 매우 큰 되지 하 고 액세스 시간이 중요 하지 않습니다. 간단한 시나리오에서 파일 디렉터리를 반복 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a5-115">The following example shows how to iterate over file directories in simple scenarios when you have access to all directories in the tree, the file sizes are not very large, and the access times are not significant.</span></span> <span data-ttu-id="6e3a5-116">이 방법은 이전 예제 보다 더 빠르게 결과 생성을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a5-116">This approach begins producing results faster than the previous example.</span></span>  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 <span data-ttu-id="6e3a5-117">사용 하는 경우 <xref:System.IO.Directory.GetFiles%2A>, 트리의 모든 디렉터리에 권한이 충분 한지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a5-117">When using <xref:System.IO.Directory.GetFiles%2A>, be sure that you have sufficient permissions on all directories in the tree.</span></span> <span data-ttu-id="6e3a5-118">그렇지 않으면 예외가 throw 되 고 결과가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a5-118">Otherwise an exception will be thrown and no results will be returned.</span></span> <span data-ttu-id="6e3a5-119">사용 하는 경우는 <xref:System.IO.Directory.EnumerateDirectories%2A> PLINQ 쿼리에서 계속 반복할 수 있도록 안전한 방식으로 I/O 예외를 처리 하는 문제가 있는 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a5-119">When using the <xref:System.IO.Directory.EnumerateDirectories%2A> in a PLINQ query, it is problematic to handle I/O exceptions in a graceful way that enables you to continue iterating.</span></span> <span data-ttu-id="6e3a5-120">코드는 I/O 또는 무단된 액세스 예외를 처리 해야 하는 경우에 설명 된 접근 방식을 고려해 야 합니다 [하는 방법: 병렬 클래스를 사용 하 여 파일 디렉터리 반복](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-the-parallel-class.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a5-120">If your code must handle I/O or unauthorized access exceptions, then you should consider the approach described in [How to: Iterate File Directories with the Parallel Class](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-the-parallel-class.md).</span></span>  
  
 <span data-ttu-id="6e3a5-121">I/O 대기 시간이 문제가 되는 경우, 예를 들어 네트워크를 통해 파일 I/O 고려할에서 설명 하는 비동기 I/O 기술 중 하나를 사용 하 여 [TPL 및 일반적인.NET Framework 비동기 프로그래밍](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) 및이 [블로그 게시물 ](http://go.microsoft.com/fwlink/?LinkID=186458).</span><span class="sxs-lookup"><span data-stu-id="6e3a5-121">If I/O latency is an issue, for example with file I/O over a network, consider using one of the asynchronous I/O techniques described in [TPL and Traditional .NET Framework Asynchronous Programming](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) and in this [blog post](http://go.microsoft.com/fwlink/?LinkID=186458).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e3a5-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e3a5-122">See Also</span></span>  
 [<span data-ttu-id="6e3a5-123">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="6e3a5-123">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
