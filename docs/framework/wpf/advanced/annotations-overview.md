---
title: 주석 개요
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- highlights [WPF]
- documents [WPF], annotations
- sticky notes [WPF]
ms.assetid: 716bf474-29bd-4c74-84a4-8e0744bdad62
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dcc881421e1a6960ab1ab9760ec2cd18a4c77c36
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="annotations-overview"></a><span data-ttu-id="a0a21-102">주석 개요</span><span class="sxs-lookup"><span data-stu-id="a0a21-102">Annotations Overview</span></span>
<span data-ttu-id="a0a21-103">종이 문서에 메모나 설명을 적는 것은 당연하게 받아들이는 매우 일반적인 행동입니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-103">Writing notes or comments on paper documents is such a commonplace activity that we almost take it for granted.</span></span> <span data-ttu-id="a0a21-104">이러한 메모나 설명은 나중에 참조하기 위해 관심 있는 항목을 강조 표시하거나 정보를 첨부하기 위해 문서에 추가하는 "주석"입니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-104">These notes or comments are "annotations" that we add to a document to flag information or to highlight items of interest for later reference.</span></span> <span data-ttu-id="a0a21-105">인쇄된 문서에 메모를 적는 것은 간단하고 일반적이지만 전자 문서에 개인적인 주석을 추가하는 기능은 대개 가능하더라도 매우 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-105">Although writing notes on printed documents is easy and commonplace, the ability to add personal comments to electronic documents is typically very limited, if available at all.</span></span>  
  
 <span data-ttu-id="a0a21-106">이 항목에서는 몇 가지 일반적인 유형의 주석, 특히 스티커 메모 및 강조 표시를 검토 하 고 보여 줍니다 방법을 [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] 이러한 유형의 Windows Presentation Foundation (WPF) 문서를 통해 응용 프로그램에 대 한 주석 컨트롤 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-106">This topic reviews several common types of annotations, specifically sticky notes and highlights, and illustrates how the [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] facilitates these types of annotations in applications through the Windows Presentation Foundation (WPF) document viewing controls.</span></span>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="a0a21-107"> 문서 보기 컨트롤을 지 원하는 주석이 포함 <xref:System.Windows.Controls.FlowDocumentReader> 및 <xref:System.Windows.Controls.FlowDocumentScrollViewer>에서 파생 된 컨트롤 뿐 <xref:System.Windows.Controls.Primitives.DocumentViewerBase> 같은 <xref:System.Windows.Controls.DocumentViewer> 및 <xref:System.Windows.Controls.FlowDocumentPageViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-107"> document viewing controls that support annotations include <xref:System.Windows.Controls.FlowDocumentReader> and <xref:System.Windows.Controls.FlowDocumentScrollViewer>, as well as controls derived from <xref:System.Windows.Controls.Primitives.DocumentViewerBase> such as <xref:System.Windows.Controls.DocumentViewer> and <xref:System.Windows.Controls.FlowDocumentPageViewer>.</span></span>  
  
  
<a name="caf1_type_stickynotes"></a>   
## <a name="sticky-notes"></a><span data-ttu-id="a0a21-108">스티커 메모</span><span class="sxs-lookup"><span data-stu-id="a0a21-108">Sticky Notes</span></span>  
 <span data-ttu-id="a0a21-109">일반적인 스티커 메모는 작은 색지에 정보를 작성하여 문서에 "붙입니다".</span><span class="sxs-lookup"><span data-stu-id="a0a21-109">A typical sticky note contains information written on a small piece of colored paper that is then "stuck" to a document.</span></span> <span data-ttu-id="a0a21-110">디지털 스티커 메모는 전자 문서에 비슷한 기능을 제공하지만 입력된 텍스트, 필기 메모(예: [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)] "잉크" 스트로크) 또는 웹 링크와 같이 다양한 유형의 콘텐츠를 유연하게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-110">Digital sticky notes provide similar functionality for electronic documents, but with the added flexibility to include many other types of content such as typed text, handwritten notes (for example, [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)] "ink" strokes), or Web links.</span></span>  
  
 <span data-ttu-id="a0a21-111">다음 그림에서는 강조 표시, 텍스트 스티커 메모 및 잉크 스티커 메모 주석의 몇 가지 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-111">The following illustration shows some examples of highlight, text sticky note, and ink sticky note annotations.</span></span>  
  
 <span data-ttu-id="a0a21-112">![강조 표시, 텍스트 및 잉크 스티커 메모 주석](../../../../docs/framework/wpf/advanced/media/caf-stickynote.jpg "CAF_StickyNote")</span><span class="sxs-lookup"><span data-stu-id="a0a21-112">![Highlight, text and ink sticky note annotations.](../../../../docs/framework/wpf/advanced/media/caf-stickynote.jpg "CAF_StickyNote")</span></span>  
  
 <span data-ttu-id="a0a21-113">다음 예제에서는 응용 프로그램에서 주석 지원을 설정하는 데 사용할 수 있는 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-113">The following example shows the method that you can use to enable annotation support in your application.</span></span>  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>   
