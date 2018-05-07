---
title: '방법: SystemFonts 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: 305d0cf18db5dc96b2d3cde863cf4ba2ae8dbb96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-systemfonts"></a>방법: SystemFonts 사용
정적 리소스를 사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.SystemFonts> 스타일 또는 단추를 사용자 지정 하려면 클래스입니다.  
  
## <a name="example"></a>예제  
 시스템 설정과 일관된 시각적 효과를 만들도록 지원하기 위해 시스템 리소스는 몇 가지 시스템이 결정하는 값을 리소스와 속성 모두로 노출합니다. <xref:System.Windows.SystemFonts> 정적 속성 및 런타임 시 이러한 값을 동적으로 액세스 하는 데 사용할 수 있는 리소스 키를 참조 하는 속성 값이 모두 시스템 글꼴을 포함 하는 클래스가입니다. 예를 들어 <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> 는 <xref:System.Windows.SystemFonts> 값 및 <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> 해당 리소스 키입니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 멤버를 사용할 수 <xref:System.Windows.SystemFonts> 정적 속성 또는 동적 리소스 참조 (정적 속성 값을 키로). 응용 프로그램이 실행되는 동안 글꼴 메트릭을 자동으로 업데이트하려면 동적 리소스 참조를 사용하고 자동으로 업데이트하지 않으려면 정적 값 참조를 사용합니다.  
  
> [!NOTE]
>  리소스 키의 경우 속성 이름 뒤에 “Key”라는 접미사가 붙습니다.  
  
 다음 예제에서는 액세스 하 고 속성을 사용 하는 방법을 보여 줍니다 <xref:System.Windows.SystemFonts> 스타일 또는 단추를 사용자 지정 정적 값으로. 지정 하는 태그 예제 <xref:System.Windows.SystemFonts> 를 단추에는 값입니다.  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 값을 사용 하려면 <xref:System.Windows.SystemFonts> 코드에서 않아도 정적 값 또는 동적 리소스 참조를 사용 하도록 합니다. 키가 아닌 속성을 사용 하는 대신는 <xref:System.Windows.SystemFonts> 클래스입니다. 키가 아닌 속성이 분명히 정적 속성의 런타임 동작으로 정의 된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서 호스팅될 때 실시간으로 속성을 다시 평가 됩니다 시스템과 적절히 시스템 값을 사용자가 수행한 변경 작업에 대 한 고려 됩니다. 다음 예제에서는 단추의 글꼴 설정을 지정하는 방법을 보여 줍니다.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.SystemFonts>  
 [시스템 브러시로 영역 그리기](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [SystemParameters 사용](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [시스템 글꼴 키 사용](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)  
 [방법 항목](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)  
 [x:Static 태그 확장](../../../../docs/framework/xaml-services/x-static-markup-extension.md)  
 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)
