---
title: "바인딩 선언 개요"
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
- markup extensions [WPF]
- data binding [WPF], declarations
- object element syntax [WPF]
- binding data [WPF], declarations
- syntax [WPF], object elements
- binding declarations [WPF]
ms.assetid: b97fd626-4c0d-4761-872a-2bca5820da2c
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 28b139f6ea2aad41e4d733e8c622699f2474b3e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="binding-declarations-overview"></a><span data-ttu-id="fd121-102">바인딩 선언 개요</span><span class="sxs-lookup"><span data-stu-id="fd121-102">Binding Declarations Overview</span></span>
<span data-ttu-id="fd121-103">이 항목에서는 바인딩을 선언할 수 있는 여러 가지 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-103">This topic discusses the different ways you can declare a binding.</span></span>  
  
 
  
<a name="Prereq"></a>   
## <a name="prerequisites"></a><span data-ttu-id="fd121-104">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fd121-104">Prerequisites</span></span>  
 <span data-ttu-id="fd121-105">이 항목은 태그 확장의 개념 및 사용 방법에 익숙하다는 것을 전제로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-105">Before reading this topic, it is important that you are familiar with the concept and usage of markup extensions.</span></span> <span data-ttu-id="fd121-106">태그 확장에 대한 자세한 내용은 [XAML 태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd121-106">For more information about markup extensions, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="fd121-107">이 항목에서는 데이터 바인딩 개념에 대해 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-107">This topic does not cover data binding concepts.</span></span> <span data-ttu-id="fd121-108">데이터 바인딩 개념에 대한 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd121-108">For a discussion of data binding concepts, see [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
<a name="BindinginXAML"></a>   
## <a name="declaring-a-binding-in-xaml"></a><span data-ttu-id="fd121-109">XAML에서 바인딩 선언</span><span class="sxs-lookup"><span data-stu-id="fd121-109">Declaring a Binding in XAML</span></span>  
 <span data-ttu-id="fd121-110">이 섹션에서는 XAML에서 바인딩을 선언하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-110">This section discusses how to declare a binding in XAML.</span></span>  
  
<a name="MarkupExtensionSyntax"></a>   
### <a name="markup-extension-usage"></a><span data-ttu-id="fd121-111">태그 확장 사용</span><span class="sxs-lookup"><span data-stu-id="fd121-111">Markup Extension Usage</span></span>  
 <span data-ttu-id="fd121-112"><xref:System.Windows.Data.Binding>은 태그 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-112"><xref:System.Windows.Data.Binding> is a markup extension.</span></span> <span data-ttu-id="fd121-113">바인딩 확장을 사용하여 바인딩을 선언할 때 선언은 `Binding` 키워드 뒤에 일련의 절이 쉼표(,)로 구분된 형태로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-113">When you use the binding extension to declare a binding, the declaration consists of a series of clauses following the `Binding` keyword and separated by commas (,).</span></span> <span data-ttu-id="fd121-114">바인딩 선언의 절 순서는 중요하지 않으며 수많은 조합이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-114">The clauses in the binding declaration can be in any order and there are many possible combinations.</span></span> <span data-ttu-id="fd121-115">절을 *이름*=*값* 쌍 *이름* 의 이름인는 <xref:System.Windows.Data.Binding> 속성 및 *값* 은 속성에 대해 설정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-115">The clauses are *Name*=*Value* pairs where *Name* is the name of the <xref:System.Windows.Data.Binding> property and *Value* is the value you are setting for the property.</span></span>  
  
 <span data-ttu-id="fd121-116">태그에서 바인딩 선언 문자열을 만들 때는 대상 개체의 특정 종속성 속성에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-116">When creating binding declaration strings in markup, they must be attached to the specific dependency property of a target object.</span></span> <span data-ttu-id="fd121-117">다음 예제에서는 바인딩하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> 속성 바인딩 확장을 사용 하 여, 지정 하는 <xref:System.Windows.Data.Binding.Source%2A> 및 <xref:System.Windows.Data.Binding.Path%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-117">The following example shows how to bind the <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> property using the binding extension, specifying the <xref:System.Windows.Data.Binding.Source%2A> and <xref:System.Windows.Data.Binding.Path%2A> properties.</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="fd121-118">대부분의 속성을 지정할 수는 <xref:System.Windows.Data.Binding> 이러한 방식으로 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-118">You can specify most of the properties of the <xref:System.Windows.Data.Binding> class this way.</span></span> <span data-ttu-id="fd121-119">목록이 구문과 바인딩 확장에 대 한 자세한 내용은 <xref:System.Windows.Data.Binding> 바인딩 확장을 사용 하 여 설정할 수 없는 속성 참조는 [바인딩 태그 확장](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-119">For more information about the binding extension as well as for a list of <xref:System.Windows.Data.Binding> properties that cannot be set using the binding extension, see the [Binding Markup Extension](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) overview.</span></span>  
  
<a name="ObjectElementSyntax"></a>   
### <a name="object-element-syntax"></a><span data-ttu-id="fd121-120">개체 요소 구문</span><span class="sxs-lookup"><span data-stu-id="fd121-120">Object Element Syntax</span></span>  
 <span data-ttu-id="fd121-121">개체 요소 구문은 바인딩 선언을 만드는 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-121">Object element syntax is an alternative to creating the binding declaration.</span></span> <span data-ttu-id="fd121-122">대부분의 경우 태그 확장 또는 개체 요소 구문을 사용할 때의 특별한 이점은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-122">In most cases, there is no particular advantage to using either the markup extension or the object element syntax.</span></span> <span data-ttu-id="fd121-123">그러나 태그 확장을 사용할 수 없는 시나리오, 예를 들어 속성 값이 문자열 형식이 아니어서 형식 변환이 존재하지 않는 경우에는 개체 요소 구문을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-123">However, in cases which the markup extension does not support your scenario, such as when your property value is of a non-string type for which no type conversion exists, you need to use the object element syntax.</span></span>  
  
 <span data-ttu-id="fd121-124">다음은 개체 요소 구문 및 태그 확장 사용의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-124">The following is an example of both the object element syntax and the markup extension usage:</span></span>  
  
 [!code-xaml[BindConversionMarkup#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversionMarkup/CSharp/Page1.xaml#1)]  
  
 <span data-ttu-id="fd121-125">이 예제에서는 바인딩하는 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 확장 구문을 사용 하는 바인딩을 선언 하 여 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-125">The example binds the <xref:System.Windows.Controls.TextBlock.Foreground%2A> property by declaring a binding using the extension syntax.</span></span> <span data-ttu-id="fd121-126">에 대 한 바인딩 선언을 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성 개체 요소 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-126">The binding declaration for the <xref:System.Windows.Controls.TextBlock.Text%2A> property uses the object element syntax.</span></span>  
  
 <span data-ttu-id="fd121-127">다양한 용어에 대한 자세한 내용은 [XAML 구문 정보](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd121-127">For more information about the different terms, see [XAML Syntax In Detail](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).</span></span>  
  
<a name="MBandPB"></a>   
### <a name="multibinding-and-prioritybinding"></a><span data-ttu-id="fd121-128">MultiBinding 및 PriorityBinding</span><span class="sxs-lookup"><span data-stu-id="fd121-128">MultiBinding and PriorityBinding</span></span>  
 <span data-ttu-id="fd121-129"><xref:System.Windows.Data.MultiBinding>및 <xref:System.Windows.Data.PriorityBinding> XAML 확장 구문을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-129"><xref:System.Windows.Data.MultiBinding> and <xref:System.Windows.Data.PriorityBinding> do not support the XAML extension syntax.</span></span> <span data-ttu-id="fd121-130">따라서 선언 하는 경우 개체 요소 구문을 사용 해야 하는 <xref:System.Windows.Data.MultiBinding> 또는 <xref:System.Windows.Data.PriorityBinding> XAML에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-130">Therefore, you must use the object element syntax if you are declaring a <xref:System.Windows.Data.MultiBinding> or a <xref:System.Windows.Data.PriorityBinding> in XAML.</span></span>  
  
<a name="BindinginCode"></a>   
## <a name="creating-a-binding-in-code"></a><span data-ttu-id="fd121-131">코드에서 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="fd121-131">Creating a Binding in Code</span></span>  
 <span data-ttu-id="fd121-132">직접 속성을 설정 하는 바인딩을 지정 하는 다른 방법은 <xref:System.Windows.Data.Binding> 코드에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-132">Another way to specify a binding is to set properties directly on a <xref:System.Windows.Data.Binding> object in code.</span></span> <span data-ttu-id="fd121-133">만드는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Data.Binding> 개체 및 코드에서 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-133">The following example shows how to create a <xref:System.Windows.Data.Binding> object and specify the properties in code.</span></span>  <span data-ttu-id="fd121-134">이 예제에서는 `TheConverter` 구현 하는 개체는 <xref:System.Windows.Data.IValueConverter> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-134">In this example, `TheConverter` is an object that implements the <xref:System.Windows.Data.IValueConverter> interface.</span></span>  
  
 [!code-csharp[BindConversion#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#1)]
 [!code-vb[BindConversion#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#1)]  
[!code-csharp[BindConversion#end1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#end1)]
[!code-vb[BindConversion#end1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#end1)]  
  
 <span data-ttu-id="fd121-135">바인딩하는 개체가 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 호출할 수는 `SetBinding` 메서드를 사용 하는 대신 직접 개체 <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-135">If the object you are binding is a <xref:System.Windows.FrameworkElement> or a <xref:System.Windows.FrameworkContentElement> you can call the `SetBinding` method on your object directly instead of using <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fd121-136">예제는 [코드에서 바인딩 만들기](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd121-136">For an example, see [Create a Binding in Code](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md).</span></span>  
  
<a name="Path_Syntax"></a>   
## <a name="binding-path-syntax"></a><span data-ttu-id="fd121-137">바인딩 경로 구문</span><span class="sxs-lookup"><span data-stu-id="fd121-137">Binding Path Syntax</span></span>  
 <span data-ttu-id="fd121-138">사용 하 여는 <xref:System.Windows.Data.Binding.Path%2A> 속성에 바인딩할 소스 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-138">Use the <xref:System.Windows.Data.Binding.Path%2A> property to specify the source value you want to bind to:</span></span>  
  
-   <span data-ttu-id="fd121-139">가장 단순한 경우는 <xref:System.Windows.Data.Binding.Path%2A> 속성 값은 바인딩의 경우와 같은 사용할 소스 개체의 속성 이름 `Path=PropertyName`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-139">In the simplest case, the <xref:System.Windows.Data.Binding.Path%2A> property value is the name of the property of the source object to use for the binding, such as `Path=PropertyName`.</span></span>  
  
-   <span data-ttu-id="fd121-140">[!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]과 비슷한 구문을 사용하여 속성의 하위 속성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-140">Subproperties of a property can be specified by a similar syntax as in [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)].</span></span> <span data-ttu-id="fd121-141">예를 들어 `Path=ShoppingCart.Order` 절은 개체 또는 속성 `ShoppingCart`의 하위 속성 `Order`에 대한 바인딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-141">For instance, the clause `Path=ShoppingCart.Order` sets the binding to the subproperty `Order` of the object or property `ShoppingCart`.</span></span>  
  
-   <span data-ttu-id="fd121-142">연결된 속성에 바인딩하려면 연결된 속성을 괄호로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-142">To bind to an attached property, place parentheses around the attached property.</span></span> <span data-ttu-id="fd121-143">예를 들어, 연결된 된 속성에 바인딩할 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, 구문은 `Path=(DockPanel.Dock)`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-143">For example, to bind to the attached property <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, the syntax is `Path=(DockPanel.Dock)`.</span></span>  
  
-   <span data-ttu-id="fd121-144">속성의 인덱서는 인덱서가 적용되는 속성 이름 뒤에 대괄호로 묶어서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-144">Indexers of a property can be specified within square brackets following the property name where the indexer is applied.</span></span> <span data-ttu-id="fd121-145">예를 들어 `Path=ShoppingCart[0]` 절은 속성의 내부 인덱싱에서 리터럴 문자열 "0"을 처리하는 방법에 해당하는 인덱스에 대한 바인딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-145">For instance, the clause `Path=ShoppingCart[0]` sets the binding to the index that corresponds to how your property's internal indexing handles the literal string "0".</span></span> <span data-ttu-id="fd121-146">중첩된 인덱서도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-146">Nested indexers are also supported.</span></span>  
  
-   <span data-ttu-id="fd121-147">`Path=ShoppingCart.ShippingInfo[MailingAddress,Street].`와 같이 `Path` 절에서 인덱서와 하위 속성을 혼합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-147">Indexers and subproperties can be mixed in a `Path` clause; for example, `Path=ShoppingCart.ShippingInfo[MailingAddress,Street].`</span></span>  
  
-   <span data-ttu-id="fd121-148">여러 인덱서 매개 변수를 쉼표(,)로 구분하여 인덱서 안에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-148">Inside indexers you can have multiple indexer parameters separated by commas (,).</span></span> <span data-ttu-id="fd121-149">각 매개 변수의 형식은 괄호를 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-149">The type of each parameter can be specified with parentheses.</span></span> <span data-ttu-id="fd121-150">예를 들어 `Path="[(sys:Int32)42,(sys:Int32)24]"`를 사용할 수 있으며 여기서 `sys`는 `System` 네임스페이스에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-150">For example, you can have `Path="[(sys:Int32)42,(sys:Int32)24]"`, where `sys` is mapped to the `System` namespace.</span></span>  
  
-   <span data-ttu-id="fd121-151">소스가 컬렉션 뷰인 경우 슬래시(/)를 사용하여 현재 항목을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-151">When the source is a collection view, the current item can be specified with a slash (/).</span></span> <span data-ttu-id="fd121-152">예를 들어 `Path=/` 절은 뷰의 현재 항목에 대한 바인딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-152">For example, the clause `Path=/` sets the binding to the current item in the view.</span></span> <span data-ttu-id="fd121-153">소스가 컬렉션인 경우 이 구문은 기본 컬렉션 뷰의 현재 항목을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-153">When the source is a collection, this syntax specifies the current item of the default collection view.</span></span>  
  
-   <span data-ttu-id="fd121-154">속성 이름과 슬래시를 결합하여 컬렉션인 속성을 트래버스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-154">Property names and slashes can be combined to traverse properties that are collections.</span></span> <span data-ttu-id="fd121-155">예를 들어 `Path=/Offices/ManagerName`은 소스 컬렉션의 현재 항목을 지정하며 여기에는 컬렉션인 `Offices` 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-155">For example, `Path=/Offices/ManagerName` specifies the current item of the source collection, which contains an `Offices` property that is also a collection.</span></span> <span data-ttu-id="fd121-156">현재 항목은 `ManagerName` 속성을 포함하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-156">Its current item is an object that contains a `ManagerName` property.</span></span>  
  
-   <span data-ttu-id="fd121-157">필요에 따라 마침표(.) 경로를 사용하여 현재 소스에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-157">Optionally, a period (.) path can be used to bind to the current source.</span></span> <span data-ttu-id="fd121-158">예를 들어 `Text="{Binding}"`은 `Text="{Binding Path=.}"`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-158">For example, `Text="{Binding}"` is equivalent to `Text="{Binding Path=.}"`.</span></span>  
  
### <a name="escaping-mechanism"></a><span data-ttu-id="fd121-159">이스케이프 메커니즘</span><span class="sxs-lookup"><span data-stu-id="fd121-159">Escaping Mechanism</span></span>  
  
-   <span data-ttu-id="fd121-160">인덱서([ ]) 안의 캐럿 문자(^)는 다음 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-160">Inside indexers ([ ]), the caret character (^) escapes the next character.</span></span>  
  
-   <span data-ttu-id="fd121-161">설정한 경우 <xref:System.Windows.Data.Binding.Path%2A> xaml에서는 또한 이스케이프 해야 (XML 엔터티를 사용 하 여) 특수 한 의미 XML 언어 정의를 특정 문자:</span><span class="sxs-lookup"><span data-stu-id="fd121-161">If you set <xref:System.Windows.Data.Binding.Path%2A> in XAML, you also need to escape (using XML entities) certain characters that are special to the XML language definition:</span></span>  
  
    -   <span data-ttu-id="fd121-162">"&" 문자를 이스케이프하려면 `&`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-162">Use `&` to escape the character "&".</span></span>  
  
    -   <span data-ttu-id="fd121-163">">" 태그를 이스케이프하려면 `>`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-163">Use `>` to escape the end tag ">".</span></span>  
  
-   <span data-ttu-id="fd121-164">또한 태그 확장 구문을 사용하여 특성의 전체 바인딩을 설명하는 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 태그 확장 파서와 관련된 문자를 이스케이프(백슬래시 \\ 사용)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-164">Additionally, if you describe the entire binding in an attribute using the markup extension syntax, you need to escape (using backslash \\) characters that are special to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] markup extension parser:</span></span>  
  
    -   <span data-ttu-id="fd121-165">백슬래시(\\)는 그 자체로 이스케이프 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-165">Backslash (\\) is the escape character itself.</span></span>  
  
    -   <span data-ttu-id="fd121-166">등호(=)는 속성 값에서 속성 이름을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-166">The equal sign (=) separates property name from property value.</span></span>  
  
    -   <span data-ttu-id="fd121-167">쉼표(,)는 속성을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-167">Comma (,) separates properties.</span></span>  
  
    -   <span data-ttu-id="fd121-168">오른쪽 중괄호(})는 태그 확장의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-168">The right curly brace (}) is the end of a markup extension.</span></span>  
  
<a name="Default"></a>   
## <a name="default-behaviors"></a><span data-ttu-id="fd121-169">기본 동작</span><span class="sxs-lookup"><span data-stu-id="fd121-169">Default Behaviors</span></span>  
 <span data-ttu-id="fd121-170">선언에서 지정되지 않은 경우 기본 동작은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-170">The default behavior is as follows if not specified in the declaration.</span></span>  
  
-   <span data-ttu-id="fd121-171">바인딩 소스 값과 바인딩 대상 값 간에 형식을 변환하는 기본 변환기가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-171">A default converter is created that tries to do a type conversion between the binding source value and the binding target value.</span></span> <span data-ttu-id="fd121-172">변환을 만들 수 없는 경우 기본 변환기는 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-172">If a conversion cannot be made, the default converter returns `null`.</span></span>  
  
-   <span data-ttu-id="fd121-173">설정 하지 않으면 <xref:System.Windows.Data.Binding.ConverterCulture%2A>, 바인딩 엔진에서 사용 하 여는 `Language` 바인딩 대상 개체의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-173">If you do not set <xref:System.Windows.Data.Binding.ConverterCulture%2A>, the binding engine uses the `Language` property of the binding target object.</span></span> <span data-ttu-id="fd121-174">XAML에서 이 값을 명시적으로 설정하지 않은 경우 기본적으로 "en-US"로 설정되거나 페이지 루트 요소(또는 임의의 요소)에서 값이 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-174">In XAML, this defaults to "en-US" or inherits the value from the root element (or any element) of the page, if one has been explicitly set.</span></span>  
  
-   <span data-ttu-id="fd121-175">바인딩에 이미 데이터 컨텍스트가 있고(예: 부모 요소에서 데이터 컨텍스트가 상속된 경우) 컨텍스트에서 반환 중인 항목 또는 컬렉션이 경로 수정 없이도 바인딩에 적합한 경우 바인딩 선언에 절을 사용하지 않아도 됩니다(`{Binding}`). 이러한 방법으로 데이터 스타일링에 바인딩이 지정되는 경우가 종종 있으며 이 경우 바인딩이 컬렉션에 대해 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-175">As long as the binding already has a data context (for instance, the inherited data context coming from a parent element), and whatever item or collection being returned by that context is appropriate for binding without requiring further path modification, a binding declaration can have no clauses at all: `{Binding}` This is often the way a binding is specified for data styling, where the binding acts upon a collection.</span></span> <span data-ttu-id="fd121-176">자세한 내용은 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)의 "전체 개체를 바인딩 소스로 사용" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd121-176">For more information, see the "Entire Objects Used as a Binding Source" section in the [Binding Sources Overview](../../../../docs/framework/wpf/data/binding-sources-overview.md).</span></span>  
  
-   <span data-ttu-id="fd121-177">기본 <xref:System.Windows.Data.Binding.Mode%2A> 단방향 및 양방향 바인딩되는 종속성 속성에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-177">The default <xref:System.Windows.Data.Binding.Mode%2A> varies between one-way and two-way depending on the dependency property that is being bound.</span></span> <span data-ttu-id="fd121-178">바인딩이 원하는 대로 동작하도록 항상 바인딩 모드를 명시적으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-178">You can always declare the binding mode explicitly to ensure that your binding has the desired behavior.</span></span> <span data-ttu-id="fd121-179">일반적으로 사용자가 편집 가능한 컨트롤 속성의 같은 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A?displayProperty=nameWithType>의 기본값은 양방향 바인딩으로 설정 되지만 대부분의 다른 속성 기본값은 단방향 바인딩으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-179">In general, user-editable control properties, such as <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A?displayProperty=nameWithType>, default to two-way bindings, whereas most other properties default to one-way bindings.</span></span>  
  
-   <span data-ttu-id="fd121-180">기본 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값 다르게 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> 및 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> 는 바인딩된 종속성 속성에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-180">The default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value varies between <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> and <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> depending on the bound dependency property as well.</span></span> <span data-ttu-id="fd121-181">대부분의 종속성 속성에 대한 기본값이 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>인 반면 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> 속성의 기본값은 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>입니다.</span><span class="sxs-lookup"><span data-stu-id="fd121-181">The default value for most dependency properties is <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, while the <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> property has a default value of <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd121-182">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd121-182">See Also</span></span>  
 [<span data-ttu-id="fd121-183">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="fd121-183">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="fd121-184">방법 항목</span><span class="sxs-lookup"><span data-stu-id="fd121-184">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [<span data-ttu-id="fd121-185">데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="fd121-185">Data Binding</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [<span data-ttu-id="fd121-186">PropertyPath XAML 구문</span><span class="sxs-lookup"><span data-stu-id="fd121-186">PropertyPath XAML Syntax</span></span>](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md)
