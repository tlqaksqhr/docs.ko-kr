---
title: "방법: 페이지에서 창의 너비를 설정 합니다."
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc9843d4a0f76547b76698a9686b5c4936baa322
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a><span data-ttu-id="a88e1-102">방법: 페이지에서 창의 너비를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88e1-102">How to: Set the Width of a Window from a Page</span></span>
<span data-ttu-id="a88e1-103">창의 너비를 설정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Page>합니다.</span><span class="sxs-lookup"><span data-stu-id="a88e1-103">This example illustrates how to set the width of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a88e1-104">예</span><span class="sxs-lookup"><span data-stu-id="a88e1-104">Example</span></span>  
 <span data-ttu-id="a88e1-105">A <xref:System.Windows.Controls.Page> 설정 하 여 해당 호스트 창의 너비를 설정할 수 <xref:System.Windows.Controls.Page.WindowWidth%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="a88e1-105">A <xref:System.Windows.Controls.Page> can set the width of its host window by setting <xref:System.Windows.Controls.Page.WindowWidth%2A>.</span></span> <span data-ttu-id="a88e1-106">이 속성을 사용 하면는 <xref:System.Windows.Controls.Page> 에 없는 다음 호스팅하고 있는 창의 형식을 정확 하 게 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a88e1-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a88e1-107">사용 하 여 창을의 너비를 설정 하려면 <xref:System.Windows.Controls.Page.WindowWidth%2A>, <xref:System.Windows.Controls.Page> 창의 자식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88e1-107">To set the width of a window using <xref:System.Windows.Controls.Page.WindowWidth%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
