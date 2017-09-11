---
title: "방법: Task.WhenAll (Visual Basic)를 사용 하 여 비동기 연습 확장 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c06d386d-e996-4da9-bf3d-05a3b6c0a258
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 91cecc84899c9a87307ed5799485ec60ef341e65
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-visual-basic"></a><span data-ttu-id="d90a6-102">방법: Task.WhenAll (Visual Basic)를 사용 하 여 비동기 연습 확장</span><span class="sxs-lookup"><span data-stu-id="d90a6-102">How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)</span></span>
<span data-ttu-id="d90a6-103">비동기 솔루션의 성능을 향상 시킬 수 있습니다 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) 를 사용 하 여는 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>메서드.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d90a6-103">You can improve the performance of the async solution in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) by using the <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="d90a6-104">이 메서드는 작업의 컬렉션으로 표시 되는 여러 개의 비동기 작업을 비동기적으로 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-104">This method asynchronously awaits multiple asynchronous operations, which are represented as a collection of tasks.</span></span>  
  
 <span data-ttu-id="d90a6-105">보았을 것 연습에서 웹 사이트를 서로 다른 속도로 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-105">You might have noticed in the walkthrough that the websites download at different rates.</span></span> <span data-ttu-id="d90a6-106">때로는 웹 사이트 중 하나 매우 느립니다, 나머지 모든 다운로드를 지연입니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-106">Sometimes one of the websites is very slow, which delays all the remaining downloads.</span></span> <span data-ttu-id="d90a6-107">이 연습에서 작성 하는 비동기 솔루션을 실행 하면 수를 종료할 때는 프로그램 쉽게 대기 하지 않으려는 경우 더 나은 옵션을 동시에 모든 다운로드를 시작 하 고 더 빠르게 사용 하는 것 다운로드 지연 되는 것을 기다리지 않고 계속 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-107">When you run the asynchronous solutions that you build in the walkthrough, you can end the program easily if you don't want to wait, but a better option would be to start all the downloads at the same time and let faster downloads continue without waiting for the one that’s delayed.</span></span>  
  
 <span data-ttu-id="d90a6-108">적용 하면는 `Task.WhenAll` 메서드를 작업의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-108">You apply the `Task.WhenAll` method to a collection of tasks.</span></span> <span data-ttu-id="d90a6-109">응용 프로그램의 `WhenAll` 컬렉션의 모든 작업이 완료 될 때까지 완료 되지 않은 단일 작업을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-109">The application of `WhenAll` returns a single task that isn’t complete until every task in the collection is completed.</span></span> <span data-ttu-id="d90a6-110">작업을 병렬로 실행할 처럼 보이지만는 추가 스레드가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-110">The tasks appear to run in parallel, but no additional threads are created.</span></span> <span data-ttu-id="d90a6-111">작업 순서에 관계 없이 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-111">The tasks can complete in any order.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d90a6-112">다음 절차에서 개발 된 비동기 응용 프로그램에 대 한 확장 설명 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-112">The following procedures describe extensions to the async applications that are developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="d90a6-113">연습을 완료 하거나 코드를 다운로드 하 여 응용 프로그램을 개발할 수 [개발자 코드 샘플](http://go.microsoft.com/fwlink/?LinkId=255191)합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-113">You can develop the applications by either completing the walkthrough or downloading the code from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191).</span></span>  
>   
>  <span data-ttu-id="d90a6-114">예제를 실행 하려면 Visual Studio 2012 있어야 합니다. 또는 나중에 컴퓨터에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-114">To run the example, you must have Visual Studio 2012 or later installed on your computer.</span></span>  
  
### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a><span data-ttu-id="d90a6-115">GetURLContentsAsync 솔루션에 Task.WhenAll을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="d90a6-115">To add Task.WhenAll to your GetURLContentsAsync solution</span></span>  
  
1.  <span data-ttu-id="d90a6-116">추가 된 `ProcessURLAsync` 에서 개발 된 첫 번째 응용 프로그램에 메서드 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-116">Add the `ProcessURLAsync` method to the first application that's developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    -   <span data-ttu-id="d90a6-117">코드를 다운로드 한 경우 [개발자 코드 샘플](http://go.microsoft.com/fwlink/?LinkId=255191)AsyncWalkthrough 프로젝트를 연 다음 추가 `ProcessURLAsync` MainWindow.xaml.vb 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-117">If you downloaded the code from  [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191), open the AsyncWalkthrough project, and then add `ProcessURLAsync` to the MainWindow.xaml.vb file.</span></span>  
  
    -   <span data-ttu-id="d90a6-118">이 연습을 완료 하 여 코드를 개발 하는 경우 추가 `ProcessURLAsync` 포함 된 응용 프로그램에는 `GetURLContentsAsync` 메서드.</span><span class="sxs-lookup"><span data-stu-id="d90a6-118">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that includes the `GetURLContentsAsync` method.</span></span> <span data-ttu-id="d90a6-119">이 응용 프로그램의 MainWindow.xaml.vb 파일은 "전체 코드 예제에서" 연습 "섹션의 첫 번째 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-119">The MainWindow.xaml.vb file for this application is the first example in the "Complete Code Examples from the Walkthrough" section.</span></span>  
  
     <span data-ttu-id="d90a6-120">`ProcessURLAsync` 메서드 통합 작업의 본문에는 `For Each` 루프 `SumPageSizesAsync` 원래 연습에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-120">The `ProcessURLAsync` method consolidates the actions in the body of the `For Each` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="d90a6-121">메서드가는 비동기적으로 바이트 배열로 지정된 된 웹 사이트의 내용을 다운로드 다음 표시 되며 및 바이트 배열의 길이 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-121">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)  
  
        Dim byteArray = Await GetURLContentsAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
    ```  
  
2.  <span data-ttu-id="d90a6-122">주석으로 처리 하거나 삭제는 `For Each` 루프 `SumPageSizesAsync`다음 코드와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-122">Comment out or delete the `For Each` loop in `SumPageSizesAsync`, as the following code shows.</span></span>  
  
    ```vb  
    'Dim total = 0  
    'For Each url In urlList  
  
    '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
  
    '    ' The previous line abbreviates the following two assignment statements.  
  
    '    ' GetURLContentsAsync returns a task. At completion, the task  
    '    ' produces a byte array.  
    '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)  
    '    'Dim urlContents As Byte() = Await getContentsTask  
  
    '    DisplayResults(url, urlContents)  
  
    '    ' Update the total.  
    '    total += urlContents.Length  
    'Next  
    ```  
  
3.  <span data-ttu-id="d90a6-123">작업 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-123">Create a collection of tasks.</span></span> <span data-ttu-id="d90a6-124">다음 코드를 정의 [쿼리](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) 를 실행 하면는 <xref:System.Linq.Enumerable.ToArray%2A>메서드를 각 웹 사이트의 콘텐츠를 다운로드 하는 작업의 컬렉션을 만듭니다.</xref:System.Linq.Enumerable.ToArray%2A></span><span class="sxs-lookup"><span data-stu-id="d90a6-124">The following code defines a [query](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="d90a6-125">작업에는 쿼리가 평가 될 때 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-125">The tasks are started when the query is evaluated.</span></span>  
  
     <span data-ttu-id="d90a6-126">메서드에 다음 코드를 추가 `SumPageSizesAsync` 의 선언 뒤 `urlList`합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-126">Add the following code to method `SumPageSizesAsync` after the declaration of `urlList`.</span></span>  
  
    ```vb  
    ' Create a query.   
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url)  
  
    ' Use ToArray to execute the query and start the download tasks.  
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  <span data-ttu-id="d90a6-127">적용 `Task.WhenAll` 작업의 컬렉션에 `downloadTasks`합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-127">Apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="d90a6-128">`Task.WhenAll`작업의 컬렉션에서 모든 작업이 완료 될 때 완료 하는 단일 작업을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-128">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>  
  
     <span data-ttu-id="d90a6-129">다음 예제에서는 `Await` 식을 단일의 완료를 대기 하는 작업입니다 `WhenAll` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-129">In the following example, the `Await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="d90a6-130">식은 각 정수는 다운로드 한 웹 사이트의 길이 정수 배열이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-130">The expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="d90a6-131">다음 코드를 추가 `SumPageSizesAsync`를 이전 단계에서 추가한 코드 뒤 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-131">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>  
  
    ```vb  
    ' Await the completion of all the running tasks.  
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
    '' The previous line is equivalent to the following two statements.  
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
    'Dim lengths As Integer() = Await whenAllTask  
    ```  
  
