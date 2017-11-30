---
title: "방법: 데이터에 ListBox 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: deb5e05a7c48f26d0b829ba75b4ae120841e0a80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-a-listbox-to-data"></a><span data-ttu-id="cbcde-102">방법: 데이터에 ListBox 바인딩</span><span class="sxs-lookup"><span data-stu-id="cbcde-102">How to: Bind a ListBox to Data</span></span>
<span data-ttu-id="cbcde-103">응용 프로그램 개발자를 만들 수 <xref:System.Windows.Controls.ListBox> 각각의 내용을 지정 하지 않고 컨트롤 <xref:System.Windows.Controls.ListBoxItem> 별도로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcde-103">An application developer can create <xref:System.Windows.Controls.ListBox> controls without specifying the contents of each <xref:System.Windows.Controls.ListBoxItem> separately.</span></span> <span data-ttu-id="cbcde-104">개별 항목으로 데이터를 바인딩할 데이터 바인딩을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbcde-104">You can use data binding to bind data to the individual items.</span></span>  
  
 <span data-ttu-id="cbcde-105">만드는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.ListBox> 채우는 <xref:System.Windows.Controls.ListBoxItem> 요소 라는 데이터 원본에 대 한 데이터 바인딩을 통해 *색*합니다.</span><span class="sxs-lookup"><span data-stu-id="cbcde-105">The following example shows how to create a <xref:System.Windows.Controls.ListBox> that populates the <xref:System.Windows.Controls.ListBoxItem> elements by data binding to a data source called *Colors*.</span></span> <span data-ttu-id="cbcde-106">이 경우 필요한 경우가 아니라면 사용할 <xref:System.Windows.Controls.ListBoxItem> 각 항목의 내용을 지정 하는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="cbcde-106">In this case it is not necessary to use <xref:System.Windows.Controls.ListBoxItem> tags to specify the content of each item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbcde-107">예제</span><span class="sxs-lookup"><span data-stu-id="cbcde-107">Example</span></span>  
 [!code-xaml[ListBoxEvent#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="cbcde-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbcde-108">See Also</span></span>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.Controls.ListBoxItem>  
 [<span data-ttu-id="cbcde-109">컨트롤</span><span class="sxs-lookup"><span data-stu-id="cbcde-109">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
