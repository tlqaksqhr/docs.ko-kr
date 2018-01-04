---
title: "방법: RichTextBox 컨트롤에 끌어 놓은 파일 열기"
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
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7dfb5f0f442b18159c18a6e5345f6757674fbb90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a><span data-ttu-id="b5731-102">방법: RichTextBox 컨트롤에 끌어 놓은 파일 열기</span><span class="sxs-lookup"><span data-stu-id="b5731-102">How to: Open a File That is Dropped on a RichTextBox Control</span></span>
<span data-ttu-id="b5731-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, 및 <xref:System.Windows.Documents.FlowDocument> 컨트롤은 모두 기능이 기본 제공 끌어서 놓기.</span><span class="sxs-lookup"><span data-stu-id="b5731-103">In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], the <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> controls all have built-in drag-and-drop functionality.</span></span> <span data-ttu-id="b5731-104">기본 제공 기능 컨트롤 간의 텍스트 내에서 끌어서 놓기 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5731-104">The built-in functionality enables drag-and-drop of text within and between the controls.</span></span> <span data-ttu-id="b5731-105">그러나 컨트롤에 파일을 삭제 하 여 파일을 열 수 없습니다 것.</span><span class="sxs-lookup"><span data-stu-id="b5731-105">However, it does not enable opening a file by dropping the file on the control.</span></span> <span data-ttu-id="b5731-106">이러한 제어는 또한 처리 된 것으로 끌어서 놓기 이벤트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5731-106">These controls also mark the drag-and-drop events as handled.</span></span> <span data-ttu-id="b5731-107">결과적으로, 기본적으로 삭제 된 파일을 여는 기능을 제공 하는 고유한 이벤트 처리기를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b5731-107">As a result, by default, you cannot add your own event handlers to provide functionality to open dropped files.</span></span>  
  
 <span data-ttu-id="b5731-108">이러한 컨트롤에서 끌어서 놓기 이벤트에 대 한 추가 처리를 추가 하려면 사용 된 <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> 메서드를 끌어서 놓기 이벤트에 대 한 이벤트 처리기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5731-108">To add additional handling for drag-and-drop events in these controls, use the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method to add your event handlers for the drag-and-drop events.</span></span> <span data-ttu-id="b5731-109">설정의 `handledEventsToo` 매개 변수를 `true` 지정된 된 처리기 이벤트 경로 따라 다른 요소에 의해 처리 된 것으로 이미 표시 된 라우트된 이벤트에 대해 호출할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5731-109">Set the `handledEventsToo` parameter to `true` to have the specified handler be invoked for a routed event that has already been marked as handled by another element along the event route.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="b5731-110">기본 제공 끌어서 놓기 기능을 바꿀 수 <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, 및 <xref:System.Windows.Documents.FlowDocument> 미리 보기 버전의 끌어서 놓기 이벤트를 처리 하 고 처리 된 것으로 미리 보기 이벤트를 표시 함으로써 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5731-110">You can replace the built-in drag-and-drop functionality of <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> by handling the preview versions of the drag-and-drop events and marking the preview events as handled.</span></span> <span data-ttu-id="b5731-111">그러나이 기본 제공 끌어서 놓기 기능을 사용할 수 없게 않으며 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5731-111">However, this will disable the built-in drag-and-drop functionality, and is not recommended.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5731-112">예</span><span class="sxs-lookup"><span data-stu-id="b5731-112">Example</span></span>  
 <span data-ttu-id="b5731-113">다음 예제에 대 한 처리기를 추가 하는 방법을 보여 줍니다는 <xref:System.Windows.DragDrop.DragOver> 및 <xref:System.Windows.DragDrop.Drop> 이벤트에는 <xref:System.Windows.Controls.RichTextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="b5731-113">The following example demonstrates how to add handlers for the <xref:System.Windows.DragDrop.DragOver> and <xref:System.Windows.DragDrop.Drop> events on a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="b5731-114">사용 하 여이 예제는 <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> 메서드 및 집합은 `handledEventsToo` 매개 변수를 `true` 이벤트 처리기도 호출 될 수 있도록는 <xref:System.Windows.Controls.RichTextBox> 처리 된 것으로 이러한 이벤트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5731-114">This example uses the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method and sets the `handledEventsToo` parameter to `true` so that the events handlers will be invoked even though the <xref:System.Windows.Controls.RichTextBox> marks these events as handled.</span></span> <span data-ttu-id="b5731-115">이벤트 처리기의 코드에서 삭제 된 텍스트 파일을 열 기능을 추가 <xref:System.Windows.Controls.RichTextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="b5731-115">The code in the event handlers adds functionality to open a text file that is dropped on the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="b5731-116">이 예제를 테스트 하려면 텍스트 파일 또는 서식 있는 텍스트 RTF (형식) 파일 탐색기에서 끌어 Windows에는 <xref:System.Windows.Controls.RichTextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="b5731-116">To test this example, drag a text file or a rich text format (RTF) file from Windows Explorer to the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="b5731-117">파일을 열면 됩니다는 <xref:System.Windows.Controls.RichTextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="b5731-117">The file will be opened in the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="b5731-118">삭제 전에 SHIFT 키를 누를 경우 파일을 일반 텍스트로 파일이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b5731-118">If you press the SHIFT key before the dropping the file, the file will be opened as plain text.</span></span>  
  
 [!code-xaml[DragDropSnippets#RtbXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
