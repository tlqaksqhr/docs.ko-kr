---
title: "방법: 코드에서 바인딩 만들기"
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
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f98190b2d0f48e931129dcf95f63b2ff6b616ccc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="ddda9-102">방법: 코드에서 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="ddda9-102">How to: Create a Binding in Code</span></span>
<span data-ttu-id="ddda9-103">만들고 설정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Data.Binding> 코드에서입니다.</span><span class="sxs-lookup"><span data-stu-id="ddda9-103">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddda9-104">예</span><span class="sxs-lookup"><span data-stu-id="ddda9-104">Example</span></span>  
 <span data-ttu-id="ddda9-105"><xref:System.Windows.FrameworkElement> 클래스 및 <xref:System.Windows.FrameworkContentElement> 둘 다 노출 하는 클래스는 `SetBinding` 메서드.</span><span class="sxs-lookup"><span data-stu-id="ddda9-105">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="ddda9-106">이러한 클래스 중 하나를 상속 하는 요소에 바인딩하는 경우 호출할 수 있습니다는 <xref:System.Windows.FrameworkElement.SetBinding%2A> 메서드를 직접 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddda9-106">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="ddda9-107">다음 예제에서는 명명 된 인스턴스인지 클래스 `MyData`, 라는 속성이 포함 된 `MyDataProperty`합니다.</span><span class="sxs-lookup"><span data-stu-id="ddda9-107">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="ddda9-108">다음 예제에서는 바인딩의 원본을 설정 하려면 바인딩 개체를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ddda9-108">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="ddda9-109">이 예에서는 사용 <xref:System.Windows.FrameworkElement.SetBinding%2A> 바인딩할는 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성 `myText`, 변수인는 <xref:System.Windows.Controls.TextBlock> 컨트롤과 `MyDataProperty`합니다.</span><span class="sxs-lookup"><span data-stu-id="ddda9-109">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="ddda9-110">전체 코드 샘플을 보려면 [코드 전용 Binding 샘플](http://msdn.microsoft.com/en-us/764aaf0b-2216-4941-9548-9c98da18d1a6)합니다.</span><span class="sxs-lookup"><span data-stu-id="ddda9-110">For the complete code sample, see [Code-only Binding Sample](http://msdn.microsoft.com/en-us/764aaf0b-2216-4941-9548-9c98da18d1a6).</span></span>  
  
 <span data-ttu-id="ddda9-111">호출 하는 대신 <xref:System.Windows.FrameworkElement.SetBinding%2A>를 사용할 수 있습니다는 <xref:System.Windows.Data.BindingOperations.SetBinding%2A> 의 정적 메서드는 <xref:System.Windows.Data.BindingOperations> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ddda9-111">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="ddda9-112">다음 예제에서는 호출 <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> 대신 <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> 바인딩할 `myText` 를 `myDataProperty`합니다.</span><span class="sxs-lookup"><span data-stu-id="ddda9-112">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="ddda9-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ddda9-113">See Also</span></span>  
 [<span data-ttu-id="ddda9-114">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="ddda9-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="ddda9-115">방법 항목</span><span class="sxs-lookup"><span data-stu-id="ddda9-115">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
