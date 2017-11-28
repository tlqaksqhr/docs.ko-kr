---
title: "방법: 텍스트 잘라내기 사용"
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
- text [WPF], trimming
- documents [WPF], trimmng text
- trimmng text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8f0f24bb6271e63dc50bd063aedfd8185711e7a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-enable-text-trimming"></a><span data-ttu-id="f0b93-102">방법: 텍스트 잘라내기 사용</span><span class="sxs-lookup"><span data-stu-id="f0b93-102">How to: Enable Text Trimming</span></span>
<span data-ttu-id="f0b93-103">사용 및에서 사용할 수 있는 값의 효과 보여 주는이 예제는 <xref:System.Windows.TextTrimming> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="f0b93-103">This example demonstrates the usage and effects of the values available in the <xref:System.Windows.TextTrimming> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0b93-104">예제</span><span class="sxs-lookup"><span data-stu-id="f0b93-104">Example</span></span>  
 <span data-ttu-id="f0b93-105">다음 예제에서는 정의 <xref:System.Windows.Controls.TextBlock> 인 요소는 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 특성이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b93-105">The following example defines a <xref:System.Windows.Controls.TextBlock> element with the <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attribute set.</span></span>  
  
 [!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]  
  
## <a name="example"></a><span data-ttu-id="f0b93-106">예제</span><span class="sxs-lookup"><span data-stu-id="f0b93-106">Example</span></span>  
 <span data-ttu-id="f0b93-107">해당 설정 <xref:System.Windows.TextTrimming> 코드에서 속성은 아래에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b93-107">Setting the corresponding <xref:System.Windows.TextTrimming> property in code is demonstrated below.</span></span>  
  
 [!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
 [!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]  
  
 <span data-ttu-id="f0b93-108">잘라내기의 텍스트에 대 한 현재 세 가지가: **CharacterEllipsis**, **WordEllipsis**, 및 **None**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b93-108">There are currently three options for trimming text: **CharacterEllipsis**, **WordEllipsis**, and **None**.</span></span>  
  
 <span data-ttu-id="f0b93-109">때 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 로 설정 된 **CharacterEllipsis**, 텍스트 자르고 줄임표가 가장자리에 가장 가까운 문자에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b93-109">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **CharacterEllipsis**, text is trimmed and continued with an ellipsis at the character closest to the trimming edge.</span></span>  <span data-ttu-id="f0b93-110">이 설정은 잘리는 경계에 좀 더 가깝게 맞추어 텍스트를 잘라내기 때문에 단어가 부분적으로 잘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b93-110">This setting tends to trim text to fit more closely to the trimming boundary, but may result in words being partially trimmed.</span></span>  <span data-ttu-id="f0b93-111">다음 그림에서이 설정의 효과 보여 줍니다.는 <xref:System.Windows.Controls.TextBlock> 위에 정의 된 것과 비슷한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b93-111">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>  
  
 <span data-ttu-id="f0b93-112">![예: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming_Character")</span><span class="sxs-lookup"><span data-stu-id="f0b93-112">![Example: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming_Character")</span></span>  
  
 <span data-ttu-id="f0b93-113">때 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 로 설정 된 **WordEllipsis**, 텍스트가 잘려 하 고 가장 가까운 가장자리에서 첫 번째 전체 단어의 끝에 줄임표가 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b93-113">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **WordEllipsis**, text is trimmed and continued with an ellipsis at the end of the first full word closest to the trimming edge.</span></span>  <span data-ttu-id="f0b93-114">이 설정은 부분적으로 트리밍된 단어에 표시 되지 것입니다 이지만로 가장자리에서 근접 하 게 텍스트 잘라내기 하지 때문는 **CharacterEllipsis** 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b93-114">This setting will not show partially trimmed words, but tends not to trim text as closely to the trimming edge as the **CharacterEllipsis** setting.</span></span>  <span data-ttu-id="f0b93-115">다음 그림에서이 설정의 효과 보여 줍니다.는 <xref:System.Windows.Controls.TextBlock> 위에 정의 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b93-115">The following figure shows the effect of this setting on the <xref:System.Windows.Controls.TextBlock> defined above.</span></span>  
  
 <span data-ttu-id="f0b93-116">![예: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming_Word")</span><span class="sxs-lookup"><span data-stu-id="f0b93-116">![Example: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming_Word")</span></span>  
  
 <span data-ttu-id="f0b93-117">때 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 로 설정 된 **None**, 텍스트 잘리지 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b93-117">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **None**, no text trimming is performed.</span></span>  <span data-ttu-id="f0b93-118">이 경우 텍스트가 부모 텍스트 컨테이너의 경계로 잘릴 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="f0b93-118">In this case, text is simply cropped to the boundary of the parent text container.</span></span>  <span data-ttu-id="f0b93-119">다음 그림에서이 설정의 효과 보여 줍니다.는 <xref:System.Windows.Controls.TextBlock> 위에 정의 된 것과 비슷한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b93-119">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>  
  
 <span data-ttu-id="f0b93-120">![예제: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming_None")</span><span class="sxs-lookup"><span data-stu-id="f0b93-120">![Example: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming_None")</span></span>
