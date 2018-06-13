---
title: '방법: 텍스트 입력 체계 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting Typography attributes [WPF]
- Typography attribute [WPF], setting
ms.assetid: 19a3b49b-60a2-4c11-a786-e26b4c965588
ms.openlocfilehash: fcc9c894970934bb5a69debef2f4e38297f82198
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542931"
---
# <a name="how-to-alter-the-typography-of-text"></a><span data-ttu-id="66831-102">방법: 텍스트 입력 체계 변경</span><span class="sxs-lookup"><span data-stu-id="66831-102">How-to: Alter the Typography of Text</span></span>
<span data-ttu-id="66831-103">설정 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Documents.TextElement.Typography%2A> 특성을 사용 하 여 <xref:System.Windows.Documents.Paragraph> 예제 요소로 합니다.</span><span class="sxs-lookup"><span data-stu-id="66831-103">The following example shows how to set the <xref:System.Windows.Documents.TextElement.Typography%2A> attribute, using <xref:System.Windows.Documents.Paragraph> as the example element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66831-104">예제</span><span class="sxs-lookup"><span data-stu-id="66831-104">Example</span></span>  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 <span data-ttu-id="66831-105">다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="66831-105">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="66831-106">![스크린 샷: 입력 체계가 변경된 텍스트](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement_Typog")</span><span class="sxs-lookup"><span data-stu-id="66831-106">![Screenshot: Text with altered typography](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement_Typog")</span></span>  
  
 <span data-ttu-id="66831-107">반면 다음 그림은 기본 입력 체계 속성이 있는 비슷한 예제가 렌더링되는 방식을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="66831-107">In contrast, the following figure shows how a similar example with default typographic properties renders.</span></span>  
  
 <span data-ttu-id="66831-108">![스크린 샷: 입력 체계가 변경된 텍스트](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement_Typog_Default")</span><span class="sxs-lookup"><span data-stu-id="66831-108">![Screenshot: Text with altered typography](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement_Typog_Default")</span></span>  
  
## <a name="example"></a><span data-ttu-id="66831-109">예제</span><span class="sxs-lookup"><span data-stu-id="66831-109">Example</span></span>  
 <span data-ttu-id="66831-110">설정 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.TextBox.Typography%2A> 속성 프로그래밍 방식으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="66831-110">The following example shows how to set the <xref:System.Windows.Controls.TextBox.Typography%2A> property programmatically.</span></span>  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## <a name="see-also"></a><span data-ttu-id="66831-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66831-111">See Also</span></span>  
 [<span data-ttu-id="66831-112">유동 문서 개요</span><span class="sxs-lookup"><span data-stu-id="66831-112">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)
