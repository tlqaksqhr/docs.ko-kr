---
title: "방법: TextBox 컨트롤의 텍스트 시작 또는 끝 위치에 커서 놓기"
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
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df30adf232ad782999d8bdf52b1946f84785f98d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a><span data-ttu-id="376b0-102">방법: TextBox 컨트롤의 텍스트 시작 또는 끝 위치에 커서 놓기</span><span class="sxs-lookup"><span data-stu-id="376b0-102">How to: Position the Cursor at the Beginning or End of Text in a TextBox Control</span></span>
<span data-ttu-id="376b0-103">시작 또는 끝의 텍스트 내용 커서 위치를 지정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="376b0-103">This example shows how to position the cursor at the beginning or end of the text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="376b0-104">예</span><span class="sxs-lookup"><span data-stu-id="376b0-104">Example</span></span>  
 <span data-ttu-id="376b0-105">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 코드 설명는 <xref:System.Windows.Controls.TextBox> 제어 하 고 이름을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="376b0-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a <xref:System.Windows.Controls.TextBox> control and assigns it a Name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a><span data-ttu-id="376b0-106">예</span><span class="sxs-lookup"><span data-stu-id="376b0-106">Example</span></span>  
 <span data-ttu-id="376b0-107">내용의의 시작 부분에 커서를 배치 하는 <xref:System.Windows.Controls.TextBox> 컨트롤을 호출 하는 <xref:System.Windows.Controls.TextBox.Select%2A> 메서드 선택 시작 위치 0 및 선택 항목 길이 0 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="376b0-107">To position the cursor at the beginning of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position of 0, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a><span data-ttu-id="376b0-108">예</span><span class="sxs-lookup"><span data-stu-id="376b0-108">Example</span></span>  
 <span data-ttu-id="376b0-109">내용의 끝에 커서를 놓습니다는 <xref:System.Windows.Controls.TextBox> 컨트롤을 호출 하는 <xref:System.Windows.Controls.TextBox.Select%2A> 메서드 콘텐츠, 텍스트의 길이 선택 길이를 0 선택 시작 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="376b0-109">To position the cursor at the end of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position equal to the  length of the text content, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a><span data-ttu-id="376b0-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="376b0-110">See Also</span></span>  
 [<span data-ttu-id="376b0-111">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="376b0-111">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="376b0-112">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="376b0-112">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
