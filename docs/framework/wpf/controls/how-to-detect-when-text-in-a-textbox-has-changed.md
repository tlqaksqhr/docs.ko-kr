---
title: "방법: TextBox에서 텍스트가 변경되는 시점 감지"
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
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 92fc8995ab75cc25bac3bb21b1646052822c3721
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="d9cc9-102">방법: TextBox에서 텍스트가 변경되는 시점 감지</span><span class="sxs-lookup"><span data-stu-id="d9cc9-102">How to: Detect When Text in a TextBox Has Changed</span></span>
<span data-ttu-id="d9cc9-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 메서드를 실행 하는 이벤트 때마다의 텍스트는 <xref:System.Windows.Controls.TextBox> 컨트롤이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-103">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>  
  
 <span data-ttu-id="d9cc9-104">에 대 한 코드 숨김 클래스에는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 를 포함 하는 <xref:System.Windows.Controls.TextBox> 변경 내용을 모니터링 하려면 컨트롤 삽입 메서드를 호출할 때마다는 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-104">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="d9cc9-105">이 메서드에 의해 실행 되는 것을 일치 하는 서명이 있어야 합니다.는 <xref:System.Windows.Controls.TextChangedEventHandler> 위임 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-105">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 <span data-ttu-id="d9cc9-106">이벤트 처리기가 호출 될 때마다 내용의 <xref:System.Windows.Controls.TextBox> 컨트롤 사용자가 또는 프로그래밍 방식으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-106">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="d9cc9-107">**참고:** 이 이벤트가 발생할 때의 <xref:System.Windows.Controls.TextBox> 컨트롤이 만들어지고 처음 텍스트가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-107">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9cc9-108">예제</span><span class="sxs-lookup"><span data-stu-id="d9cc9-108">Example</span></span>  
 <span data-ttu-id="d9cc9-109">에 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 정의 하는 프로그램 <xref:System.Windows.Controls.TextBox> 을 제어는 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트 처리기 메서드 이름과 일치 하는 값을 가진 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-109">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextChangedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## <a name="example"></a><span data-ttu-id="d9cc9-110">예제</span><span class="sxs-lookup"><span data-stu-id="d9cc9-110">Example</span></span>  
 <span data-ttu-id="d9cc9-111">에 대 한 코드 숨김 클래스에는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 를 포함 하는 <xref:System.Windows.Controls.TextBox> 변경 내용을 모니터링 하려면 컨트롤 삽입 메서드를 호출할 때마다는 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-111">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="d9cc9-112">이 메서드에 의해 실행 되는 것을 일치 하는 서명이 있어야 합니다.는 <xref:System.Windows.Controls.TextChangedEventHandler> 위임 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-112">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 <span data-ttu-id="d9cc9-113">이벤트 처리기가 호출 될 때마다 내용의 <xref:System.Windows.Controls.TextBox> 컨트롤 사용자가 또는 프로그래밍 방식으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-113">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="d9cc9-114">**참고:** 이 이벤트가 발생할 때의 <xref:System.Windows.Controls.TextBox> 컨트롤이 만들어지고 처음 텍스트가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="d9cc9-114">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
 <span data-ttu-id="d9cc9-115">설명</span><span class="sxs-lookup"><span data-stu-id="d9cc9-115">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9cc9-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9cc9-116">See Also</span></span>  
 <xref:System.Windows.Controls.TextChangedEventArgs>  
 [<span data-ttu-id="d9cc9-117">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="d9cc9-117">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="d9cc9-118">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="d9cc9-118">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