## <a name="highlights"></a><span data-ttu-id="a0a21-114">강조 표시</span><span class="sxs-lookup"><span data-stu-id="a0a21-114">Highlights</span></span>  
 <span data-ttu-id="a0a21-115">사람들은 종이 문서에 표시할 때 밑줄 긋기, 강조 표시, 문장에 포함된 단어에 동그라미 표시, 여백에 표식이나 주석 그리기 등의 창조적인 방법으로 관심 있는 항목에 주의를 끌도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-115">People use creative methods to draw attention to items of interest when they mark up a paper document, such as underlining, highlighting, circling words in a sentence, or drawing marks or notations in the margin.</span></span>  <span data-ttu-id="a0a21-116">[!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)]의 강조 표시 주석은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 문서 보기 컨트롤에 표시되는 정보를 지정하는 것과 비슷한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-116">Highlight annotations in [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] provide a similar feature for marking up information displayed in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] document viewing controls.</span></span>  
  
 <span data-ttu-id="a0a21-117">다음 그림에서는 강조 표시 주석의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-117">The following illustration shows an example of a highlight annotation.</span></span>  
  
 <span data-ttu-id="a0a21-118">![강조 표시 주석](../../../../docs/framework/wpf/advanced/media/caf-callouts.png "CAF_Callouts")</span><span class="sxs-lookup"><span data-stu-id="a0a21-118">![Highlight Annotation](../../../../docs/framework/wpf/advanced/media/caf-callouts.png "CAF_Callouts")</span></span>  
  
 <span data-ttu-id="a0a21-119">일반적으로 사용자가 일부 텍스트 또는 관심 있는 항목을 먼저 선택 하 고 표시 하려면 마우스 오른쪽 단추로 클릭 하 여 주석을 작성 한 <xref:System.Windows.Controls.ContextMenu> 주석 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-119">Users typically create annotations by first selecting some text or an item of interest, and then right-clicking to display a <xref:System.Windows.Controls.ContextMenu> of annotation options.</span></span>  <span data-ttu-id="a0a21-120">다음 예제와 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 선언 하는 데 사용할 수는 <xref:System.Windows.Controls.ContextMenu> 만들고 주석을 관리 하려면 사용자가 액세스할 수 있는 라우팅된 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-120">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] you can use to declare a <xref:System.Windows.Controls.ContextMenu> with routed commands that users can access to create and manage annotations.</span></span>  
  
 [!code-xaml[DocViewerAnnotationsXps#CreateDeleteAnnotations](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>   
## <a name="data-anchoring"></a><span data-ttu-id="a0a21-121">데이터 고정</span><span class="sxs-lookup"><span data-stu-id="a0a21-121">Data Anchoring</span></span>  
 <span data-ttu-id="a0a21-122">[!INCLUDE[TLA2#tla_caf](../../../../includes/tla2sharptla-caf-md.md)]에서는 표시 보기의 위치뿐만 아니라 사용자가 선택한 데이터에도 주석을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-122">The [!INCLUDE[TLA2#tla_caf](../../../../includes/tla2sharptla-caf-md.md)] binds annotations to the data that the user selects, not just to a position on the display view.</span></span> <span data-ttu-id="a0a21-123">따라서 사용자가 표시 창을 스크롤하거나 크기를 조정할 때와 같이 문서 보기가 변경되면 주석은 바인딩된 데이터 선택 항목과 함께 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-123">Therefore, if the document view changes, such as when the user scrolls or resizes the display window, the annotation stays with the data selection to which it is bound.</span></span> <span data-ttu-id="a0a21-124">예를 들어 다음 그래픽에서는 사용자가 텍스트를 선택하여 만든 주석을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-124">For example, the following graphic illustrates an annotation that the user has made on a text selection.</span></span> <span data-ttu-id="a0a21-125">문서 보기가 변경되면(스크롤, 크기 조정, 배율 또는 이동 등) 강조 표시 주석은 원래의 데이터 선택 항목과 함께 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-125">When the document view changes (scrolls, resizes, scales, or otherwise moves), the highlight annotation moves with the original data selection.</span></span>  
  
 <span data-ttu-id="a0a21-126">![주석 데이터 고정](../../../../docs/framework/wpf/advanced/media/caf-dataanchoring.png "CAF_DataAnchoring")</span><span class="sxs-lookup"><span data-stu-id="a0a21-126">![Annotation Data Anchoring](../../../../docs/framework/wpf/advanced/media/caf-dataanchoring.png "CAF_DataAnchoring")</span></span>  
  
<a name="matching_annotations_with_annotated_objects"></a>   
## <a name="matching-annotations-with-annotated-objects"></a><span data-ttu-id="a0a21-127">주석이 지정된 개체에 주석 연결</span><span class="sxs-lookup"><span data-stu-id="a0a21-127">Matching Annotations with Annotated Objects</span></span>  
 <span data-ttu-id="a0a21-128">주석을 해당 주석이 지정된 개체와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-128">You can match annotations with the corresponding annotated objects.</span></span> <span data-ttu-id="a0a21-129">예를 들어 주석 창이 있는 간단한 문서 판독기 응용 프로그램을 생각해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-129">For example, consider a simple document reader application that has a comments pane.</span></span> <span data-ttu-id="a0a21-130">주석 창은 문서에 고정된 주석 목록의 텍스트를 표시하는 목록 상자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-130">The comments pane might be a list box that displays the text from a list of annotations that are anchored to a document.</span></span> <span data-ttu-id="a0a21-131">사용자가 목록 상자에서 항목을 선택하면 응용 프로그램에서 해당 주석 개체에 고정된 문서의 단락을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-131">If the user selects an item in the list box, then the application brings into view the paragraph in the document that the corresponding annotation object is anchored to.</span></span>  
  
 <span data-ttu-id="a0a21-132">다음 예제에서는 주석 창으로 사용되는 목록 상자의 이벤트 처리기를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-132">The following example demonstrates how to implement the event handler of such a list box that serves as the comments pane.</span></span>  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 <span data-ttu-id="a0a21-133">다른 예제 시나리오는 주석 및 전자 메일을 통해 문서 독자 간의 스티커 메모를 교환할 수 있도록 하는 응용 프로그램을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-133">Another example scenario involves applications that enable the exchange of annotations and sticky notes between document readers through email.</span></span> <span data-ttu-id="a0a21-134">이러한 응용 프로그램은 이 기능을 통해 판독기에서 교환하는 주석이 포함된 페이지로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a21-134">This feature enables these applications to navigate the reader to the page that contains the annotation that is being exchanged.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a21-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0a21-135">See Also</span></span>  
 <xref:System.Windows.Controls.Primitives.DocumentViewerBase>  
 <xref:System.Windows.Controls.DocumentViewer>  
 <xref:System.Windows.Controls.FlowDocumentPageViewer>  
 <xref:System.Windows.Controls.FlowDocumentScrollViewer>  
 <xref:System.Windows.Controls.FlowDocumentReader>  
 <xref:System.Windows.Annotations.IAnchorInfo>  
 [<span data-ttu-id="a0a21-136">주석 스키마</span><span class="sxs-lookup"><span data-stu-id="a0a21-136">Annotations Schema</span></span>](../../../../docs/framework/wpf/advanced/annotations-schema.md)  
 [<span data-ttu-id="a0a21-137">ContextMenu 개요</span><span class="sxs-lookup"><span data-stu-id="a0a21-137">ContextMenu Overview</span></span>](../../../../docs/framework/wpf/controls/contextmenu-overview.md)  
 [<span data-ttu-id="a0a21-138">명령 개요</span><span class="sxs-lookup"><span data-stu-id="a0a21-138">Commanding Overview</span></span>](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [<span data-ttu-id="a0a21-139">유동 문서 개요</span><span class="sxs-lookup"><span data-stu-id="a0a21-139">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="a0a21-140">방법: MenuItem에 명령 추가</span><span class="sxs-lookup"><span data-stu-id="a0a21-140">How to: Add a Command to a MenuItem</span></span>](http://msdn.microsoft.com/library/013d68a0-5373-4a68-bd91-5de574307370)
