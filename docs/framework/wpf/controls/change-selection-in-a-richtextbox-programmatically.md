---
title: "프로그래밍 방식으로 RichTextBox의 선택 변경"
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
- changing selections in a text box [WPF]
- changing selections in a RichTextBox [WPF]
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f645a5719425742ba02f8f9056ca788fd6fdb931
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a><span data-ttu-id="72a09-102">프로그래밍 방식으로 RichTextBox의 선택 변경</span><span class="sxs-lookup"><span data-stu-id="72a09-102">Change Selection in a RichTextBox Programmatically</span></span>
<span data-ttu-id="72a09-103">프로그래밍 방식으로의 현재 선택 영역을 변경 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.RichTextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="72a09-103">This example shows how to programmatically change the current selection in a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="72a09-104">사용자가 사용자 인터페이스를 사용 하 여 콘텐츠를 선택 하는 경우이 옵션을이 선택은 같습니다.</span><span class="sxs-lookup"><span data-stu-id="72a09-104">This selection is the same as if the user had selected the content by using the user interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72a09-105">예</span><span class="sxs-lookup"><span data-stu-id="72a09-105">Example</span></span>  
 <span data-ttu-id="72a09-106">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 코드 설명 명명 된 <xref:System.Windows.Controls.RichTextBox> 단순 콘텐츠는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="72a09-106">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="72a09-107">예</span><span class="sxs-lookup"><span data-stu-id="72a09-107">Example</span></span>  
 <span data-ttu-id="72a09-108">다음 코드는 프로그래밍 방식으로 몇 가지 임의의 텍스트를 선택 내부를 클릭할 때는 <xref:System.Windows.Controls.RichTextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="72a09-108">The following code programmatically selects some arbitrary text when the user clicks inside the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="72a09-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72a09-109">See Also</span></span>  
 [<span data-ttu-id="72a09-110">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="72a09-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [<span data-ttu-id="72a09-111">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="72a09-111">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
