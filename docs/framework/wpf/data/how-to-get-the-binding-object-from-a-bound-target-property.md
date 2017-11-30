---
title: "방법: 바인딩된 대상 속성에서 바인딩 개체 가져오기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 498849cc0205775f88c21d90d12b45c6b71a5dec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a><span data-ttu-id="a39a1-102">방법: 바인딩된 대상 속성에서 바인딩 개체 가져오기</span><span class="sxs-lookup"><span data-stu-id="a39a1-102">How to: Get the Binding Object from a Bound Target Property</span></span>
<span data-ttu-id="a39a1-103">이 예제에서는 데이터 바인딩된 대상 속성에서 바인딩 개체를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a39a1-103">This example shows how to obtain the binding object from a data-bound target property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a39a1-104">예제</span><span class="sxs-lookup"><span data-stu-id="a39a1-104">Example</span></span>  
 <span data-ttu-id="a39a1-105">가져오기 위해 다음을 수행할 수 있습니다는 <xref:System.Windows.Data.Binding> 개체:</span><span class="sxs-lookup"><span data-stu-id="a39a1-105">You can do the following to get the <xref:System.Windows.Data.Binding> object:</span></span>  
  
 [!code-csharp[BindValidation#GetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  <span data-ttu-id="a39a1-106">대상 개체의 둘 이상의 속성이 데이터 바인딩을 사용하고 있을 수 있으므로 원하는 바인딩에 대한 종속성 속성을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a39a1-106">You must specify the dependency property for the binding you want because it is possible that more than one property of the target object is using data binding.</span></span>  
  
 <span data-ttu-id="a39a1-107">가져올 수 있습니다는 <xref:System.Windows.Data.BindingExpression> 의 값을 가져온 후는 <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a39a1-107">Alternatively, you can get the <xref:System.Windows.Data.BindingExpression> and then get the value of the <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> property.</span></span>  
  
 <span data-ttu-id="a39a1-108">전체 예제는 [Binding Validation Sample](http://go.microsoft.com/fwlink/?LinkID=159972)(바인딩 유효성 검사 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a39a1-108">For the complete example see [Binding Validation Sample](http://go.microsoft.com/fwlink/?LinkID=159972).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a39a1-109">바인딩이 하는 경우는 <xref:System.Windows.Data.MultiBinding>를 사용 하 여 <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="a39a1-109">If your binding is a <xref:System.Windows.Data.MultiBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.</span></span> <span data-ttu-id="a39a1-110">이 경우는 <xref:System.Windows.Data.PriorityBinding>를 사용 하 여 <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="a39a1-110">If it is a <xref:System.Windows.Data.PriorityBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>.</span></span> <span data-ttu-id="a39a1-111">사용 하 여 대상 속성은 바인딩되어 있는지 여부는 확실 한 경우는 <xref:System.Windows.Data.Binding>, <xref:System.Windows.Data.MultiBinding>, 또는 <xref:System.Windows.Data.PriorityBinding>를 사용할 수 있습니다 <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="a39a1-111">If you are uncertain whether the target property is bound using a <xref:System.Windows.Data.Binding>, a <xref:System.Windows.Data.MultiBinding>, or a <xref:System.Windows.Data.PriorityBinding>, you can use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a39a1-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a39a1-112">See Also</span></span>  
 [<span data-ttu-id="a39a1-113">코드에서 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="a39a1-113">Create a Binding in Code</span></span>](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md)  
 [<span data-ttu-id="a39a1-114">방법 항목</span><span class="sxs-lookup"><span data-stu-id="a39a1-114">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
