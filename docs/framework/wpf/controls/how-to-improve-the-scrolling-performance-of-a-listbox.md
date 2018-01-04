---
title: "방법: ListBox의 스크롤 성능 개선"
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
- ListBox control [WPF], reusing item containers
- ListBox control [WPF], improving scrolling performance
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 58435948a3ddd8042b95b30b8d6cbdba984f34d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a><span data-ttu-id="77698-102">방법: ListBox의 스크롤 성능 개선</span><span class="sxs-lookup"><span data-stu-id="77698-102">How to: Improve the Scrolling Performance of a ListBox</span></span>
<span data-ttu-id="77698-103">경우는 <xref:System.Windows.Controls.ListBox> 많은 항목이 포함 된 스크롤할 때 사용자 인터페이스 응답이 느려질 수 있습니다는 <xref:System.Windows.Controls.ListBox> 스크롤 막대의 엄지 단추를 끌거나 마우스 휠을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="77698-103">If a <xref:System.Windows.Controls.ListBox> contains many items, the user interface response can be slow when a user scrolls the <xref:System.Windows.Controls.ListBox> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="77698-104">성능을 향상 시킬 수 있습니다는 <xref:System.Windows.Controls.ListBox> 사용자가을 설정 하 여를 스크롤할 때는 `VirtualizingStackPanel.VirtualizationMode` 연결 된 속성을 <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="77698-104">You can improve the performance of the <xref:System.Windows.Controls.ListBox> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77698-105">예</span><span class="sxs-lookup"><span data-stu-id="77698-105">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="77698-106">설명</span><span class="sxs-lookup"><span data-stu-id="77698-106">Description</span></span>  
<span data-ttu-id="77698-107">다음 예제에서는 한 <xref:System.Windows.Controls.ListBox> 설정 하 고는 `VirtualizingStackPanel.VirtualizationMode` 연결 된 속성을 <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> 스크롤 하는 동안 성능 향상을 위해 합니다.</span><span class="sxs-lookup"><span data-stu-id="77698-107">The following example creates a <xref:System.Windows.Controls.ListBox> and sets the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to improve performance during scrolling.</span></span>  
  
## <a name="code"></a><span data-ttu-id="77698-108">코드</span><span class="sxs-lookup"><span data-stu-id="77698-108">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 <span data-ttu-id="77698-109">다음 예제에서는 사용 하 여 이전 예제에서 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="77698-109">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
