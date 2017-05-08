---
title: "방법: SystemParameters 사용 | Microsoft Docs"
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
  - "클래스, SystemParameters"
  - "SystemParameters 클래스"
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# 방법: SystemParameters 사용
이 예제에서는 <xref:System.Windows.SystemParameters>의 속성에 액세스한 후 이를 사용하여 단추에 스타일을 지정하거나 단추를 사용자 지정하는 방법을 보여 줍니다.  
  
## 예제  
 시스템 리소스는 시스템 설정과 일관된 시각적 효과를 만들 수 있도록 몇 가지 시스템 기반 설정을 리소스로 노출합니다.  <xref:System.Windows.SystemParameters>는 시스템 매개 변수 값 속성과, 이러한 값에 바인딩되는 리소스 키를 포함하는 클래스입니다.  예를 들어 <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A>는 <xref:System.Windows.SystemParameters> 속성 값이고 <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>는 해당하는 리소스 키입니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서는 <xref:System.Windows.SystemParameters>의 멤버를 정적 속성이나 동적 리소스 참조\(정적 속성 값을 키로 사용\)로 사용할 수 있습니다.  응용 프로그램이 실행되는 동안 시스템 기반 값을 자동으로 업데이트하려면 동적 리소스 참조를 사용하고, 그렇지 않은 경우에는 정적 참조를 사용하십시오.  리소스 키의 경우 속성 이름 뒤에 `Key`라는 접미사가 붙습니다.  
  
 다음 예제에서는 <xref:System.Windows.SystemParameters>에 액세스한 후 해당 정적 값을 사용하여 단추에 스타일을 지정하거나 단추를 사용자 지정하는 방법을 보여 줍니다.  이 태그 예제에서는 단추에 <xref:System.Windows.SystemParameters> 값을 적용하여 단추의 크기를 지정합니다.  
  
 [!code-xml[SystemRes_snip#ParameterStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 코드에서 <xref:System.Windows.SystemParameters> 값을 사용하는 경우 정적 참조나 동적 리소스 참조를 사용할 필요가 없습니다.  대신 <xref:System.Windows.SystemParameters> 클래스의 값을 사용해야 합니다.  키가 아닌 속성은 명백하게 정적 속성으로 정의되지만, 시스템에서 호스팅될 때 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 런타임에 속성을 실시간으로 다시 평가하여 사용자가 시스템 값을 변경한 내용을 적절하게 고려합니다. 다음 예제에서는 <xref:System.Windows.SystemParameters> 값을 사용하여 단추의 너비와 높이를 설정하는 방법을 보여 줍니다.  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## 참고 항목  
 <xref:System.Windows.SystemParameters>   
 [시스템 브러시로 영역 그리기](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [SystemFonts 사용](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)   
 [시스템 매개 변수 키 사용](../../../../docs/framework/wpf/advanced/how-to-use-system-parameters-keys.md)   
 [방법 항목](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)