---
title: "방법: Freezable의 고정 여부 확인"
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
helpviewer_keywords: Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 47fb0a871c3792450386c440629ead1ee3fbecdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a><span data-ttu-id="58f56-102">방법: Freezable의 고정 여부 확인</span><span class="sxs-lookup"><span data-stu-id="58f56-102">How to: Determine Whether a Freezable Is Frozen</span></span>
<span data-ttu-id="58f56-103">확인 하는 방법을 보여 주는이 예제 여부는 <xref:System.Windows.Freezable> 개체를 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58f56-103">This example shows how to determine whether a <xref:System.Windows.Freezable> object is frozen.</span></span> <span data-ttu-id="58f56-104">고정 된 수정 하려고 할 경우 <xref:System.Windows.Freezable> 개체를 throw 한 <xref:System.InvalidOperationException>합니다.</span><span class="sxs-lookup"><span data-stu-id="58f56-104">If you try to modify a frozen <xref:System.Windows.Freezable> object, it throws an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="58f56-105">이 예외가 throw를 방지 하려면 사용는 <xref:System.Windows.Freezable.IsFrozen%2A> 의 속성은 <xref:System.Windows.Freezable> 고정 되어 있는지 여부를 결정 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="58f56-105">To avoid throwing this exception, use the <xref:System.Windows.Freezable.IsFrozen%2A> property of the <xref:System.Windows.Freezable> object to determine whether it is frozen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58f56-106">예제</span><span class="sxs-lookup"><span data-stu-id="58f56-106">Example</span></span>  
 <span data-ttu-id="58f56-107">다음 예제에서는 고정는 <xref:System.Windows.Media.SolidColorBrush> 다음 사용 하 여 테스트는 <xref:System.Windows.Freezable.IsFrozen%2A> 고정 되어 있는지 여부를 결정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="58f56-107">The following example freezes a <xref:System.Windows.Media.SolidColorBrush> and then tests it by using the <xref:System.Windows.Freezable.IsFrozen%2A> property to determine whether it is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="58f56-108">에 대 한 자세한 내용은 <xref:System.Windows.Freezable> 개체 참조는 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="58f56-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58f56-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58f56-109">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.IsFrozen%2A>  
 [<span data-ttu-id="58f56-110">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="58f56-110">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="58f56-111">방법 항목</span><span class="sxs-lookup"><span data-stu-id="58f56-111">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
