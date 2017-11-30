---
title: "방법: 텍스트 편집 컨트롤에서 맞춤법 검사 사용"
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
- spellchecking [WPF]
- real-time spellchecking
- TextBox control [WPF], real-time spellchecking
- spelling checker [WPF]
- checking spelling [WPF]
ms.assetid: 6f953d2b-67e8-4012-84ce-53c0e958da47
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e70bbe3b4d3656001af23108b2f76b40d2887318
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-spell-checking-in-a-text-editing-control"></a><span data-ttu-id="64748-102">방법: 텍스트 편집 컨트롤에서 맞춤법 검사 사용</span><span class="sxs-lookup"><span data-stu-id="64748-102">How to: Enable Spell Checking in a Text Editing Control</span></span>
<span data-ttu-id="64748-103">실시간 맞춤법 검사 사용할 수 있도록 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.TextBox> 를 사용 하 여는 <xref:System.Windows.Controls.SpellCheck.IsEnabled%2A> 의 속성은 <xref:System.Windows.Controls.SpellCheck> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="64748-103">The following example shows how to enable real-time spell checking in a <xref:System.Windows.Controls.TextBox> by using the <xref:System.Windows.Controls.SpellCheck.IsEnabled%2A> property of the <xref:System.Windows.Controls.SpellCheck> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64748-104">예제</span><span class="sxs-lookup"><span data-stu-id="64748-104">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellCheckExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/spellcheckexample.xaml#spellcheckexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_procedural_snip#SpellCheckCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_procedural_snip/CSharp/SpellCheckExample.cs#spellcheckcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_procedural_snip#SpellCheckCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_procedural_snip/visualbasic/spellcheckexample.vb#spellcheckcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="64748-105">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64748-105">See Also</span></span>  
 [<span data-ttu-id="64748-106">상황에 맞는 메뉴로 맞춤법 검사 사용</span><span class="sxs-lookup"><span data-stu-id="64748-106">Use Spell Checking with a Context Menu</span></span>](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)  
 [<span data-ttu-id="64748-107">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="64748-107">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="64748-108">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="64748-108">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
