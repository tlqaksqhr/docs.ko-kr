---
title: "방법: Grid의 자식 요소 위치 지정"
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
helpviewer_keywords: Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ca385e1aee10fb10ac3e912999aec3a11d03ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="05ee7-102">방법: Grid의 자식 요소 위치 지정</span><span class="sxs-lookup"><span data-stu-id="05ee7-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="05ee7-103">Get를 사용 하 고에 정의 된 메서드를 설정 하는 방법을 보여 주는이 예제 <xref:System.Windows.Controls.Grid> 자식 요소의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="05ee7-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05ee7-104">예</span><span class="sxs-lookup"><span data-stu-id="05ee7-104">Example</span></span>  
 <span data-ttu-id="05ee7-105">다음 예제에서는 부모 <xref:System.Windows.Controls.Grid> 요소 (`grid1`)는에 세 개의 열 3 개와 행.</span><span class="sxs-lookup"><span data-stu-id="05ee7-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="05ee7-106">자식 <xref:System.Windows.Shapes.Rectangle> 요소 (`rect1`)에 추가 되 고 <xref:System.Windows.Controls.Grid> 0 열에서 위치 0 행을 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ee7-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="05ee7-107"><xref:System.Windows.Controls.Button>요소 위치를 변경 하기 위해 호출할 수 있는 메서드를 나타냅니다는 <xref:System.Windows.Shapes.Rectangle> 내의 요소는 <xref:System.Windows.Controls.Grid>합니다.</span><span class="sxs-lookup"><span data-stu-id="05ee7-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="05ee7-108">사용자가 단추를 클릭 하면 관련된 메서드가 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ee7-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="05ee7-109">다음 코드 예제에서는 메서드를 처리 하는 단추 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="05ee7-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="05ee7-110">이 예제에서는 기록에 이러한 메서드 호출 <xref:System.Windows.Controls.TextBlock> 사용 관련 요소를 get 메서드를 문자열로 새 속성 값을 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ee7-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="05ee7-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05ee7-111">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 [<span data-ttu-id="05ee7-112">패널 개요</span><span class="sxs-lookup"><span data-stu-id="05ee7-112">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
