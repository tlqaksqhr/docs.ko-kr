---
title: "방법: 여러 줄 TextBox 컨트롤 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2a6885a594e5fcd747f85dedf1afbd39ec644717
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-multiline-textbox-control"></a><span data-ttu-id="2e8e0-102">방법: 여러 줄 TextBox 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="2e8e0-102">How to: Create a Multiline TextBox Control</span></span>
<span data-ttu-id="2e8e0-103">사용 하는 방법을 보여 주는이 예제 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 정의 하는 <xref:System.Windows.Controls.TextBox> 컨트롤을 여러 줄의 텍스트를 수용 하기 위해 자동으로 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e8e0-103">This example shows how to use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.TextBox> control that will automatically expand to accommodate multiple lines of text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e8e0-104">예</span><span class="sxs-lookup"><span data-stu-id="2e8e0-104">Example</span></span>  
 <span data-ttu-id="2e8e0-105">설정의 <xref:System.Windows.Controls.TextBox.TextWrapping%2A> 특성을 **줄 바꿈** 입력 한 텍스트를 배치할 새 하면 경우 줄의 가장자리는 <xref:System.Windows.Controls.TextBox> 컨트롤은에 도달 하면 자동으로 확장 되는 <xref:System.Windows.Controls.TextBox> 경우 새 줄을 위한 공간을 포함 하도록 컨트롤 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e8e0-105">Setting the <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attribute to **Wrap** will cause entered text to wrap to a new line when the edge of the <xref:System.Windows.Controls.TextBox> control is reached, automatically expanding the <xref:System.Windows.Controls.TextBox> control to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="2e8e0-106">설정의 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> 특성을 **true** 다시 한 번 자동으로 확장 되 RETURN 키를 누를 때 삽입할 새 줄의 <xref:System.Windows.Controls.TextBox> 필요 하면 새 줄을 위한 공간을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e8e0-106">Setting the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attribute to **true** causes a new line to be inserted when the RETURN key is pressed, once again automatically expanding the <xref:System.Windows.Controls.TextBox> to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="2e8e0-107"><xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> 스크롤 막대를 추가 하는 특성은 <xref:System.Windows.Controls.TextBox>되도록의 내용을 <xref:System.Windows.Controls.TextBox> if 스크롤할 수는 <xref:System.Windows.Controls.TextBox> 프레임 또는 포함 하는 창의 크기를 넘어 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e8e0-107">The <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attribute adds a scroll bar to the <xref:System.Windows.Controls.TextBox>, so that the contents of the <xref:System.Windows.Controls.TextBox> can be scrolled through if the <xref:System.Windows.Controls.TextBox> expands beyond the size of the frame or window that encloses it.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="2e8e0-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e8e0-108">See Also</span></span>  
 <xref:System.Windows.TextWrapping>  
 [<span data-ttu-id="2e8e0-109">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="2e8e0-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="2e8e0-110">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="2e8e0-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
