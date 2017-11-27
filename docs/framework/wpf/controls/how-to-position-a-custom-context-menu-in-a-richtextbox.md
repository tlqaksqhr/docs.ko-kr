---
title: "방법: RichTextBox에서 사용자 지정 상황에 맞는 메뉴의 위치 지정"
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
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1c0a4fd8d2df15dcca2d9d1751f3089922d9a5ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a><span data-ttu-id="c94c1-102">방법: RichTextBox에서 사용자 지정 상황에 맞는 메뉴의 위치 지정</span><span class="sxs-lookup"><span data-stu-id="c94c1-102">How to: Position a Custom Context Menu in a RichTextBox</span></span>
<span data-ttu-id="c94c1-103">에 대 한 사용자 지정 상황에 맞는 메뉴를 배치 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.RichTextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="c94c1-103">This example shows how to position a custom context menu for a <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="c94c1-104">**RichTextBox**에 대한 사용자 지정 상황에 맞는 메뉴를 구현하는 경우 상황에 맞는 메뉴의 배치를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c94c1-104">When you implement a custom context menu for a **RichTextBox**, you are responsible for handling the placement of the context menu.</span></span>  <span data-ttu-id="c94c1-105">기본적으로 **RichTextBox**의 가운데에 사용자 지정 상황에 맞는 메뉴가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="c94c1-105">By default, a custom context menu is opened at the center of the **RichTextBox**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c94c1-106">예제</span><span class="sxs-lookup"><span data-stu-id="c94c1-106">Example</span></span>  
 <span data-ttu-id="c94c1-107">기본 배치 동작을 재정의 하려면 추가 대 한 수신기는 <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="c94c1-107">To override the default placement behavior, add a listener for the <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event.</span></span>  <span data-ttu-id="c94c1-108">다음 예제에서는 이를 프로그래밍 방식으로 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c94c1-108">The following example shows how to do this programmatically.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a><span data-ttu-id="c94c1-109">예제</span><span class="sxs-lookup"><span data-stu-id="c94c1-109">Example</span></span>  
 <span data-ttu-id="c94c1-110">다음 예제에서는 해당 구현을 <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> 이벤트 수신기입니다.</span><span class="sxs-lookup"><span data-stu-id="c94c1-110">The following example shows an implementation the corresponding <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event listener.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="c94c1-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c94c1-111">See Also</span></span>  
 [<span data-ttu-id="c94c1-112">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="c94c1-112">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [<span data-ttu-id="c94c1-113">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="c94c1-113">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
