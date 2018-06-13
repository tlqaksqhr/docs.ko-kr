---
title: '방법: RichTextBox에서 텍스트 콘텐츠 추출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
ms.openlocfilehash: 309fe15c76c17a79e11341f3a50c0bf5a7a2cc21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553938"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a>방법: RichTextBox에서 텍스트 콘텐츠 추출
내용을 추출 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.RichTextBox> 일반 텍스트로 합니다.  
  
## <a name="example"></a>예제  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 코드 설명 명명 된 <xref:System.Windows.Controls.RichTextBox> 단순 콘텐츠는 컨트롤입니다.  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a>예제  
 다음 코드를 사용 하는 메서드를 구현 하는 <xref:System.Windows.Controls.RichTextBox> 를 인수로 일반 텍스트 콘텐츠를 나타내는 문자열을 반환 하는 <xref:System.Windows.Controls.RichTextBox>합니다.  
  
 메서드를 새로 만듭니다. <xref:System.Windows.Documents.TextRange> 의 내용에서는 <xref:System.Windows.Controls.RichTextBox>를 사용 하 여는 <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> 및 <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> 추출할 콘텐츠의 범위를 나타냅니다.  <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> 및 <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> 각 속성 반환는 <xref:System.Windows.Documents.TextPointer>의 내용을 제공 하는 기본 FlowDocument 액세스할 수 있어야 하 고는 <xref:System.Windows.Controls.RichTextBox>합니다.  <xref:System.Windows.Documents.TextRange> 일반 텍스트 부분을 반환 하는 텍스트 속성을 제공 된 <xref:System.Windows.Documents.TextRange> 문자열입니다.  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a>참고 항목  
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)
