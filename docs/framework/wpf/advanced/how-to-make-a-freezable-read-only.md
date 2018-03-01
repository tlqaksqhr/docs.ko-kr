---
title: "방법: Freezable을 읽기 전용으로 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aa6d3f7109e8258dff0a07556bc8572f6071c961
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="3a3ff-102">방법: Freezable을 읽기 전용으로 설정</span><span class="sxs-lookup"><span data-stu-id="3a3ff-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="3a3ff-103">확인 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Freezable> 호출 하 여 읽기 전용 해당 <xref:System.Windows.Freezable.Freeze%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="3a3ff-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="3a3ff-104">고정할 수 없습니다는 <xref:System.Windows.Freezable> 다음 조건 중 하나라도 않은 경우 개체 `true` 개체에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a3ff-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
-   <span data-ttu-id="3a3ff-105">애니메이션이 적용 또는 데이터 바인딩된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3a3ff-105">It has animated or data bound properties.</span></span>  
  
-   <span data-ttu-id="3a3ff-106">동적 리소스에서 설정 하는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a3ff-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="3a3ff-107">동적 리소스에 대 한 자세한 내용은 참조는 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a3ff-107">For more information about dynamic resources, see the [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
-   <span data-ttu-id="3a3ff-108">포함 된 <xref:System.Windows.Freezable> 고정할 수 없는 하위 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3a3ff-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="3a3ff-109">이러한 조건이 `false` 에 대 한 프로그램 <xref:System.Windows.Freezable> 개체 하지 않으려는 수정 성능을 향상 시키는 것을 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3a3ff-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a3ff-110">예</span><span class="sxs-lookup"><span data-stu-id="3a3ff-110">Example</span></span>  
 <span data-ttu-id="3a3ff-111">다음 예제에서는 고정 한 <xref:System.Windows.Media.SolidColorBrush>의 형식인 <xref:System.Windows.Freezable> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3a3ff-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="3a3ff-112">에 대 한 자세한 내용은 <xref:System.Windows.Freezable> 개체 참조는 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a3ff-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a3ff-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a3ff-113">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CanFreeze%2A>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [<span data-ttu-id="3a3ff-114">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="3a3ff-114">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="3a3ff-115">방법 항목</span><span class="sxs-lookup"><span data-stu-id="3a3ff-115">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
