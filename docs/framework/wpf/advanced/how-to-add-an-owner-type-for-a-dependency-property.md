---
title: "방법: 종속성 속성의 소유자 형식 추가"
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
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b93934c8f84a7257445b530e27896342bdd73aea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a><span data-ttu-id="e251c-102">방법: 종속성 속성의 소유자 형식 추가</span><span class="sxs-lookup"><span data-stu-id="e251c-102">How to: Add an Owner Type for a Dependency Property</span></span>
<span data-ttu-id="e251c-103">이 예제는 클래스를 다른 형식에 대해 등록 된 종속성 속성의 소유자로 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e251c-103">This example shows how to add a class as an owner of a dependency property registered for a different type.</span></span> <span data-ttu-id="e251c-104">이 수행 하 여는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 판독기 및 속성 시스템은 모두 속성의 소유자로 추가 클래스를 인식할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e251c-104">By doing this, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader and property system are both able to recognize the class as an additional owner of the property.</span></span> <span data-ttu-id="e251c-105">필요에 따라 소유자로 추가 추가 하는 클래스 형식별 메타 데이터를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e251c-105">Adding as owner optionally allows the adding class to provide type-specific metadata.</span></span>  
  
 <span data-ttu-id="e251c-106">다음 예에서 `StateProperty` 하 여 등록 하는 속성은 `MyStateControl` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e251c-106">In the following example, `StateProperty` is a property registered by the `MyStateControl` class.</span></span> <span data-ttu-id="e251c-107">클래스 `UnrelatedStateControl` 자체의 소유자로 추가 `StateProperty` 를 사용 하는 <xref:System.Windows.DependencyProperty.AddOwner%2A> 메서드를 추가 하는 형식에 있는 종속성 속성에 대 한 새 메타 데이터에 대 한 허용 하는 시그니처를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="e251c-107">The class `UnrelatedStateControl` adds itself as an owner of the `StateProperty` using the <xref:System.Windows.DependencyProperty.AddOwner%2A> method, specifically using the signature that allows for new metadata for the dependency property as it exists on the adding type.</span></span> <span data-ttu-id="e251c-108">제공 해야 하는 알림 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 에 표시 된 예제와 비슷한 속성에 대 한 접근자는 [종속성 속성을 구현](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) 등으로 다시 추가 하는 클래스에서 종속성 속성 식별자를 노출 소유자입니다.</span><span class="sxs-lookup"><span data-stu-id="e251c-108">Notice that you should provide [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] accessors for the property similar to the example shown in the [Implement a Dependency Property](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) example, as well as re-expose the dependency property identifier on the class being added as owner.</span></span>  
  
 <span data-ttu-id="e251c-109">래퍼에 없는 종속성 속성에도 작동 사용 하 여 프로그래밍 방식 액세스의 관점에서 <xref:System.Windows.DependencyObject.GetValue%2A> 또는 <xref:System.Windows.DependencyObject.SetValue%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="e251c-109">Without wrappers, the dependency property would still work from the perspective of programmatic access using <xref:System.Windows.DependencyObject.GetValue%2A> or <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="e251c-110">하지만 일반적으로이 속성 시스템 동작은와 하려는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성 래퍼 합니다.</span><span class="sxs-lookup"><span data-stu-id="e251c-110">But you typically want to parallel this property-system behavior with the [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] property wrappers.</span></span> <span data-ttu-id="e251c-111">래퍼 더 쉽게 종속성 속성을 프로그래밍 방식으로 설정 하 고로 속성을 설정할 수 있게 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="e251c-111">The wrappers make it easier to set the dependency property programmatically, and make it possible to set the properties as [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributes.</span></span>  
  
 <span data-ttu-id="e251c-112">기본 메타 데이터를 재정의 하는 방법을 알아보려면 참조 [종속성 속성에 대 한 메타 데이터 재정의](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e251c-112">To find out how to override default metadata, see [Override Metadata for a Dependency Property](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e251c-113">예</span><span class="sxs-lookup"><span data-stu-id="e251c-113">Example</span></span>  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="e251c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e251c-114">See Also</span></span>  
 [<span data-ttu-id="e251c-115">사용자 지정 종속성 속성</span><span class="sxs-lookup"><span data-stu-id="e251c-115">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [<span data-ttu-id="e251c-116">종속성 속성 개요</span><span class="sxs-lookup"><span data-stu-id="e251c-116">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
