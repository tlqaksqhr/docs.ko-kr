---
title: "방법: TextBox 텍스트의 소스를 업데이트하는 시점 제어"
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
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c923a24f5abfdb059a436206a15181a67d03068f
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a><span data-ttu-id="81675-102">방법: TextBox 텍스트의 소스를 업데이트하는 시점 제어</span><span class="sxs-lookup"><span data-stu-id="81675-102">How to: Control When the TextBox Text Updates the Source</span></span>
<span data-ttu-id="81675-103">이 항목에서는 사용 하는 방법을 설명는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 바인딩 소스 업데이트의 타이밍을 제어 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="81675-103">This topic describes how to use the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property to control the timing of binding source updates.</span></span> <span data-ttu-id="81675-104">항목에서는 사용 된 <xref:System.Windows.Controls.TextBox> 예를 들어 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="81675-104">The topic uses the <xref:System.Windows.Controls.TextBox> control as an example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81675-105">예제</span><span class="sxs-lookup"><span data-stu-id="81675-105">Example</span></span>  
 <span data-ttu-id="81675-106"><xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> 속성에는 기본 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>합니다.</span><span class="sxs-lookup"><span data-stu-id="81675-106">The <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> property has a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span></span> <span data-ttu-id="81675-107">즉, 경우에 응용 프로그램에 <xref:System.Windows.Controls.TextBox> 데이터 바인딩된 <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> 속성에 입력 한 텍스트는 <xref:System.Windows.Controls.TextBox> 될 때까지 소스를 업데이트 하지 않습니다는 <xref:System.Windows.Controls.TextBox> 포커스를 잃을 (예를 들어, 클릭는 반대쪽<xref:System.Windows.Controls.TextBox>).</span><span class="sxs-lookup"><span data-stu-id="81675-107">This means if an application has a <xref:System.Windows.Controls.TextBox> with a data-bound <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> property, the text you type into the <xref:System.Windows.Controls.TextBox> does not update the source until the <xref:System.Windows.Controls.TextBox> loses focus (for instance, when you click away from the <xref:System.Windows.Controls.TextBox>).</span></span>  
  
 <span data-ttu-id="81675-108">입력 하는 원본으로 업데이트 되기를 원하는 경우, 설정 된 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 에 대 한 바인딩 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>합니다.</span><span class="sxs-lookup"><span data-stu-id="81675-108">If you want the source to get updated as you are typing, set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> of the binding to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="81675-109">다음 예제에서는 `Text` 둘 다는 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.TextBlock> 동일한 소스 속성에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="81675-109">In the following example, the `Text` properties of both the <xref:System.Windows.Controls.TextBox> and the <xref:System.Windows.Controls.TextBlock> are bound to the same source property.</span></span> <span data-ttu-id="81675-110"><xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 의 속성은 <xref:System.Windows.Controls.TextBox> 바인딩으로 설정 된 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>합니다.</span><span class="sxs-lookup"><span data-stu-id="81675-110">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property of the <xref:System.Windows.Controls.TextBox> binding is set to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span>  
  
 [!code-xaml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#usthowto)]  
  
 <span data-ttu-id="81675-111">결과적으로 <xref:System.Windows.Controls.TextBlock> 사용자가 텍스트를 (변경 되기 때문에 소스) 같은 텍스트를 표시는 <xref:System.Windows.Controls.TextBox>샘플의 다음 스크린 샷에서 예와 같이:</span><span class="sxs-lookup"><span data-stu-id="81675-111">As a result, the <xref:System.Windows.Controls.TextBlock> shows the same text (because the source changes) as the user enters text into the <xref:System.Windows.Controls.TextBox>, as illustrated by the following screenshot of the sample:</span></span>  
  
 <span data-ttu-id="81675-112">![단순 데이터 바인딩 샘플 스크린샷](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")</span><span class="sxs-lookup"><span data-stu-id="81675-112">![Simple data binding sample screen shot](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")</span></span>  
  
 <span data-ttu-id="81675-113">대화 상자 또는 사용자가 편집 가능한 폼 하 고 사용자가 완료 되는 필드를 편집 하 고 "확인"을 클릭 될 때까지 원본 업데이트 연기 하려는 설정할 수 있습니다는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값에 대 한 바인딩 <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>다음 예제와 같이,:</span><span class="sxs-lookup"><span data-stu-id="81675-113">If you have a dialog or a user-editable form and you want to defer source updates until the user is finished editing the fields and clicks "OK", you can set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of your bindings to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, as in the following example:</span></span>  
  
 [!code-xaml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="81675-114">설정 하는 경우는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값을 <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, 응용 프로그램 호출 하는 경우에 소스 값 변경의 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="81675-114">When you set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, the source value only changes when the application calls the <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> method.</span></span> <span data-ttu-id="81675-115">다음 예제에서는 호출 하는 방법을 보여 줍니다. <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> 에 대 한 `itemNameTextBox`:</span><span class="sxs-lookup"><span data-stu-id="81675-115">The following example shows how to call <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> for `itemNameTextBox`:</span></span>  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  <span data-ttu-id="81675-116">다른 컨트롤의 속성에 대 한 동일한 기법을 사용할 수 있지만 대부분의 다른 속성 기본값 한지 염두에서에 둬야 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>합니다.</span><span class="sxs-lookup"><span data-stu-id="81675-116">You can use the same technique for properties of other controls, but keep in mind that most other properties have a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="81675-117">자세한 내용은 참조는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성 페이지.</span><span class="sxs-lookup"><span data-stu-id="81675-117">For more information, see the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81675-118"><xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성 소스 업데이트를 처리 하 고 따라서만 관련 된 <xref:System.Windows.Data.BindingMode.TwoWay> 또는 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩.</span><span class="sxs-lookup"><span data-stu-id="81675-118">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property deals with source updates and therefore is only relevant for <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings.</span></span> <span data-ttu-id="81675-119">에 대 한 <xref:System.Windows.Data.BindingMode.TwoWay> 및 <xref:System.Windows.Data.BindingMode.OneWayToSource> 작업이 면 속성 변경 알림을 제공 하는 소스 개체 요구 사항에 대 한 바인딩을 합니다.</span><span class="sxs-lookup"><span data-stu-id="81675-119">For <xref:System.Windows.Data.BindingMode.TwoWay> and <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings to work, the source object needs to provide property change notifications.</span></span> <span data-ttu-id="81675-120">자세한 내용은 이 항목에 제시된 샘플을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81675-120">You can refer to the samples cited in this topic for more information.</span></span> <span data-ttu-id="81675-121">또한 [속성 변경 알림 구현](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md)을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81675-121">In addition, you can look at [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81675-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81675-122">See Also</span></span>  
 [<span data-ttu-id="81675-123">방법 항목</span><span class="sxs-lookup"><span data-stu-id="81675-123">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
