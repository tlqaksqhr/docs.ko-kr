---
title: "방법: SystemFonts 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "클래스, SystemFonts"
  - "글꼴, 시스템 글꼴"
  - "시스템 글꼴"
  - "SystemFonts 클래스"
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
caps.latest.revision: 27
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# 방법: SystemFonts 사용
이 예제에서는 <xref:System.Windows.SystemFonts> 클래스의 정적 리소스를 사용하여 단추에 스타일을 지정하거나 단추를 사용자 지정하는 방법을 보여 줍니다.  
  
## 예제  
 시스템 설정과 일관된 시각적 효과를 만들도록 지원하기 위해 시스템 리소스는 몇 가지 시스템 값을 리소스와 속성 모두로 노출합니다.  <xref:System.Windows.SystemFonts>는 정적 속성으로서의 시스템 글꼴 값과 런타임에 이러한 값에 동적으로 액세스하는 데 사용할 수 있는 리소스 키를 참조하는 속성이 모두 들어 있는 클래스입니다.  예를 들어 <xref:System.Windows.SystemFonts.CaptionFontFamily%2A>는 <xref:System.Windows.SystemFonts> 값이고 <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>는 해당하는 리소스 키입니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서는 <xref:System.Windows.SystemFonts>의 멤버를 정적 속성 또는 동적 리소스 참조\(정적 속성 값을 키로 사용하는 경우\) 중 하나로 사용할 수 있습니다.  응용 프로그램이 실행되는 동안 글꼴 메트릭을 자동으로 업데이트하려면 동적 리소스 참조를 사용하고 자동으로 업데이트하지 않으려면 정적 값 참조를 사용하십시오.  
  
> [!NOTE]
>  리소스 키의 경우 속성 이름 뒤에 "Key"라는 접미사가 붙습니다.  
  
 다음 예제에서는 <xref:System.Windows.SystemFonts>에 액세스한 후 해당 속성을 정적 값으로 사용하여 단추에 스타일을 지정하거나 단추를 사용자 지정하는 방법을 보여 줍니다.  이 태그 예제에서는 단추에 <xref:System.Windows.SystemFonts> 값을 할당합니다.  
  
 [!code-xml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 코드에 <xref:System.Windows.SystemFonts> 값을 사용하려는 경우 정적 값 또는 동적 리소스 참조 중 하나를 사용할 필요가 없습니다.  이때는 <xref:System.Windows.SystemFonts> 클래스의 키가 아닌 속성을 사용하십시오.  키가 아닌 속성이 정적 속성으로 정의된 것처럼 보이더라도 시스템에서 호스팅되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 런타임에 속성을 실시간으로 다시 평가하여 시스템 값에 대해 사용자가 수행한 변경 작업을 적절하게 처리합니다.  다음 예제에서는 단추의 글꼴 설정을 지정하는 방법을 보여 줍니다.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## 참고 항목  
 <xref:System.Windows.SystemFonts>   
 [시스템 브러시로 영역 그리기](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [SystemParameters 사용](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)   
 [시스템 글꼴 키 사용](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)   
 [방법 항목](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)   
 [x:Static 태그 확장](../../../../docs/framework/xaml-services/x-static-markup-extension.md)   
 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)