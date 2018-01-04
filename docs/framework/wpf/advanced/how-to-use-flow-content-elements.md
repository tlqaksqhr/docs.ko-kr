---
title: "방법: 유동 콘텐츠 요소 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e637e114187d0864afe4211a45c346c1e5a449b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="a25c0-102">방법: 유동 콘텐츠 요소 사용</span><span class="sxs-lookup"><span data-stu-id="a25c0-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="a25c0-103">다음 예제에서는 다양한 유동 콘텐츠 요소 및 연결된 특성에 대한 선언적 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a25c0-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="a25c0-104">여기서 설명하는 요소와 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a25c0-104">Elements and attributes demonstrated include:</span></span>  
  
-   <span data-ttu-id="a25c0-105"><xref:System.Windows.Documents.Bold> 요소</span><span class="sxs-lookup"><span data-stu-id="a25c0-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
-   <span data-ttu-id="a25c0-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> 특성</span><span class="sxs-lookup"><span data-stu-id="a25c0-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
-   <span data-ttu-id="a25c0-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> 특성</span><span class="sxs-lookup"><span data-stu-id="a25c0-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
-   <span data-ttu-id="a25c0-108"><xref:System.Windows.Documents.Italic> 요소</span><span class="sxs-lookup"><span data-stu-id="a25c0-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
-   <span data-ttu-id="a25c0-109"><xref:System.Windows.Documents.LineBreak> 요소</span><span class="sxs-lookup"><span data-stu-id="a25c0-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
-   <span data-ttu-id="a25c0-110"><xref:System.Windows.Documents.List> 요소</span><span class="sxs-lookup"><span data-stu-id="a25c0-110"><xref:System.Windows.Documents.List> element</span></span>  
  
-   <span data-ttu-id="a25c0-111"><xref:System.Windows.Documents.ListItem> 요소</span><span class="sxs-lookup"><span data-stu-id="a25c0-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
-   <span data-ttu-id="a25c0-112"><xref:System.Windows.Documents.Paragraph> 요소</span><span class="sxs-lookup"><span data-stu-id="a25c0-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
-   <span data-ttu-id="a25c0-113"><xref:System.Windows.Documents.Run> 요소</span><span class="sxs-lookup"><span data-stu-id="a25c0-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
-   <span data-ttu-id="a25c0-114"><xref:System.Windows.Documents.Section> 요소</span><span class="sxs-lookup"><span data-stu-id="a25c0-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
-   <span data-ttu-id="a25c0-115"><xref:System.Windows.Documents.Span> 요소</span><span class="sxs-lookup"><span data-stu-id="a25c0-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
-   <span data-ttu-id="a25c0-116"><xref:System.Windows.Documents.Typography.Variants%2A>특성 (위 첨자 및 아래 첨자)</span><span class="sxs-lookup"><span data-stu-id="a25c0-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
-   <span data-ttu-id="a25c0-117"><xref:System.Windows.Documents.Underline> 요소</span><span class="sxs-lookup"><span data-stu-id="a25c0-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="a25c0-118">예</span><span class="sxs-lookup"><span data-stu-id="a25c0-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
