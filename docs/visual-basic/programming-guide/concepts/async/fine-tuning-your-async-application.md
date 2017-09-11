---
title: "Async (Visual Basic) 응용 프로그램을 미세 조정 | Microsoft 문서"
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
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
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
ms.openlocfilehash: e031c2e23430a62629424ee57a140a7d8da41777
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="fine-tuning-your-async-application-visual-basic"></a><span data-ttu-id="2d23e-102">Async (Visual Basic) 응용 프로그램을 미세 조정</span><span class="sxs-lookup"><span data-stu-id="2d23e-102">Fine-Tuning Your Async Application (Visual Basic)</span></span>
<span data-ttu-id="2d23e-103">추가할 수 있습니다 정밀도 및 유연성을 비동기 응용 프로그램에 메서드 및 속성을 사용 하 여 하는 <xref:System.Threading.Tasks.Task>형식을 사용할 수 있도록 합니다.</xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="2d23e-103">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="2d23e-104">이 섹션의 항목 사용 하는 예제를 보여 줍니다. <xref:System.Threading.CancellationToken>중요 한 `Task` <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> </xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> 등의</xref:System.Threading.CancellationToken></span><span class="sxs-lookup"><span data-stu-id="2d23e-104">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="2d23e-105">사용 하 여 `WhenAny` 및 `WhenAll`를 더 쉽게 여러 작업을 시작 하 고 단일 작업을 모니터링 하 여 완료를 기다리는 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d23e-105">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
-   <span data-ttu-id="2d23e-106">`WhenAny`컬렉션에서 모든 작업이 완료 되 면 완료 되는 작업을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23e-106">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="2d23e-107">사용 하는 예제를 보려면 `WhenAny`, 참조 [하나의 완전 (Visual Basic) 한 후 남은 비동기 작업 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)및 [여러 비동기 작업을 시작 하 고 프로세스에로 이러한 완전 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23e-107">For examples that use `WhenAny`, see  [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)and [Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
-   <span data-ttu-id="2d23e-108">`WhenAll`컬렉션의 모든 작업이 완료 되 면 완료 하는 작업을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23e-108">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="2d23e-109">자세한 내용 및 사용 하는 예제 `WhenAll`, 참조 [하는 방법: Task.WhenAll (Visual Basic)를 사용 하 여 비동기 연습 확장](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23e-109">For more information and an example that uses `WhenAll`, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="2d23e-110">이 섹션에는 다음 예제에서는 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d23e-110">This section includes the following examples.</span></span>  
  
-   <span data-ttu-id="2d23e-111">[비동기 작업 또는 작업 (Visual Basic) 목록이 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23e-111">[Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
-   [<span data-ttu-id="2d23e-112">(Visual Basic) 기간 이후 비동기 작업 취소</span><span class="sxs-lookup"><span data-stu-id="2d23e-112">Cancel Async Tasks after a Period of Time (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [<span data-ttu-id="2d23e-113">하나가 (Visual Basic) 완료 되 면 남은 비동기 작업 취소</span><span class="sxs-lookup"><span data-stu-id="2d23e-113">Cancel Remaining Async Tasks after One Is Complete (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [<span data-ttu-id="2d23e-114">여러 비동기 작업을 시작 하 고 (Visual Basic) 완료 될 때마다 처리</span><span class="sxs-lookup"><span data-stu-id="2d23e-114">Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  <span data-ttu-id="2d23e-115">예제를 실행 하려면 Visual Studio 2012 이상 및.NET Framework 4.5 또는 있어야 사용자의 컴퓨터에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d23e-115">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="2d23e-116">프로젝트는 프로세스를 시작 하는 단추와 다음 이미지와 같이, 취소 하는 단추가 포함 된 UI를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d23e-116">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="2d23e-117">단추는 이름이 지정 `startButton` 및 `cancelButton`합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23e-117">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="2d23e-118">![취소 단추가 있는 WPF 창](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "취소")</span><span class="sxs-lookup"><span data-stu-id="2d23e-118">![WPF window with Cancel button](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "Cancellation")</span></span>  
  
 <span data-ttu-id="2d23e-119">전체 Windows Presentation Foundation (WPF) 프로젝트를 다운로드할 수 있습니다 [Async 샘플: 세밀 하 게 응용 프로그램 튜닝](http://go.microsoft.com/fwlink/?LinkId=255046)합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23e-119">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d23e-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2d23e-120">See Also</span></span>  
 [<span data-ttu-id="2d23e-121">비동기 프로그래밍 async 및 Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d23e-121">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)
