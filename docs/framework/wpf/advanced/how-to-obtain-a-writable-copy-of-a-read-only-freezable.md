---
title: "방법: 읽기 전용 Freezable의 쓰기 가능한 복사본 가져오기"
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
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9fe22e49ee28de60bc76d7a4f543462bbcfac48c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a><span data-ttu-id="f2fc9-102">방법: 읽기 전용 Freezable의 쓰기 가능한 복사본 가져오기</span><span class="sxs-lookup"><span data-stu-id="f2fc9-102">How to: Obtain a Writable Copy of a Read-Only Freezable</span></span>
<span data-ttu-id="f2fc9-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Freezable.Clone%2A> 메서드는 읽기 전용의 쓰기 가능한 복사본을 만드는 <xref:System.Windows.Freezable>합니다.</span><span class="sxs-lookup"><span data-stu-id="f2fc9-103">This example shows how to use the <xref:System.Windows.Freezable.Clone%2A> method to create a writable copy of a read-only <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="f2fc9-104">이후에 <xref:System.Windows.Freezable> 개체 표시 되어 읽기 전용 ("고정")으로 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2fc9-104">After a <xref:System.Windows.Freezable> object is marked as read-only ("frozen"), you cannot modify it.</span></span> <span data-ttu-id="f2fc9-105">사용할 수 있습니다는 <xref:System.Windows.Freezable.Clone%2A> 방법이 고정된 된 개체의 수정 가능한 복제본을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2fc9-105">However, you can use the <xref:System.Windows.Freezable.Clone%2A> method to create a modifiable clone of the frozen object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2fc9-106">예</span><span class="sxs-lookup"><span data-stu-id="f2fc9-106">Example</span></span>  
 <span data-ttu-id="f2fc9-107">다음 예제에서는 고정 된의 수정 가능한 복제본 <xref:System.Windows.Media.SolidColorBrush> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f2fc9-107">The following example creates a modifiable clone of a frozen <xref:System.Windows.Media.SolidColorBrush> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 <span data-ttu-id="f2fc9-108">에 대 한 자세한 내용은 <xref:System.Windows.Freezable> 개체 참조는 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f2fc9-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2fc9-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2fc9-109">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CloneCurrentValue%2A>  
 [<span data-ttu-id="f2fc9-110">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="f2fc9-110">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="f2fc9-111">방법 항목</span><span class="sxs-lookup"><span data-stu-id="f2fc9-111">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
