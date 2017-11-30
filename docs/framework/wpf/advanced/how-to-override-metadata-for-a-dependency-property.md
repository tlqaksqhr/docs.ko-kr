---
title: "방법: 종속성 속성의 메타데이터 재정의"
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
- metadata [WPF], overriding for dependency properties
- dependency properties [WPF], overriding metadata for
- overriding metadata for dependency properties [WPF]
ms.assetid: f90f026e-60d8-428a-933d-edf0dba4441f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8e7cb01c81b5fb24830cbe0cc39befbadaf4405e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-override-metadata-for-a-dependency-property"></a><span data-ttu-id="5c69b-102">방법: 종속성 속성의 메타데이터 재정의</span><span class="sxs-lookup"><span data-stu-id="5c69b-102">How to: Override Metadata for a Dependency Property</span></span>
<span data-ttu-id="5c69b-103">호출 하 여 상속된 된 클래스에서 제공 되는 기본 종속성 속성 메타 데이터를 재정의 하는 방법을 보여 주는이 예제는 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 메서드와 유형별 메타 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c69b-103">This example shows how to override default dependency property metadata that comes from an inherited class, by calling the <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> method and providing type-specific metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c69b-104">예제</span><span class="sxs-lookup"><span data-stu-id="5c69b-104">Example</span></span>  
 <span data-ttu-id="5c69b-105">정의 하 여 해당 <xref:System.Windows.PropertyMetadata>는 클래스는 기본 값과 속성 시스템 콜백이 같은 종속성 속성의 동작을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c69b-105">By defining its <xref:System.Windows.PropertyMetadata>, a class can define the dependency property's behaviors, such as its default value and property system callbacks.</span></span> <span data-ttu-id="5c69b-106">여러 종속성 속성 클래스에는 이미 등록 프로세스의 일부로 설정된 기본 메타데이터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c69b-106">Many dependency property classes already have default metadata established as part of their registration process.</span></span> <span data-ttu-id="5c69b-107">여기에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]의 일부인 종속성 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c69b-107">This includes the dependency properties that are part of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)].</span></span> <span data-ttu-id="5c69b-108">해당 클래스 상속을 통해 종속성 속성을 상속받는 클래스에서는 원래 메타데이터를 재정의할 수 있으므로 메타데이터를 통해 변경할 수 있는 속성의 특성이 모든 서브클래스별 요구 사항과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="5c69b-108">A class that inherits the dependency property through its class inheritance can override the original metadata so that the characteristics of the property that can be altered through metadata will match any subclass-specific requirements.</span></span>  
  
 <span data-ttu-id="5c69b-109">종속성 속성에 대한 메타데이터의 재정의는 속성 시스템이 해당 속성을 사용하기 전에 수행되어야 합니다(속성을 등록하는 개체의 특정 인스턴스가 인스턴스화되는 시간과 같은 것으로 간주).</span><span class="sxs-lookup"><span data-stu-id="5c69b-109">Overriding metadata on a dependency property must be done prior to that property being placed in use by the property system (this equates to the time that specific instances of objects that register the property are instantiated).</span></span> <span data-ttu-id="5c69b-110">에 대 한 호출이 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 로 자신을 제공 하는 형식의 정적 생성자 내에서 수행 해야 합니다는 `forType` 의 매개 변수 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="5c69b-110">Calls to <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> must be performed within the static constructors of the type that provides itself as the `forType` parameter of <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>.</span></span> <span data-ttu-id="5c69b-111">소유자 형식의 인스턴스가 존재하는 메타데이터를 변경하려고 하면 예외가 발생하지는 않지만 속성 시스템에서 일관성 없는 동작이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5c69b-111">If you attempt to change metadata once instances of the owner type exist, this will not raise exceptions, but will result in inconsistent behaviors in the property system.</span></span> <span data-ttu-id="5c69b-112">또한 메타데이터 형식별로 한 번만 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c69b-112">Also, metadata can only be overridden once per type.</span></span> <span data-ttu-id="5c69b-113">동일한 형식의 메타데이터를 이어서 재정의하려고 하면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5c69b-113">Subsequent attempts to override metadata on the same type will raise an exception.</span></span>  
  
 <span data-ttu-id="5c69b-114">다음 예제에서는 사용자 정의 클래스 `MyAdvancedStateControl`은 `MyAdvancedStateControl`에 의해 `StateProperty`에 제공된 메타데이터를 새 속성 메타데이터로 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5c69b-114">In the following example, the custom class `MyAdvancedStateControl` overrides the metadata provided for `StateProperty` by `MyAdvancedStateControl` with new property metadata.</span></span> <span data-ttu-id="5c69b-115">예를 들어 새로 생성된 `MyAdvancedStateControl` 인스턴스에서 속성을 쿼리하면 `StateProperty`의 기본값이 `true`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c69b-115">For instance, the default value of the `StateProperty` is now `true` when the property is queried on a newly constructed `MyAdvancedStateControl` instance.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#myadvancedstatecontrol)]
[!code-vb[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#myadvancedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="5c69b-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c69b-116">See Also</span></span>  
 <xref:System.Windows.DependencyProperty>  
 [<span data-ttu-id="5c69b-117">종속성 속성 개요</span><span class="sxs-lookup"><span data-stu-id="5c69b-117">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="5c69b-118">사용자 지정 종속성 속성</span><span class="sxs-lookup"><span data-stu-id="5c69b-118">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [<span data-ttu-id="5c69b-119">방법 항목</span><span class="sxs-lookup"><span data-stu-id="5c69b-119">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