5.  <span data-ttu-id="d90a6-132">마지막으로, 사용 된 <xref:System.Linq.Enumerable.Sum%2A>모든 웹 사이트의 길이의 합을 계산 하는 방법.</xref:System.Linq.Enumerable.Sum%2A></span><span class="sxs-lookup"><span data-stu-id="d90a6-132">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to calculate the sum of the lengths of all the websites.</span></span> <span data-ttu-id="d90a6-133">다음 줄을 추가 `SumPageSizesAsync`합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-133">Add the following line to `SumPageSizesAsync`.</span></span>  
  
    ```vb  
    Dim total = lengths.Sum()  
    ```  
  
### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a><span data-ttu-id="d90a6-134">HttpClient.GetByteArrayAsync 솔루션에 Task.WhenAll을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="d90a6-134">To add Task.WhenAll to the HttpClient.GetByteArrayAsync solution</span></span>  
  
1.  <span data-ttu-id="d90a6-135">다음 버전의 추가 `ProcessURLAsync` 에서 개발 된 두 번째 응용 프로그램에 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-135">Add the following version of `ProcessURLAsync` to the second application that's developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    -   <span data-ttu-id="d90a6-136">코드를 다운로드 한 경우 [개발자 코드 샘플](http://go.microsoft.com/fwlink/?LinkId=255191)AsyncWalkthrough_HttpClient 프로젝트를 연 다음 추가 `ProcessURLAsync` MainWindow.xaml.vb 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-136">If you downloaded the code from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191), open the AsyncWalkthrough_HttpClient project, and then add `ProcessURLAsync` to the MainWindow.xaml.vb file.</span></span>  
  
    -   <span data-ttu-id="d90a6-137">이 연습을 완료 하 여 코드를 개발 하는 경우 추가 `ProcessURLAsync` 사용 하 여 응용 프로그램에는 `HttpClient.GetByteArrayAsync` 메서드.</span><span class="sxs-lookup"><span data-stu-id="d90a6-137">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that uses the `HttpClient.GetByteArrayAsync` method.</span></span> <span data-ttu-id="d90a6-138">이 응용 프로그램의 MainWindow.xaml.vb 파일은 "전체 코드 예제에서" 연습 "섹션에 두 번째 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-138">The MainWindow.xaml.vb file for this application is the second example in the "Complete Code Examples from the Walkthrough" section.</span></span>  
  
     <span data-ttu-id="d90a6-139">`ProcessURLAsync` 메서드 통합 작업의 본문에는 `For Each` 루프 `SumPageSizesAsync` 원래 연습에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-139">The `ProcessURLAsync` method consolidates the actions in the body of the `For Each` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="d90a6-140">메서드가는 비동기적으로 바이트 배열로 지정된 된 웹 사이트의 내용을 다운로드 다음 표시 되며 및 바이트 배열의 길이 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-140">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>  
  
     <span data-ttu-id="d90a6-141">유일한 차이점은 `ProcessURLAsync` 이전 절차에서 메서드를 사용 하는는 <xref:System.Net.Http.HttpClient>인스턴스, `client`.</xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="d90a6-141">The only difference from the `ProcessURLAsync` method in the previous procedure is the use of the <xref:System.Net.Http.HttpClient> instance, `client`.</span></span>  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
    ```  
  
2.  <span data-ttu-id="d90a6-142">주석으로 처리 하거나 삭제는 `For Each` 루프 `SumPageSizesAsync`다음 코드와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-142">Comment out or delete the `For Each` loop in `SumPageSizesAsync`, as the following code shows.</span></span>  
  
    ```vb  
    'Dim total = 0   
    'For Each url In urlList   
    '    ' GetByteArrayAsync returns a task. At completion, the task   
    '    ' produces a byte array.   
    '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)   
  
    '    ' The following two lines can replace the previous assignment statement.   
    '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)   
    '    'Dim urlContents As Byte() = Await getContentsTask   
  
    '    DisplayResults(url, urlContents)   
  
    '    ' Update the total.   
    '    total += urlContents.Length   
    'Next  
  
    ```  
  
3.  <span data-ttu-id="d90a6-143">정의 [쿼리](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) 를 실행 하면는 <xref:System.Linq.Enumerable.ToArray%2A>메서드를 각 웹 사이트의 콘텐츠를 다운로드 하는 작업의 컬렉션을 만듭니다.</xref:System.Linq.Enumerable.ToArray%2A></span><span class="sxs-lookup"><span data-stu-id="d90a6-143">Define a [query](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="d90a6-144">작업에는 쿼리가 평가 될 때 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-144">The tasks are started when the query is evaluated.</span></span>  
  
     <span data-ttu-id="d90a6-145">메서드에 다음 코드를 추가 `SumPageSizesAsync` 의 선언 뒤 `client` 및 `urlList`합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-145">Add the following code to method `SumPageSizesAsync` after the declaration of `client` and `urlList`.</span></span>  
  
    ```vb  
    ' Create a query.  
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url, client)  
  
    ' Use ToArray to execute the query and start the download tasks.  
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  <span data-ttu-id="d90a6-146">다음으로, 적용 `Task.WhenAll` 작업의 컬렉션에 `downloadTasks`합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-146">Next, apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="d90a6-147">`Task.WhenAll`작업의 컬렉션에서 모든 작업이 완료 될 때 완료 하는 단일 작업을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-147">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>  
  
     <span data-ttu-id="d90a6-148">다음 예제에서는 `Await` 식을 단일의 완료를 대기 하는 작업입니다 `WhenAll` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-148">In the following example, the `Await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="d90a6-149">완료 되 면는 `Await` 식이 있는 각 정수는 다운로드 한 웹 사이트의 길이, 정수의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-149">When complete, the `Await` expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="d90a6-150">다음 코드를 추가 `SumPageSizesAsync`를 이전 단계에서 추가한 코드 뒤 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-150">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>  
  
    ```vb  
    ' Await the completion of all the running tasks.  
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
    '' The previous line is equivalent to the following two statements.  
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
    'Dim lengths As Integer() = Await whenAllTask  
    ```  
  
