---
title: "Async 응용 프로그램 미세 조정(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: 97696eb9-81fc-4940-9655-84daa8eb4d5c
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8d8e655845f2d71e35ac72ba4f5a5b12027e2e1b
ms.sourcegitcommit: cec0525b2121c36198379525e69aa5388266db5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="fine-tuning-your-async-application-c"></a><span data-ttu-id="8f409-102">Async 응용 프로그램 미세 조정(C#)</span><span class="sxs-lookup"><span data-stu-id="8f409-102">Fine-Tuning Your Async Application (C#)</span></span>
<span data-ttu-id="8f409-103"><xref:System.Threading.Tasks.Task> 형식이 제공하는 메서드 및 속성을 사용하여 async 응용 프로그램에 정확성 및 유연성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f409-103">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="8f409-104">이 섹션의 항목에서는 <xref:System.Threading.CancellationToken>을 사용하는 예제와 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>과 같은 중요한 `Task` 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8f409-104">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="8f409-105">`WhenAny` 및 `WhenAll`를 사용하면 더 쉽게 여러 작업을 시작하고 단일 작업을 모니터링하여 완료할 때까지 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f409-105">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
-   <span data-ttu-id="8f409-106">`WhenAny`는 컬렉션의 임의 작업이 완료되면 완료되는 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f409-106">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="8f409-107">`WhenAny`를 사용하는 예제는 [비동기 작업 하나가 완료되면 남은 비동기 작업 취소(C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) 및 [S비동기 작업을 여러 개 시작하고 완료될 때마다 처리(C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f409-107">For examples that use `WhenAny`, see [Cancel Remaining Async Tasks after One Is Complete (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) and [Start Multiple Async Tasks and Process Them As They Complete (C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
-   <span data-ttu-id="8f409-108">`WhenAll`은 컬렉션의 모든 작업이 완료되면 완료되는 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f409-108">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="8f409-109">자세한 내용 및 `WhenAll`을 사용하는 예제는 [방법: Task.WhenAll을 사용하여 비동기 연습 확장(C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f409-109">For more information and an example that uses `WhenAll`, see [How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="8f409-110">이 섹션에 포함된 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8f409-110">This section includes the following examples.</span></span>  
  
-   <span data-ttu-id="8f409-111">[비동기 작업 또는 작업 목록 취소(C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="8f409-111">[Cancel an Async Task or a List of Tasks (C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
-   [<span data-ttu-id="8f409-112">일정 기간 이후 비동기 작업 취소(C#)</span><span class="sxs-lookup"><span data-stu-id="8f409-112">Cancel Async Tasks after a Period of Time (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [<span data-ttu-id="8f409-113">비동기 작업 하나가 완료되면 남은 비동기 작업 취소(C#)</span><span class="sxs-lookup"><span data-stu-id="8f409-113">Cancel Remaining Async Tasks after One Is Complete (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [<span data-ttu-id="8f409-114">비동기 작업을 여러 개 시작하고 완료될 때마다 처리(C#)</span><span class="sxs-lookup"><span data-stu-id="8f409-114">Start Multiple Async Tasks and Process Them As They Complete (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  <span data-ttu-id="8f409-115">예제를 실행하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f409-115">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="8f409-116">다음 그림과 같이 프로젝트는 프로세스를 시작하는 단추와 프로세스를 취소하는 단추가 포함된 UI를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f409-116">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="8f409-117">단추 이름은 `startButton` 및 `cancelButton`입니다.</span><span class="sxs-lookup"><span data-stu-id="8f409-117">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="8f409-118">![취소 단추가 있는 WPF 창](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "취소")</span><span class="sxs-lookup"><span data-stu-id="8f409-118">![WPF window with Cancel button](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "Cancellation")</span></span>  
  
 <span data-ttu-id="8f409-119">[Async 샘플: 응용 프로그램 세부 조정](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)에서 전체 WPF(Windows Presentation Foundation) 프로젝트를 다운로드하여 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f409-119">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f409-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f409-120">See Also</span></span>  
 [<span data-ttu-id="8f409-121">async 및 await를 사용한 비동기 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="8f409-121">Asynchronous Programming with async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/index.md)
