---
title: "방법: 종속성 속성 구현"
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
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9bc4dee8f0b2eef76e5769ae7da3a13edf7c3300
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-dependency-property"></a><span data-ttu-id="4f48f-102">방법: 종속성 속성 구현</span><span class="sxs-lookup"><span data-stu-id="4f48f-102">How to: Implement a Dependency Property</span></span>
<span data-ttu-id="4f48f-103">백업 하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성을는 <xref:System.Windows.DependencyProperty> 필드에서 종속성 속성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f48f-103">This example shows how to back a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] property with a <xref:System.Windows.DependencyProperty> field, thus defining a dependency property.</span></span> <span data-ttu-id="4f48f-104">고유 속성을 정의하고 스타일, 데이터 바인딩, 상속, 애니메이션 및 기본값을 포함한 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 기능의 여러 측면을 지원하려면 해당 속성을 종속성 속성으로 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f48f-104">When you define your own properties and want them to support many aspects of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] functionality, including styles, data binding, inheritance, animation, and default values, you should implement them as a dependency property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f48f-105">예제</span><span class="sxs-lookup"><span data-stu-id="4f48f-105">Example</span></span>  
 <span data-ttu-id="4f48f-106">다음 예제에서는 호출 하 여 종속성 속성을 먼저 등록는 <xref:System.Windows.DependencyProperty.Register%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="4f48f-106">The following example first registers a dependency property by calling the <xref:System.Windows.DependencyProperty.Register%2A> method.</span></span> <span data-ttu-id="4f48f-107">종속성 속성의 특징 해야 및 이름을 저장 하는 사용 하는 식별자 필드의 이름은 <xref:System.Windows.DependencyProperty.Name%2A> 의 일환으로 종속성 속성에 대해 선택한는 <xref:System.Windows.DependencyProperty.Register%2A> 리터럴 문자열에 의해 추가 된 호출 `Property`합니다.</span><span class="sxs-lookup"><span data-stu-id="4f48f-107">The name of the identifier field that you use to store the name and characteristics of the dependency property must be the <xref:System.Windows.DependencyProperty.Name%2A> you chose for the dependency property as part of the <xref:System.Windows.DependencyProperty.Register%2A> call, appended by the literal string `Property`.</span></span> <span data-ttu-id="4f48f-108">예를 들어, 종속성 속성을 등록 하는 경우는 <xref:System.Windows.DependencyProperty.Name%2A> 의 `Location`, 종속성 속성에 대해 정의 하는 식별자 필드 이름을 지정 해야 하는 다음 `LocationProperty`합니다.</span><span class="sxs-lookup"><span data-stu-id="4f48f-108">For instance, if you register a dependency property with a <xref:System.Windows.DependencyProperty.Name%2A> of `Location`, then the identifier field that you define for the dependency property must be named `LocationProperty`.</span></span>  
  
 <span data-ttu-id="4f48f-109">이 예제에서는 종속성 속성의 이름 및 해당 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 접근자가 `State`; 식별자 필드는 `StateProperty`; 속성의 형식이 <xref:System.Boolean>; 종속성 속성을 등록 된 형식이 고 `MyStateControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="4f48f-109">In this example, the name of the dependency property and its [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] accessor is `State`; the identifier field is `StateProperty`; the type of the property is <xref:System.Boolean>; and the type that registers the dependency property is `MyStateControl`.</span></span>  
  
 <span data-ttu-id="4f48f-110">이 명명 패턴을 따르지 못한 경우 디자이너가 속성을 제대로 보고하지 않을 수 있으며 속성 시스템 스타일 응용 프로그램의 특정 측면이 예상대로 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f48f-110">If you fail to follow this naming pattern, designers might not report your property correctly, and certain aspects of property system style application might not behave as expected.</span></span>  
  
 <span data-ttu-id="4f48f-111">종속성 속성에 대한 기본 메타데이터를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f48f-111">You can also specify default metadata for a dependency property.</span></span> <span data-ttu-id="4f48f-112">이 예제에서는 `State` 종속성 속성의 기본값이 `false`로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f48f-112">This example registers the default value of the `State` dependency property to be `false`.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 <span data-ttu-id="4f48f-113">개인 필드가 있는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성을 단지 백업하는 것과는 반대로 종속성 속성을 구현하는 방법과 이유에 대한 자세한 내용은 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f48f-113">For more information about how and why to implement a dependency property, as opposed to just backing a [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] property with a private field, see [Dependency Properties Overview](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f48f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f48f-114">See Also</span></span>  
 [<span data-ttu-id="4f48f-115">종속성 속성 개요</span><span class="sxs-lookup"><span data-stu-id="4f48f-115">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="4f48f-116">방법 항목</span><span class="sxs-lookup"><span data-stu-id="4f48f-116">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
