---
title: "방법: 시스템 글꼴 키 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 53538c64d2af5d8407f79848ddcd01f7665303c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-system-fonts-keys"></a><span data-ttu-id="4fa3a-102">방법: 시스템 글꼴 키 사용</span><span class="sxs-lookup"><span data-stu-id="4fa3a-102">How to: Use System Fonts Keys</span></span>
<span data-ttu-id="4fa3a-103">시스템 리소스는 개발자가 시스템 설정과 일관된 시각적 효과를 만들 수 있도록 몇 가지 시스템 메트릭을 리소스로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="4fa3a-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="4fa3a-104"><xref:System.Windows.SystemFonts>시스템 글꼴 값과 값에 바인딩되는 시스템 글꼴 리소스를 모두 포함 하는 클래스-예를 들어 <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> 및 <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="4fa3a-104"><xref:System.Windows.SystemFonts> is a class that contains both system font values and system font resources that bind to the values—for example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span></span>  
  
 <span data-ttu-id="4fa3a-105">시스템 글꼴 메트릭은 정적 리소스나 동적 리소스로 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fa3a-105">System font metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="4fa3a-106">응용 프로그램이 실행되는 동안 글꼴 메트릭을 자동으로 업데이트하려면 동적 리소스를 사용하고 자동으로 업데이트하지 않으려면 정적 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4fa3a-106">Use a dynamic resource if you want the font metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4fa3a-107">동적 리소스는 키워드를 사용할 *키* 속성 이름에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fa3a-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="4fa3a-108">다음 예제에서는 시스템 글꼴 동적 리소스에 액세스한 후 사용하여 단추에 스타일을 지정하거나 단추를 사용자 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4fa3a-108">The following example shows how to access and use system font dynamic resources to style or customize a button.</span></span> <span data-ttu-id="4fa3a-109">이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 할당 하는 단추 스타일을 만드는 예제 <xref:System.Windows.SystemFonts> 를 단추에는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4fa3a-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example creates a button style that assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fa3a-110">예</span><span class="sxs-lookup"><span data-stu-id="4fa3a-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#FontDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="4fa3a-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4fa3a-111">See Also</span></span>  
 [<span data-ttu-id="4fa3a-112">시스템 브러시로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="4fa3a-112">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="4fa3a-113">SystemParameters 사용</span><span class="sxs-lookup"><span data-stu-id="4fa3a-113">Use SystemParameters</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [<span data-ttu-id="4fa3a-114">SystemFonts 사용</span><span class="sxs-lookup"><span data-stu-id="4fa3a-114">Use SystemFonts</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)
