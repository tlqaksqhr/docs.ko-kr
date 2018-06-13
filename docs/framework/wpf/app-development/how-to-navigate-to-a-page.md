---
title: '방법: 페이지로 이동'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: 896287376979d40816e3937fff77b38bf71a62f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548391"
---
# <a name="how-to-navigate-to-a-page"></a><span data-ttu-id="48b5f-102">방법: 페이지로 이동</span><span class="sxs-lookup"><span data-stu-id="48b5f-102">How to: Navigate to a Page</span></span>
<span data-ttu-id="48b5f-103">이 예제는 페이지를 탐색할 수 있습니다에서 여러 가지 방법으로 <xref:System.Windows.Navigation.NavigationWindow>합니다.</span><span class="sxs-lookup"><span data-stu-id="48b5f-103">This example illustrates several ways in which a page can be navigated to from a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48b5f-104">예제</span><span class="sxs-lookup"><span data-stu-id="48b5f-104">Example</span></span>  
 <span data-ttu-id="48b5f-105">수는 <xref:System.Windows.Navigation.NavigationWindow> 다음 중 하나를 사용 하 여 페이지를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48b5f-105">It is possible for a <xref:System.Windows.Navigation.NavigationWindow> to navigate to a page using one of the following:</span></span>  
  
-   <span data-ttu-id="48b5f-106"><xref:System.Windows.Navigation.NavigationWindow.Source%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="48b5f-106">The <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property.</span></span>  
  
-   <span data-ttu-id="48b5f-107"><xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="48b5f-107">The <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> method.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)]<span data-ttu-id="48b5f-108"> 상대 또는 절대 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48b5f-108"> can be either relative or absolute.</span></span> <span data-ttu-id="48b5f-109">자세한 내용은 [WPF의 Pack URI](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="48b5f-109">For more information, see [Pack URIs in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48b5f-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48b5f-110">See Also</span></span>  
 <xref:System.Windows.Controls.Frame>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Navigation.NavigationService>
