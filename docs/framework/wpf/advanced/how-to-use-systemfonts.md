---
title: "방법: SystemFonts 사용"
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
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2579926dfc71028590e09993e2773ee2cfac1505
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-systemfonts"></a><span data-ttu-id="c548f-102">방법: SystemFonts 사용</span><span class="sxs-lookup"><span data-stu-id="c548f-102">How to: Use SystemFonts</span></span>
<span data-ttu-id="c548f-103">정적 리소스를 사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.SystemFonts> 스타일 또는 단추를 사용자 지정 하려면 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c548f-103">This example shows how to use the static resources of the <xref:System.Windows.SystemFonts> class in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c548f-104">예</span><span class="sxs-lookup"><span data-stu-id="c548f-104">Example</span></span>  
 <span data-ttu-id="c548f-105">시스템 설정과 일관된 시각적 효과를 만들도록 지원하기 위해 시스템 리소스는 몇 가지 시스템이 결정하는 값을 리소스와 속성 모두로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="c548f-105">System resources expose several system-determined values as both resources and properties in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="c548f-106"><xref:System.Windows.SystemFonts>정적 속성 및 런타임 시 이러한 값을 동적으로 액세스 하는 데 사용할 수 있는 리소스 키를 참조 하는 속성 값이 모두 시스템 글꼴을 포함 하는 클래스가입니다.</span><span class="sxs-lookup"><span data-stu-id="c548f-106"><xref:System.Windows.SystemFonts> is a class that contains both system font values as static properties, and properties that reference resource keys that can be used to access those values dynamically at run time.</span></span> <span data-ttu-id="c548f-107">예를 들어 <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> 는 <xref:System.Windows.SystemFonts> 값 및 <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> 해당 리소스 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c548f-107">For example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> is a <xref:System.Windows.SystemFonts> value, and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> is a corresponding resource key.</span></span>  
  
 <span data-ttu-id="c548f-108">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 멤버를 사용할 수 <xref:System.Windows.SystemFonts> 정적 속성 또는 동적 리소스 참조 (정적 속성 값을 키로).</span><span class="sxs-lookup"><span data-stu-id="c548f-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemFonts> as either static properties or dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="c548f-109">응용 프로그램이 실행되는 동안 글꼴 메트릭을 자동으로 업데이트하려면 동적 리소스 참조를 사용하고 자동으로 업데이트하지 않으려면 정적 값 참조를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c548f-109">Use a dynamic resource reference if you want the font metric to automatically update while the application runs; otherwise, use a static value reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c548f-110">리소스 키의 경우 속성 이름 뒤에 “Key”라는 접미사가 붙습니다.</span><span class="sxs-lookup"><span data-stu-id="c548f-110">The resource keys have the suffix "Key" appended to the property name.</span></span>  
  
 <span data-ttu-id="c548f-111">다음 예제에서는 액세스 하 고 속성을 사용 하는 방법을 보여 줍니다 <xref:System.Windows.SystemFonts> 스타일 또는 단추를 사용자 지정 정적 값으로.</span><span class="sxs-lookup"><span data-stu-id="c548f-111">The following example shows how to access and use the properties of <xref:System.Windows.SystemFonts> as static values in order to style or customize a button.</span></span> <span data-ttu-id="c548f-112">지정 하는 태그 예제 <xref:System.Windows.SystemFonts> 를 단추에는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c548f-112">This markup example assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 <span data-ttu-id="c548f-113">값을 사용 하려면 <xref:System.Windows.SystemFonts> 코드에서 않아도 정적 값 또는 동적 리소스 참조를 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c548f-113">To use the values of <xref:System.Windows.SystemFonts> in code, you do not have to use either a static value or a dynamic resource reference.</span></span> <span data-ttu-id="c548f-114">키가 아닌 속성을 사용 하는 대신는 <xref:System.Windows.SystemFonts> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c548f-114">Instead, use the non-key properties of the <xref:System.Windows.SystemFonts> class.</span></span> <span data-ttu-id="c548f-115">키가 아닌 속성이 분명히 정적 속성의 런타임 동작으로 정의 된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서 호스팅될 때 실시간으로 속성을 다시 평가 됩니다 시스템과 적절히 시스템 값을 사용자가 수행한 변경 작업에 대 한 고려 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c548f-115">Although the non-key properties are apparently defined as static properties, the run-time behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in real time and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="c548f-116">다음 예제에서는 단추의 글꼴 설정을 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c548f-116">The following example shows how to specify the font settings of a button.</span></span>  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="c548f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c548f-117">See Also</span></span>  
 <xref:System.Windows.SystemFonts>  
 [<span data-ttu-id="c548f-118">시스템 브러시로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="c548f-118">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="c548f-119">SystemParameters 사용</span><span class="sxs-lookup"><span data-stu-id="c548f-119">Use SystemParameters</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [<span data-ttu-id="c548f-120">시스템 글꼴 키 사용</span><span class="sxs-lookup"><span data-stu-id="c548f-120">Use System Fonts Keys</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)  
 [<span data-ttu-id="c548f-121">방법 항목</span><span class="sxs-lookup"><span data-stu-id="c548f-121">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)  
 [<span data-ttu-id="c548f-122">x:Static 태그 확장</span><span class="sxs-lookup"><span data-stu-id="c548f-122">x:Static Markup Extension</span></span>](../../../../docs/framework/xaml-services/x-static-markup-extension.md)  
 [<span data-ttu-id="c548f-123">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="c548f-123">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="c548f-124">DynamicResource 태그 확장</span><span class="sxs-lookup"><span data-stu-id="c548f-124">DynamicResource Markup Extension</span></span>](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)
