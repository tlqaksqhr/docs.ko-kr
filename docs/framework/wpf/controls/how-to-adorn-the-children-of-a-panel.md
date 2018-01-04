---
title: "방법: 패널의 자식 표시"
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
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 70a2c1e7735a6df31a44fce7eb9bb2371acc208b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-adorn-the-children-of-a-panel"></a><span data-ttu-id="20330-102">방법: 패널의 자식 표시</span><span class="sxs-lookup"><span data-stu-id="20330-102">How to: Adorn the Children of a Panel</span></span>
<span data-ttu-id="20330-103">프로그래밍 방식으로 지정된 된 자식에 표시기를 바인딩하는 방법을 보여 주는이 예제 <xref:System.Windows.Controls.Panel>합니다.</span><span class="sxs-lookup"><span data-stu-id="20330-103">This example shows how to programmatically bind an adorner to the children of a specified <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20330-104">예</span><span class="sxs-lookup"><span data-stu-id="20330-104">Example</span></span>  
 <span data-ttu-id="20330-105">표시기의 자식 항목에 바인딩하는 <xref:System.Windows.Controls.Panel>, 다음이 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20330-105">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="20330-106">선언 <xref:System.Windows.Documents.AdornerLayer> 개체와 호출은 `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 메서드 표시 수의 자식 요소에 대 한 표시기 계층을 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="20330-106">Declare a new <xref:System.Windows.Documents.AdornerLayer> object and call the `static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> method to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2.  <span data-ttu-id="20330-107">부모 요소와 호출의 자식을 열거는 <xref:System.Windows.Documents.AdornerLayer.Add%2A> 표시기 각 자식 요소를 바인딩하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="20330-107">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="20330-108">다음 예에서는 바인딩합니다 (위에 표시 된)의 자식에 SimpleCircleAdorner는 <xref:System.Windows.Controls.StackPanel> 라는 *myStackPanel*합니다.</span><span class="sxs-lookup"><span data-stu-id="20330-108">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  <span data-ttu-id="20330-109">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 사용하여 표시기를 다른 요소에 바인딩하는 것은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20330-109">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20330-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20330-110">See Also</span></span>  
 [<span data-ttu-id="20330-111">표시기 개요</span><span class="sxs-lookup"><span data-stu-id="20330-111">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
