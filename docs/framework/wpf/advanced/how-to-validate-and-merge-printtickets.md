---
title: "방법: PrintTicket 유효성 검사 및 병합"
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
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5cf2091d50433bb936b3d4976d1c3eabea73edc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="2cc94-102">방법: PrintTicket 유효성 검사 및 병합</span><span class="sxs-lookup"><span data-stu-id="2cc94-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="2cc94-103">[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Schema](http://go.microsoft.com/fwlink/?LinkId=186397) 유연성이 있고 확장 가능 포함 <xref:System.Printing.PrintCapabilities> 및 <xref:System.Printing.PrintTicket> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-103">The [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](http://go.microsoft.com/fwlink/?LinkId=186397) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="2cc94-104">인쇄 장치의 기능을 전자 항목별로 정리 하 고 후자 지정이 장치가 문서, 개별 문서 또는 개별 페이지의 특정 시퀀스에 대해 이러한 기능을 어떻게 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="2cc94-105">인쇄를 지 원하는 응용 프로그램에 대 한 작업의 일반적인 순서는 다음과 같은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1.  <span data-ttu-id="2cc94-106">프린터의 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-106">Determine a printer's capabilities.</span></span>  
  
2.  <span data-ttu-id="2cc94-107">구성 된 <xref:System.Printing.PrintTicket> 이러한 기능을 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3.  <span data-ttu-id="2cc94-108">유효성 검사는 <xref:System.Printing.PrintTicket>합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="2cc94-109">이 문서에서는이 작업을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cc94-110">예</span><span class="sxs-lookup"><span data-stu-id="2cc94-110">Example</span></span>  
 <span data-ttu-id="2cc94-111">아래의 간단한 예제에서 우리에 관심이 프린터 양면 인쇄를 지원할 수 있는지 여부 — 양면 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="2cc94-112">주요 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-112">The major steps are as follows.</span></span>  
  
1.  <span data-ttu-id="2cc94-113">가져오기는 <xref:System.Printing.PrintCapabilities> 개체는 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="2cc94-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2.  <span data-ttu-id="2cc94-114">원하는 기능이 있는지 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="2cc94-115">테스트 아래 예제는 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> 속성의는 <xref:System.Printing.PrintCapabilities> 시트의 옆으로 "페이지"회전 용지 시트의 양쪽에서 인쇄 기능이 있는지에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="2cc94-116">이후 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> 컬렉션이 사용 하 여는 `Contains` 방식의 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2cc94-117">이 단계는 엄격 하 게 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-117">This step is not strictly necessary.</span></span> <span data-ttu-id="2cc94-118"><xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> 아래 사용 하는 방법에 각 요청을 확인 합니다는 <xref:System.Printing.PrintTicket> 프린터의 기능에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="2cc94-119">프린터에서 필요한 기능을 지원 하지 않는, 프린터 드라이버의 대체 요청을 대체 합니다는 <xref:System.Printing.PrintTicket> 메서드에 의해 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3.  <span data-ttu-id="2cc94-120">샘플 코드에서는 프린터에서 양면 인쇄를 지 원하는 경우는 <xref:System.Printing.PrintTicket> 양면 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="2cc94-121">하지만 응용 프로그램에서 가능한 모든 프린터에서 사용할 수 있는 설정을 지정 하지는 <xref:System.Printing.PrintTicket> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="2cc94-122">프로그래머와 프로그램 시간을 모두의 낭비 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="2cc94-123">코드는 양면 인쇄 요청만 설정 하 고이 병합 하는 대신, <xref:System.Printing.PrintTicket> 된 기존의 완벽 하 게 구성 하 고 유효성을 검사 <xref:System.Printing.PrintTicket>,이 경우 사용자의 기본 <xref:System.Printing.PrintTicket>합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4.  <span data-ttu-id="2cc94-124">샘플 적절 하 게 호출 하는 <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> 새, 병합 하는 메서드, 최소한의 <xref:System.Printing.PrintTicket> 이며 기본값은 사용자의 <xref:System.Printing.PrintTicket>합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="2cc94-125">반환 합니다.는 <xref:System.Printing.ValidationResult> 포함 하는 <xref:System.Printing.PrintTicket> 속성 중 하나로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5.  <span data-ttu-id="2cc94-126">이 샘플에 있는 항목을 다음 테스트 새 <xref:System.Printing.PrintTicket> 양면 인쇄를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="2cc94-127">그렇지 않으면 다음 샘플 하면 사용자에 대 한 새 기본 인쇄 티켓 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="2cc94-128">위의 2 단계 그대로 남아 있었습니다. 프린터 긴 측면 양면 인쇄를 지원 하지 않을 경우에 테스트 결과 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="2cc94-129">(위의 참고 참조).</span><span class="sxs-lookup"><span data-stu-id="2cc94-129">(See the note above.)</span></span>  
  
6.  <span data-ttu-id="2cc94-130">하 여 변경 내용을 커밋하는 마지막 중요 단계는 <xref:System.Printing.PrintQueue.UserPrintTicket%2A> 속성은 <xref:System.Printing.PrintQueue> 와 <xref:System.Printing.PrintQueue.Commit%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="2cc94-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="2cc94-131">이 예에서는 빠르게 테스트 수 있도록 나머지 아래 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="2cc94-132">프로젝트 및 네임 스페이스를 만들고 코드 조각은 네임 스페이스 블록에이 문서에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="2cc94-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cc94-133">See Also</span></span>  
 <xref:System.Printing.PrintCapabilities>  
 <xref:System.Printing.PrintTicket>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [<span data-ttu-id="2cc94-134">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="2cc94-134">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="2cc94-135">인쇄 개요</span><span class="sxs-lookup"><span data-stu-id="2cc94-135">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="2cc94-136">스키마를 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc94-136">Print Schema</span></span>](http://go.microsoft.com/fwlink/?LinkId=186397)
