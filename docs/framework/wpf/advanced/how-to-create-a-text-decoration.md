---
title: '방법: 텍스트 장식 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
ms.openlocfilehash: c16073dd2413c1258f4875ac4118e0656d29b171
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545411"
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="0d2a3-102">방법: 텍스트 장식 만들기</span><span class="sxs-lookup"><span data-stu-id="0d2a3-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="0d2a3-103">A <xref:System.Windows.TextDecoration> 개체는 시각적 장식 텍스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="0d2a3-104">텍스트 장식의 네 가지가: 밑줄, 초기, 취소선 및 윗줄 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="0d2a3-105">다음 예제에서는 텍스트를 기준으로 텍스트 장식의 위치를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 <span data-ttu-id="0d2a3-106">![텍스트 장식 위치의 다이어그램](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")</span><span class="sxs-lookup"><span data-stu-id="0d2a3-106">![Diagram of text decoration locations](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")</span></span>  
<span data-ttu-id="0d2a3-107">텍스트 장식의 종류의 예</span><span class="sxs-lookup"><span data-stu-id="0d2a3-107">Example of text decoration types</span></span>  
  
 <span data-ttu-id="0d2a3-108">텍스트 장식 텍스트를 추가 하려면 만듭니다는 <xref:System.Windows.TextDecoration> 개체 및 해당 속성을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-108">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="0d2a3-109">사용 하 여는 <xref:System.Windows.TextDecoration.Location%2A> 속성을 통해 밑줄 등 텍스트 장식이 나타나는 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-109">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="0d2a3-110">사용 된 <xref:System.Windows.TextDecoration.Pen%2A> 텍스트 장식 단색 또는 그라데이션 색 등의 모양을 지정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-110">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="0d2a3-111">에 대 한 값을 지정 하지 않으면는 <xref:System.Windows.TextDecoration.Pen%2A> 속성에 텍스트와 동일한 색으로 장식의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-111">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="0d2a3-112">정의 하 고 나면는 <xref:System.Windows.TextDecoration> 개체를 추가 하는 <xref:System.Windows.TextDecorations> 원하는 텍스트 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-112">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="0d2a3-113">다음 예제에서는 선형 그라데이션 브러시 및 펜 파선된으로 스타일이 지정 된 텍스트 장식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-113">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 <span data-ttu-id="0d2a3-114">![선형 그라데이션 밑줄로 텍스트 장식](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")</span><span class="sxs-lookup"><span data-stu-id="0d2a3-114">![Text decoration with linear gradient underline](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")</span></span>  
<span data-ttu-id="0d2a3-115">선형 그라데이션으로 스타일이 지정 된 밑줄의 예 파선된 펜 및 브러시</span><span class="sxs-lookup"><span data-stu-id="0d2a3-115">Example of an underline styled with a linear gradient brush and dashed pen</span></span>  
  
 <span data-ttu-id="0d2a3-116"><xref:System.Windows.Documents.Hyperlink> 개체는 유동 콘텐츠 내에서 하이퍼링크를 호스팅할 수 있도록 하는 인라인 수준의 유동 콘텐츠 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-116">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="0d2a3-117">기본적으로 <xref:System.Windows.Documents.Hyperlink> 사용 하 여 한 <xref:System.Windows.TextDecoration> 밑줄을 표시 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-117">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="0d2a3-118"><xref:System.Windows.TextDecoration> 특히 많은 경우 개체를 인스턴스화할 때 성능이 저하 될 수 있습니다 <xref:System.Windows.Documents.Hyperlink> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-118"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="0d2a3-119">광범위 하 게 사용의 경우 <xref:System.Windows.Documents.Hyperlink> 요소를 만들려는 경우와 같은 이벤트 트리거될 때만 밑줄이 표시 된 <xref:System.Windows.ContentElement.MouseEnter> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-119">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="0d2a3-120">다음 예제에서는 "My MSN" 링크의 밑줄은 동적-만 표시 될 때는 <xref:System.Windows.ContentElement.MouseEnter> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-120">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 <span data-ttu-id="0d2a3-121">![Textdecoration을 표시 하는 하이퍼링크](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span><span class="sxs-lookup"><span data-stu-id="0d2a3-121">![Hyperlinks displaying TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span></span>  
<span data-ttu-id="0d2a3-122">TextDecorations를 사용 하 여 정의 되는 하이퍼링크</span><span class="sxs-lookup"><span data-stu-id="0d2a3-122">Hyperlinks defined with TextDecorations</span></span>  
  
 <span data-ttu-id="0d2a3-123">자세한 내용은 [하이퍼링크에 밑줄이 그어지는지 여부 지정](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-123">For more information, see [Specify Whether a Hyperlink is Underlined](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d2a3-124">예제</span><span class="sxs-lookup"><span data-stu-id="0d2a3-124">Example</span></span>  
 <span data-ttu-id="0d2a3-125">다음 코드 예제에서는 밑줄 텍스트 장식을 글꼴의 기본값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-125">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="0d2a3-126">다음 코드 예제에서는 밑줄 텍스트 장식은 펜 단색 브러시를 사용한 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-126">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="0d2a3-127">다음 코드 예제에서는 밑줄 텍스트 장식은 파선 펜 선형 그라데이션 브러시로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0d2a3-127">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="0d2a3-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d2a3-128">See Also</span></span>  
 <xref:System.Windows.TextDecoration>  
 <xref:System.Windows.Documents.Hyperlink>  
 [<span data-ttu-id="0d2a3-129">하이퍼링크에 밑줄이 그어지는지 여부 지정</span><span class="sxs-lookup"><span data-stu-id="0d2a3-129">Specify Whether a Hyperlink is Underlined</span></span>](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)
