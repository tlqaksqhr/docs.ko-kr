---
title: "방법: TextBox 컨트롤에서 포커스 설정"
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
- focus [WPF], setting
- TextBox control [WPF], setting focus
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe07633e41986e383d5f40dc66c0689a91e33116
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-focus-in-a-textbox-control"></a><span data-ttu-id="2f67f-102">방법: TextBox 컨트롤에서 포커스 설정</span><span class="sxs-lookup"><span data-stu-id="2f67f-102">How to: Set Focus in a TextBox Control</span></span>
<span data-ttu-id="2f67f-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.UIElement.Focus%2A> 에 포커스를 설정 하는 메서드는 <xref:System.Windows.Controls.TextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f67f-103">This example shows how to use the <xref:System.Windows.UIElement.Focus%2A> method to set focus on a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f67f-104">예</span><span class="sxs-lookup"><span data-stu-id="2f67f-104">Example</span></span>  
 <span data-ttu-id="2f67f-105">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제는 간단한 설명 <xref:System.Windows.Controls.TextBox> 라는 컨트롤 *tbFocusMe*</span><span class="sxs-lookup"><span data-stu-id="2f67f-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example describes a simple <xref:System.Windows.Controls.TextBox> control named *tbFocusMe*</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxFocusXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## <a name="example"></a><span data-ttu-id="2f67f-106">예</span><span class="sxs-lookup"><span data-stu-id="2f67f-106">Example</span></span>  
 <span data-ttu-id="2f67f-107">다음 예제에서는 <xref:System.Windows.UIElement.Focus%2A> 에 포커스를 설정 하는 메서드는 <xref:System.Windows.Controls.TextBox> 이름의 *tbFocusMe*합니다.</span><span class="sxs-lookup"><span data-stu-id="2f67f-107">The following example calls the <xref:System.Windows.UIElement.Focus%2A> method to set the focus on the <xref:System.Windows.Controls.TextBox> control with the Name *tbFocusMe*.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## <a name="see-also"></a><span data-ttu-id="2f67f-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f67f-108">See Also</span></span>  
 <xref:System.Windows.UIElement.Focusable%2A>  
 <xref:System.Windows.UIElement.IsFocused%2A>  
 [<span data-ttu-id="2f67f-109">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="2f67f-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="2f67f-110">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="2f67f-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
