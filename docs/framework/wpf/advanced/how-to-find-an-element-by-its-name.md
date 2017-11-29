---
title: "방법: 이름에 따라 요소 찾기"
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
helpviewer_keywords: elements [WPF], finding by name
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 62e5cc9c65afe9da9c77d06c103e99d3ff8d995a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-find-an-element-by-its-name"></a><span data-ttu-id="41c8d-102">방법: 이름에 따라 요소 찾기</span><span class="sxs-lookup"><span data-stu-id="41c8d-102">How to: Find an Element by Its Name</span></span>
<span data-ttu-id="41c8d-103">이 예제에서는 사용 하는 방법을 설명는 <xref:System.Windows.FrameworkElement.FindName%2A> 메서드 여 요소를 해당 <xref:System.Windows.FrameworkElement.Name%2A> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="41c8d-103">This example describes how to use the <xref:System.Windows.FrameworkElement.FindName%2A> method to find an element by its <xref:System.Windows.FrameworkElement.Name%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41c8d-104">예제</span><span class="sxs-lookup"><span data-stu-id="41c8d-104">Example</span></span>  
 <span data-ttu-id="41c8d-105">이 예제에서는 메서드 이름을 사용 하 여 특정 요소를 찾을 수 있는 단추의 이벤트 처리기로 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41c8d-105">In this example, the method to find a particular element by its name is written as the event handler of a button.</span></span> <span data-ttu-id="41c8d-106">`stackPanel`이 <xref:System.Windows.FrameworkElement.Name%2A> 루트의 <xref:System.Windows.FrameworkElement> 검색 중인 문서를 나타내고 메서드 예제 다음 시각적으로 찾은 요소의 캐스팅 하 여 <xref:System.Windows.Controls.TextBlock> 중 하나를 변경 하 고는 <xref:System.Windows.Controls.TextBlock> 표시 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 속성.</span><span class="sxs-lookup"><span data-stu-id="41c8d-106">`stackPanel` is the <xref:System.Windows.FrameworkElement.Name%2A> of the root <xref:System.Windows.FrameworkElement> being searched, and the example method then visually indicates the found element by casting it as <xref:System.Windows.Controls.TextBlock> and changing one of the <xref:System.Windows.Controls.TextBlock> visible [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] properties.</span></span>  
  
 [!code-csharp[FEFindName#Find](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]
