---
title: '방법: 연결된 속성 등록'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF], registering
- registering attached properties [WPF]
ms.assetid: eb47bd94-0451-4f8d-8fb6-95f7812ac05b
ms.openlocfilehash: e6b0b461552811c5b3fca46a11f087f710e3b2e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544078"
---
# <a name="how-to-register-an-attached-property"></a><span data-ttu-id="a7967-102">방법: 연결된 속성 등록</span><span class="sxs-lookup"><span data-stu-id="a7967-102">How to: Register an Attached Property</span></span>
<span data-ttu-id="a7967-103">이 예제에서는 연결된 속성을 등록하고 public 접근자를 제공하여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]과 코드의 속성을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7967-103">This example shows how to register an attached property and provide public accessors so that you can use the property in both [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span> <span data-ttu-id="a7967-104">연결된 속성은 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 정의한 구문 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="a7967-104">Attached properties are a syntax concept defined by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="a7967-105">대부분의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 형식에 연결된 속성도 종속성 속성으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7967-105">Most attached properties for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] types are also implemented as dependency properties.</span></span> <span data-ttu-id="a7967-106">종속성 속성을 사용 하 여 모든에서 <xref:System.Windows.DependencyObject> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a7967-106">You can use dependency properties on any <xref:System.Windows.DependencyObject> types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7967-107">예제</span><span class="sxs-lookup"><span data-stu-id="a7967-107">Example</span></span>  
 <span data-ttu-id="a7967-108">다음 예제에서는 연결된 된 속성을 사용 하 여 종속성 속성으로 등록 하는 방법을 보여 줍니다는 <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="a7967-108">The following example shows how to register an attached property as a dependency property, by using the <xref:System.Windows.DependencyProperty.RegisterAttached%2A> method.</span></span> <span data-ttu-id="a7967-109">공급자 클래스에는 속성이 다른 클래스에 사용될 때 해당 클래스의 메타데이터를 재정의하지 않는 한 적용 가능한 속성에 대한 기본 메타데이터를 제공하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7967-109">The provider class has the option of providing default metadata for the property that is applicable when the property is used on another class, unless that class overrides the metadata.</span></span> <span data-ttu-id="a7967-110">이 예제에서는 `IsBubbleSource` 속성의 기본값은 `false`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7967-110">In this example, the default value of the `IsBubbleSource` property is set to `false`.</span></span>  
  
 <span data-ttu-id="a7967-111">종속성 속성으로 등록되지 않은 경우를 포함하여 연결된 속성에 대한 공급자 클래스는 명명 규칙 `Set`*[AttachedPropertyName]* 및 `Get`*[AttachedPropertyName]* 를 따르는 정적 get 및 set 접근자를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7967-111">The provider class for an attached property (even if it is not registered as a dependency property) must provide static get and set accessors that follow the naming convention `Set`*[AttachedPropertyName]* and `Get`*[AttachedPropertyName]*.</span></span> <span data-ttu-id="a7967-112">활성 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 판독기가 속성을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 특성으로 인식하고 적절한 형식을 확인할 수 있도록 이러한 접근자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a7967-112">These accessors are required so that the acting [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader can recognize the property as an attribute in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and resolve the appropriate types.</span></span>  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
## <a name="see-also"></a><span data-ttu-id="a7967-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7967-113">See Also</span></span>  
 <xref:System.Windows.DependencyProperty>  
 [<span data-ttu-id="a7967-114">종속성 속성 개요</span><span class="sxs-lookup"><span data-stu-id="a7967-114">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="a7967-115">사용자 지정 종속성 속성</span><span class="sxs-lookup"><span data-stu-id="a7967-115">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [<span data-ttu-id="a7967-116">방법 항목</span><span class="sxs-lookup"><span data-stu-id="a7967-116">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
