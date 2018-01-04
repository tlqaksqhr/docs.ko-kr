---
title: "방법: 텍스트 선택 검색"
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
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32be79811de4b8056449c2c6d6c53eca8cc063f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-retrieve-a-text-selection"></a><span data-ttu-id="19200-102">방법: 텍스트 선택 검색</span><span class="sxs-lookup"><span data-stu-id="19200-102">How to: Retrieve a Text Selection</span></span>
<span data-ttu-id="19200-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TextBox.SelectedText%2A> 속성에서 사용자가 선택한 텍스트를 검색할는 <xref:System.Windows.Controls.TextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="19200-103">This example shows one way to use the <xref:System.Windows.Controls.TextBox.SelectedText%2A> property to retrieve text that the user has selected in a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19200-104">예</span><span class="sxs-lookup"><span data-stu-id="19200-104">Example</span></span>  
 <span data-ttu-id="19200-105">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 의 정의 표시 하는 예제는 <xref:System.Windows.Controls.TextBox> 를 선택 하려면 몇 가지 텍스트가 포함 된 컨트롤 및 <xref:System.Windows.Controls.Button> 지정한 <xref:System.Windows.Controls.Button.OnClick%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="19200-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example shows the definition of a <xref:System.Windows.Controls.TextBox> control that contains some text to select, and a <xref:System.Windows.Controls.Button> control with a specified <xref:System.Windows.Controls.Button.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="19200-106">이 예제에서는 관련 된 단추 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기는 텍스트 선택 항목을 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19200-106">In this example, a button with an associated <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler is used to retrieve the text selection.</span></span> <span data-ttu-id="19200-107">사용자가 단추를 클릭할 때는 <xref:System.Windows.Controls.Button.OnClick%2A> 메서드는 문자열에 텍스트 상자에 선택한 모든 텍스트를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="19200-107">When the user clicks the button, the <xref:System.Windows.Controls.Button.OnClick%2A> method copies any selected text in the textbox into a string.</span></span> <span data-ttu-id="19200-108">텍스트 선택 영역이 검색 하 (단추 클릭) 뿐만 아니라 다양 한 시나리오에 맞게 쉽게 수정할 수 있습니다 (텍스트 선택 항목을 문자열로 복사)는 해당 선택으로 수행 되는 작업 하는 특별 한 상황이 합니다.</span><span class="sxs-lookup"><span data-stu-id="19200-108">The particular circumstances by which the text selection is retrieved (clicking a button), as well as the action taken with that selection (copying the text selection to a string), can easily be modified to accommodate a wide variety of scenarios.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a><span data-ttu-id="19200-109">예</span><span class="sxs-lookup"><span data-stu-id="19200-109">Example</span></span>  
 <span data-ttu-id="19200-110">다음 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] 보여 주는 예제는 <xref:System.Windows.Controls.Button.OnClick%2A> 에 정의 된 단추에 대 한 이벤트 처리기는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 이 예제에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="19200-110">The following [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] example shows an <xref:System.Windows.Controls.Button.OnClick%2A> event handler for the button defined in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for this example.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a><span data-ttu-id="19200-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19200-111">See Also</span></span>  
 [<span data-ttu-id="19200-112">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="19200-112">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="19200-113">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="19200-113">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
