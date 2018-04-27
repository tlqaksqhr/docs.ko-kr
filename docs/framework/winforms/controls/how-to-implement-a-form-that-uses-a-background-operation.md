---
title: '방법: 백그라운드 작업을 사용하는 폼 구현'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- background threads
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9f483f93-1613-4be1-a021-b4934e9c78f3
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 416e7e1a4a380e13c9b3f776bc8e31812b217c51
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="e42ae-102">방법: 백그라운드 작업을 사용하는 폼 구현</span><span class="sxs-lookup"><span data-stu-id="e42ae-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="e42ae-103">다음 예제 프로그램은 피보나치 숫자를 계산하는 폼을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e42ae-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="e42ae-104">계산은 사용자 인터페이스 스레드와 별개인 스레드에서 실행되므로 계산이 진행될 때 사용자 인터페이스가 지연 없이 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e42ae-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="e42ae-105">Visual Studio에서는 이 작업이 광범위하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e42ae-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="e42ae-106">또한 [연습: 백그라운드 작업을 사용하는 양식 구현](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e42ae-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e42ae-107">예제</span><span class="sxs-lookup"><span data-stu-id="e42ae-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e42ae-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e42ae-108">Compiling the Code</span></span>  
 <span data-ttu-id="e42ae-109">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e42ae-109">This example requires:</span></span>  
  
-   <span data-ttu-id="e42ae-110">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="e42ae-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="e42ae-111">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e42ae-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="e42ae-112">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e42ae-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="e42ae-113">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e42ae-113">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e42ae-114">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="e42ae-114">Robust Programming</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e42ae-115">모든 종류의 다중 스레딩을 사용할 때는 매우 심각하고 복잡한 버그에 잠재적으로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="e42ae-115">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="e42ae-116">다중 스레딩을 사용하는 솔루션을 구현하기 전에 [관리되는 스레딩을 구현하는 최선의 방법](../../../../docs/standard/threading/managed-threading-best-practices.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e42ae-116">Consult the [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e42ae-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e42ae-117">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [<span data-ttu-id="e42ae-118">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="e42ae-118">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="e42ae-119">관리되는 스레딩을 구현하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="e42ae-119">Managed Threading Best Practices</span></span>](../../../../docs/standard/threading/managed-threading-best-practices.md)
