---
title: "방법: RichTextBox 콘텐츠 저장, 로드 및 인쇄"
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
- saving RichTextBox controls [WPF]
- printing RichTextBox controls [WPF]
- loading RichTextBox controls [WPF]
- RichTextBox control [WPF], saving
- RichTextBox control [WPF], printing
- RichTextBox control [WPF], loading
ms.assetid: ffb113d3-c68a-47ca-8ac0-882283f38326
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ca969848ae82d567642cd0f4174c52ebc24ef5d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-save-load-and-print-richtextbox-content"></a><span data-ttu-id="e3e20-102">방법: RichTextBox 콘텐츠 저장, 로드 및 인쇄</span><span class="sxs-lookup"><span data-stu-id="e3e20-102">How to: Save, Load, and Print RichTextBox Content</span></span>
<span data-ttu-id="e3e20-103">내용을 저장 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.RichTextBox> 로드에 다시 해당 파일에 <xref:System.Windows.Controls.RichTextBox>, 내용을 인쇄 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e20-103">The following example shows how to save content of a <xref:System.Windows.Controls.RichTextBox> to a file, load that content back into the <xref:System.Windows.Controls.RichTextBox>, and print the contents.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3e20-104">예제</span><span class="sxs-lookup"><span data-stu-id="e3e20-104">Example</span></span>  
 <span data-ttu-id="e3e20-105">예제에 대한 태그는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e20-105">Below is the markup for the example.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="e3e20-106">예제</span><span class="sxs-lookup"><span data-stu-id="e3e20-106">Example</span></span>  
 <span data-ttu-id="e3e20-107">예제에 대한 코드 숨김은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e20-107">Below is the code behind for the example.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e3e20-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3e20-108">See Also</span></span>  
 [<span data-ttu-id="e3e20-109">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="e3e20-109">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [<span data-ttu-id="e3e20-110">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="e3e20-110">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
