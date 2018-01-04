---
title: "방법: 열거형 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 72439cdc1c1017378a5b6b3f6b4bf41a9eee2537
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="9f703-102">방법: 열거형 바인딩</span><span class="sxs-lookup"><span data-stu-id="9f703-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="9f703-103">이 예제에서는 열거형의 GetValues 메서드에 바인딩하여 열거형에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f703-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f703-104">예</span><span class="sxs-lookup"><span data-stu-id="9f703-104">Example</span></span>  
 <span data-ttu-id="9f703-105">다음 예제에서는 <xref:System.Windows.Controls.ListBox> 의 목록을 표시 <xref:System.Windows.HorizontalAlignment> 데이터 바인딩을 통해 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9f703-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="9f703-106"><xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.Button> 변경할 수 있도록 바인딩된는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 의 속성 값은 <xref:System.Windows.Controls.Button> 에 값을 선택 하 여는 <xref:System.Windows.Controls.ListBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="9f703-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="9f703-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f703-107">See Also</span></span>  
 [<span data-ttu-id="9f703-108">메서드 바인딩</span><span class="sxs-lookup"><span data-stu-id="9f703-108">Bind to a Method</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)  
 [<span data-ttu-id="9f703-109">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="9f703-109">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="9f703-110">방법 항목</span><span class="sxs-lookup"><span data-stu-id="9f703-110">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