5.  <span data-ttu-id="d90a6-151">마지막으로 사용 하 여는 <xref:System.Linq.Enumerable.Sum%2A>를 모든 웹 사이트의 길이 합한 값을 가져오는 메서드입니다.</xref:System.Linq.Enumerable.Sum%2A></span><span class="sxs-lookup"><span data-stu-id="d90a6-151">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to get the sum of the lengths of all the websites.</span></span> <span data-ttu-id="d90a6-152">다음 줄을 추가 `SumPageSizesAsync`합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-152">Add the following line to `SumPageSizesAsync`.</span></span>  
  
    ```vb  
    Dim total = lengths.Sum()  
    ```  
  
### <a name="to-test-the-taskwhenall-solutions"></a><span data-ttu-id="d90a6-153">Task.WhenAll 솔루션을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="d90a6-153">To test the Task.WhenAll solutions</span></span>  
  
-   <span data-ttu-id="d90a6-154">두 솔루션에 대 한 프로그램을 실행 하려면 F5 키를 선택 하 고 선택 된 **시작** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-154">For either solution, choose the F5 key to run the program, and then choose the **Start** button.</span></span> <span data-ttu-id="d90a6-155">출력의 출력에서 비동기 솔루션을 비슷해야 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-155">The output should resemble the output from the async solutions in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="d90a6-156">그러나 웹 사이트 나타나는 각 시간에 다른 순서로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-156">However, notice that the websites appear in a different order each time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d90a6-157">예제</span><span class="sxs-lookup"><span data-stu-id="d90a6-157">Example</span></span>  
 <span data-ttu-id="d90a6-158">다음 코드에서는 사용 하는 프로젝트에 대 한 확장은 `GetURLContentsAsync` 메서드는 웹에서 콘텐츠를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-158">The following code shows the extensions to the project that uses the `GetURLContentsAsync` method to download content from the web.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        resultsTextBox.Clear()  
  
        ' One-step async call.  
        Await SumPageSizesAsync()  
  
        '' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' Create a query.   
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url)  
  
        ' Use ToArray to execute the query and start the download tasks.  
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
  
        ' You can do other work here before awaiting.  
  
        ' Await the completion of all the running tasks.  
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
        '' The previous line is equivalent to the following two statements.  
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
        'Dim lengths As Integer() = Await whenAllTask  
  
        Dim total = lengths.Sum()  
  
        'Dim total = 0  
        'For Each url In urlList  
  
        '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
  
        '    ' The previous line abbreviates the following two assignment statements.  
  
        '    ' GetURLContentsAsync returns a task. At completion, the task  
        '    ' produces a byte array.  
        '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)  
        '    'Dim urlContents As Byte() = Await getContentsTask  
  
        '    DisplayResults(url, urlContents)  
  
        '    ' Update the total.  
        '    total += urlContents.Length  
        'NextNext  
  
        ' Display the total count for all of the web addresses.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    ' The actions from the foreach loop are moved to this async method.  
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)  
  
        Dim byteArray = Await GetURLContentsAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
  
        ' The downloaded resource ends up in the variable named content.  
        Dim content = New MemoryStream()  
  
        ' Initialize an HttpWebRequest for the current URL.  
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
        ' Send the request to the Internet resource and wait for  
        ' the response.  
        Using response As WebResponse = Await webReq.GetResponseAsync()  
            ' Get the data stream that is associated with the specified URL.  
            Using responseStream As Stream = response.GetResponseStream()  
                ' Read the bytes in responseStream and copy them to content.    
                ' CopyToAsync returns a Task, not a Task<T>.  
                Await responseStream.CopyToAsync(content)  
            End Using  
        End Using  
  
        ' Return the result as a byte array.  
        Return content.ToArray()  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="example"></a><span data-ttu-id="d90a6-159">예제</span><span class="sxs-lookup"><span data-stu-id="d90a6-159">Example</span></span>  
 <span data-ttu-id="d90a6-160">다음 코드에서는 메서드를 사용 하는 프로젝트에 대 한 확장 `HttpClient.GetByteArrayAsync` 웹에서 콘텐츠를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90a6-160">The following code shows the extensions to the project that uses method `HttpClient.GetByteArrayAsync` to download content from the web.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        resultsTextBox.Clear()  
  
        '' One-step async call.  
        Await SumPageSizesAsync()  
  
        '' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Declare an HttpClient object and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' Create a query.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client)  
  
        ' Use ToArray to execute the query and start the download tasks.  
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
  
        ' You can do other work here before awaiting.  
  
        ' Await the completion of all the running tasks.  
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
        '' The previous line is equivalent to the following two statements.  
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
        'Dim lengths As Integer() = Await whenAllTask  
  
        Dim total = lengths.Sum()  
  
        ''<snippet7>  
        'Dim total = 0  
        'For Each url In urlList  
        '    ' GetByteArrayAsync returns a task. At completion, the task  
        '    ' produces a byte array.  
        '    '<snippet31>  
        '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
        '    '</snippet31>  
  
        '    ' The following two lines can replace the previous assignment statement.  
        '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)  
        '    'Dim urlContents As Byte() = Await getContentsTask  
  
        '    DisplayResults(url, urlContents)  
  
        '    ' Update the total.  
        '    total += urlContents.Length  
        'NextNext  
  
        ' Display the total count for all of the web addresses.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://www.msdn.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="d90a6-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d90a6-161">See Also</span></span>  
 <span data-ttu-id="d90a6-162"><xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d90a6-162"><xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></span></span>   
<span data-ttu-id="d90a6-163"> [연습: Async를 사용 하 여 웹 서비스에 액세스 및 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)</span><span class="sxs-lookup"><span data-stu-id="d90a6-163"> [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)</span></span>
