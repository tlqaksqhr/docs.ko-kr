---
title: '방법: 바인딩 지우기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
ms.openlocfilehash: f66477fc857a9e7a065e01b8cddf43789042b59c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555859"
---
# <a name="how-to-clear-bindings"></a><span data-ttu-id="63728-102">방법: 바인딩 지우기</span><span class="sxs-lookup"><span data-stu-id="63728-102">How to: Clear Bindings</span></span>
<span data-ttu-id="63728-103">이 예에서는 개체에서 바인딩을 지우는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="63728-103">This example shows how to clear bindings from an object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63728-104">예제</span><span class="sxs-lookup"><span data-stu-id="63728-104">Example</span></span>  
 <span data-ttu-id="63728-105">개체에서 개별 속성에서 바인딩을 지우려면 호출 <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="63728-105">To clear a binding from an individual property on an object, call <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> as shown in the following example.</span></span> <span data-ttu-id="63728-106">다음 예제에서 바인딩을 제거는 <xref:System.Windows.Controls.TextBlock.TextProperty> 의 *mytext*, <xref:System.Windows.Controls.TextBlock> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="63728-106">The following example removes the binding from the <xref:System.Windows.Controls.TextBlock.TextProperty> of *mytext*, a <xref:System.Windows.Controls.TextBlock> object.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 <span data-ttu-id="63728-107">바인딩을 지우면 바인딩이 제거되므로, 종속성 속성의 값이 바인딩이 없는 값으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="63728-107">Clearing the binding removes the binding so that the value of the dependency property is changed to whatever it would have been without the binding.</span></span> <span data-ttu-id="63728-108">이 값은 기본값, 상속된 값 또는 데이터 템플릿 바인딩의 값이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63728-108">This value could be a default value, an inherited value, or a value from a data template binding.</span></span>  
  
 <span data-ttu-id="63728-109">개체의 모든 가능한 속성에서 바인딩을 지우려면를 사용 하 여 <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="63728-109">To clear bindings from all possible properties on an object, use <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63728-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63728-110">See Also</span></span>  
 <xref:System.Windows.Data.BindingOperations>  
 [<span data-ttu-id="63728-111">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="63728-111">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="63728-112">방법 항목</span><span class="sxs-lookup"><span data-stu-id="63728-112">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
