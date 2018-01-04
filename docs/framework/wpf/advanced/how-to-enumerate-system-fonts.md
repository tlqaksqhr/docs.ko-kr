---
title: "방법: 시스템 글꼴 열거"
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
- typography [WPF], enumerating system fonts
- fonts [WPF], enumerating
- system fonts [WPF], enumerating
- enumerating [WPF], system fonts
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf917dc2af256cdd0f3a0c579f86847e1bf4f1e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enumerate-system-fonts"></a><span data-ttu-id="1785c-102">방법: 시스템 글꼴 열거</span><span class="sxs-lookup"><span data-stu-id="1785c-102">How to: Enumerate System Fonts</span></span>
## <a name="example"></a><span data-ttu-id="1785c-103">예</span><span class="sxs-lookup"><span data-stu-id="1785c-103">Example</span></span>  
 <span data-ttu-id="1785c-104">다음 예제에서는 시스템 글꼴 컬렉션에서 글꼴을 열거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1785c-104">The following example shows how to enumerate the fonts in the system font collection.</span></span> <span data-ttu-id="1785c-105">각각의 글꼴 패밀리 이름을 <xref:System.Windows.Media.FontFamily> 내 <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> 콤보 상자에 항목으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1785c-105">The font family name of each <xref:System.Windows.Media.FontFamily> within <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> is added as an item to a combo box.</span></span>  
  
 [!code-csharp[TextOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 <span data-ttu-id="1785c-106">같은 디렉터리에 있는 여러 버전의 동일한 글꼴 패밀리는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 글꼴 열거형 글꼴의 가장 최신 버전을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1785c-106">If multiple versions of the same font family reside in the same directory, the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] font enumeration returns the most recent version of the font.</span></span> <span data-ttu-id="1785c-107">버전 정보 확인을 제공 하지 않는 경우 최신 타임 스탬프가 있는 글꼴 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1785c-107">If the version information does not provide resolution, the font with latest timestamp is returned.</span></span> <span data-ttu-id="1785c-108">타임 스탬프 정보를 해당 하는 경우에 알파벳 순서로 첫 번째 글꼴 파일이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1785c-108">If the timestamp information is equivalent, the font file that is first in alphabetical order is returned.</span></span>
