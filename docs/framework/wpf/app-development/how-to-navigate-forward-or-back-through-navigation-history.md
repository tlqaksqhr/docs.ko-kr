---
title: '방법: 탐색 기록을 앞으로 또는 뒤로 탐색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: ac3b8b71b6adf04d71cf35edbb042b82c57d8e1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a>방법: 탐색 기록을 앞으로 또는 뒤로 탐색
이 예제에는 앞으로 또는 뒤로 탐색 기록의 항목을 탐색 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 내용을 사용 하 여 다음과 같은 호스트에서 실행 되는 코드 탐색 기록, 한 번에 하나의 항목을 통해 앞 이나 뒤로 탐색할 수 있습니다.  
  
-   <xref:System.Windows.Navigation.NavigationWindow> 사용 하 여 <xref:System.Windows.Navigation.NavigationService>  
  
-   <xref:System.Windows.Controls.Frame> 사용 하 여 <xref:System.Windows.Navigation.NavigationService>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 한 항목 앞으로 탐색 하려면 먼저 체크 해야를 검사 하 여 앞으로 탐색 기록에서 항목이 있는지는 **CanGoForward** 속성입니다. 한 항목 앞으로 탐색 하려면 호출는 **GoForward** 메서드. 이 다음 예에서 확인할 수 있습니다.  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 한 항목 뒤로 탐색 하려면, 검사 하 여 뒤로 탐색 기록의 항목이 있는지를 먼저 확인 해야 합니다는 **CanGoBack** 속성입니다. 한 항목 뒤로 탐색 하려면 호출는 **GoBack** 메서드. 이 다음 예에서 확인할 수 있습니다.  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**, **GoForward**, **CanGoBack**, 및 **GoBack** 구현 <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, 및 <xref:System.Windows.Navigation.NavigationService>합니다.  
  
> [!NOTE]
>  호출 하는 경우 **GoForward**, 앞으로 탐색 기록의 항목이 고 호출 하는 경우 또는 **GoBack**를 뒤로 탐색 기록의 항목이 고는 <xref:System.InvalidOperationException> throw 됩니다.
