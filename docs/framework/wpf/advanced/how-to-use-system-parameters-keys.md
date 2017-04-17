---
title: "방법: 시스템 매개 변수 키 사용 | Microsoft Docs"
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
  - "리소스 키, SystemParameters 클래스"
  - "SystemParameters 클래스"
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: 시스템 매개 변수 키 사용
시스템 리소스는 개발자가 시스템 설정과 일관된 시각적 효과를 만들 수 있도록 몇 가지 시스템 메트릭을 리소스로 노출합니다.  <xref:System.Windows.SystemParameters>는 시스템 매개 변수 값과 이러한 값에 바인딩되는 리소스 키\(예: <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> 및 <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>\)를 모두 포함하는 클래스입니다.  시스템 매개 변수 메트릭은 정적 리소스나 동적 리소스로 사용될 수 있습니다.  응용 프로그램이 실행되는 동안 매개 변수 메트릭을 자동으로 업데이트하려면 동적 리소스를 사용하고 자동으로 업데이트하지 않으려면 정적 리소스를 사용하십시오.  
  
> [!NOTE]
>  동적 리소스의 경우 속성 이름에 *Key*라는 키워드가 추가됩니다.  
  
 다음 예제에서는 시스템 매개 변수 동적 리소스에 액세스한 후 사용하여 단추에 스타일을 지정하거나 단추를 사용자 지정하는 방법을 보여 줍니다.  이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제에서는 <xref:System.Windows.SystemParameters> 값을 단추의 너비와 높이에 할당하여 단추의 크기를 조정합니다.  
  
## 예제  
 [!code-xml[SystemRes_snip#ParameterDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## 참고 항목  
 [시스템 브러시로 영역 그리기](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [SystemFonts 사용](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)   
 [SystemParameters 사용](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)