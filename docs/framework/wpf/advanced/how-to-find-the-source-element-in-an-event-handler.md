---
title: "방법: 이벤트 처리기에서 소스 요소 찾기"
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
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d62d657b886b867481088e32fe1dd0614377e146
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="cb67d-102">방법: 이벤트 처리기에서 소스 요소 찾기</span><span class="sxs-lookup"><span data-stu-id="cb67d-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="cb67d-103">이 예제에는 이벤트 처리기에서 원본 요소를 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb67d-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb67d-104">예</span><span class="sxs-lookup"><span data-stu-id="cb67d-104">Example</span></span>  
 <span data-ttu-id="cb67d-105">다음 예제에서는 한 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 코드 숨김 파일에 선언 된 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="cb67d-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="cb67d-106">처리기에 연결 되어 있는 단추를 클릭 처리기 속성 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb67d-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="cb67d-107">처리기 코드를 사용 하 여는 <xref:System.Windows.RoutedEventArgs.Source%2A> 변경 하는 이벤트 인수에서 보고 되는 라우트된 이벤트 데이터의 <xref:System.Windows.FrameworkElement.Width%2A> 속성 값에는 <xref:System.Windows.RoutedEventArgs.Source%2A> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cb67d-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="cb67d-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb67d-108">See Also</span></span>  
 <xref:System.Windows.RoutedEventArgs>  
 [<span data-ttu-id="cb67d-109">라우트된 이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="cb67d-109">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="cb67d-110">방법 항목</span><span class="sxs-lookup"><span data-stu-id="cb67d-110">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
