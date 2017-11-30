---
title: "방법: 인쇄 큐의 하위 집합 열거"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 393d1692526551b1eb9aa16f48d3c78c3cd6692f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="a512f-102">방법: 인쇄 큐의 하위 집합 열거</span><span class="sxs-lookup"><span data-stu-id="a512f-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="a512f-103">프린터의 회사 전체 집합을 관리 하는 정보 기술 (IT) 전문가가 직면 하는 일반적인 상황 특정 한 특성이 있는 프린터의 목록을 생성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a512f-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="a512f-104">이 기능을 제공는 <xref:System.Printing.PrintServer.GetPrintQueues%2A> 의 메서드는 <xref:System.Printing.PrintServer> 개체 및 <xref:System.Printing.EnumeratedPrintQueueTypes> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="a512f-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a512f-105">예제</span><span class="sxs-lookup"><span data-stu-id="a512f-105">Example</span></span>  
 <span data-ttu-id="a512f-106">아래 예제에서 코드는 먼저 나열 하려는 인쇄 대기열의 특성을 지정 하는 플래그의 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a512f-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="a512f-107">이 예제에서는 인쇄 큐 인쇄 서버에 로컬로 설치 되 고 공유를 찾고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a512f-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="a512f-108"><xref:System.Printing.EnumeratedPrintQueueTypes> 열거형은 다양 한 비즈니스 가능성이 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a512f-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="a512f-109">코드는 다음 만듭니다는 <xref:System.Printing.LocalPrintServer> 개체에서 파생 된 클래스 <xref:System.Printing.PrintServer>합니다.</span><span class="sxs-lookup"><span data-stu-id="a512f-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="a512f-110">로컬 인쇄 서버는 응용 프로그램이 실행 되는 컴퓨터.</span><span class="sxs-lookup"><span data-stu-id="a512f-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="a512f-111">마지막 중요 한 단계에 배열을 전달 하는 것은 <xref:System.Printing.PrintServer.GetPrintQueues%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="a512f-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="a512f-112">마지막으로 결과가 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a512f-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="a512f-113">이 예제를 사용 함으로써 확장할 수는 `foreach` 각 인쇄 큐를 통해 단계를 추가로 수행 하는 루프 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a512f-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="a512f-114">예를 들어 있습니다 수 차단 프린터에서 양면 인쇄 루프 호출 함으로써 지원 하지 않는 각 인쇄 대기열의 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> 메서드와 이중의 존재 여부에 대 한 반환 되는 값을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a512f-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a512f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a512f-115">See Also</span></span>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [<span data-ttu-id="a512f-116">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="a512f-116">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="a512f-117">인쇄 개요</span><span class="sxs-lookup"><span data-stu-id="a512f-117">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="a512f-118">Microsoft XPS Document Writer</span><span class="sxs-lookup"><span data-stu-id="a512f-118">Microsoft XPS Document Writer</span></span>](http://go.microsoft.com/fwlink/?LinkId=147319)
