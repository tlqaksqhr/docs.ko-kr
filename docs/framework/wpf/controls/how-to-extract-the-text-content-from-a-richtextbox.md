---
title: "방법: RichTextBox에서 텍스트 콘텐츠 추출"
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
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f24b71bcb5f013c4b7054dd0948e5f2709230a99
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a><span data-ttu-id="c5ef9-102">방법: RichTextBox에서 텍스트 콘텐츠 추출</span><span class="sxs-lookup"><span data-stu-id="c5ef9-102">How to: Extract the Text Content from a RichTextBox</span></span>
<span data-ttu-id="c5ef9-103">내용을 추출 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.RichTextBox> 일반 텍스트로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ef9-103">This example shows how to extract the contents of a <xref:System.Windows.Controls.RichTextBox> as plain text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5ef9-104">예제</span><span class="sxs-lookup"><span data-stu-id="c5ef9-104">Example</span></span>  
 <span data-ttu-id="c5ef9-105">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 코드 설명 명명 된 <xref:System.Windows.Controls.RichTextBox> 단순 콘텐츠는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="c5ef9-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a><span data-ttu-id="c5ef9-106">예제</span><span class="sxs-lookup"><span data-stu-id="c5ef9-106">Example</span></span>  
 <span data-ttu-id="c5ef9-107">다음 코드를 사용 하는 메서드를 구현 하는 <xref:System.Windows.Controls.RichTextBox> 를 인수로 일반 텍스트 콘텐츠를 나타내는 문자열을 반환 하는 <xref:System.Windows.Controls.RichTextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ef9-107">The following code implements a method that takes a <xref:System.Windows.Controls.RichTextBox> as an argument, and returns a string representing the plain text contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="c5ef9-108">메서드를 새로 만듭니다. <xref:System.Windows.Documents.TextRange> 의 내용에서는 <xref:System.Windows.Controls.RichTextBox>를 사용 하 여는 <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> 및 <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> 추출할 콘텐츠의 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c5ef9-108">The method creates a new <xref:System.Windows.Documents.TextRange> from the contents of the <xref:System.Windows.Controls.RichTextBox>, using the <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> to indicate the range of the contents to extract.</span></span>  <span data-ttu-id="c5ef9-109"><xref:System.Windows.Documents.FlowDocument.ContentStart%2A>및 <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> 각 속성 반환는 <xref:System.Windows.Documents.TextPointer>의 내용을 제공 하는 기본 FlowDocument 액세스할 수 있어야 하 고는 <xref:System.Windows.Controls.RichTextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ef9-109"><xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> properties each return a <xref:System.Windows.Documents.TextPointer>, and are accessible on the underlying FlowDocument that represents the contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  <span data-ttu-id="c5ef9-110"><xref:System.Windows.Documents.TextRange>일반 텍스트 부분을 반환 하는 텍스트 속성을 제공 된 <xref:System.Windows.Documents.TextRange> 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c5ef9-110"><xref:System.Windows.Documents.TextRange> provides a Text property, which returns the plain text portions of the <xref:System.Windows.Documents.TextRange> as a string.</span></span>  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a><span data-ttu-id="c5ef9-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5ef9-111">See Also</span></span>  
 [<span data-ttu-id="c5ef9-112">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="c5ef9-112">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [<span data-ttu-id="c5ef9-113">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="c5ef9-113">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
