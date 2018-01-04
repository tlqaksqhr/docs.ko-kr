---
title: "TextBlock 개요"
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
- controls [WPF], TextBlock
- TextBlock control [WPF]
ms.assetid: 24720bca-341a-4b03-8a6b-7a678023b10a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 404f5677bca0df45d4f7dbf689a297499b36bbab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="textblock-overview"></a><span data-ttu-id="e5dd5-102">TextBlock 개요</span><span class="sxs-lookup"><span data-stu-id="e5dd5-102">TextBlock Overview</span></span>
<span data-ttu-id="e5dd5-103"><xref:System.Windows.Controls.TextBlock> 컨트롤에 대 한 유연한 텍스트 지원을 제공 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-103">The <xref:System.Windows.Controls.TextBlock> control provides flexible text support for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="e5dd5-104">두 개 이상의 텍스트 단락이 필요하지 않은 기본 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 시나리오의 경우 요소가 대상으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-104">The element is targeted primarily toward basic [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios that do not require more than one paragraph of text.</span></span> <span data-ttu-id="e5dd5-105">와 같은 프레젠테이션 정확 하 게 제어할 수 있는 속성의 번호를 지원 <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, 및 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-105">It supports a number of properties that enable precise control of presentation, such as <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, and <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>.</span></span> <span data-ttu-id="e5dd5-106">사용 하 여 텍스트 콘텐츠를 추가할 수 있습니다는 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-106">Text content can be added using the <xref:System.Windows.Controls.TextBlock.Text%2A> property.</span></span> <span data-ttu-id="e5dd5-107">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 사용될 경우 여는 태그와 닫는 태그 사이의 콘텐츠는 암시적으로 요소의 텍스트로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-107">When used in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], content between the open and closing tag is implicitly added as the text of the element.</span></span>  
  
 <span data-ttu-id="e5dd5-108">A <xref:System.Windows.Controls.TextBlock> 매우 간단 하 게 사용 하 여 요소를 인스턴스화할 수 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-108">A <xref:System.Windows.Controls.TextBlock> element can be instantiated very simply using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[TextBlockSnip_XAML#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip_XAML/CS/default.xaml#2)]  
  
 <span data-ttu-id="e5dd5-109">마찬가지로, 사용 된 <xref:System.Windows.Controls.TextBlock> 코드의 요소는 비교적 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5dd5-109">Similarly, usage of the <xref:System.Windows.Controls.TextBlock> element in code is relatively simple.</span></span>  
  
 [!code-csharp[TextBlockSnip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip/CSharp/TextBlockSnips.cs#1)]
 [!code-vb[TextBlockSnip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBlockSnip/VisualBasic/TextBlockSnips.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e5dd5-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5dd5-110">See Also</span></span>  
 <xref:System.Windows.Controls.Label>
