---
title: "방법: 리소스 정의 및 참조 | Microsoft Docs"
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
  - "리소스 정의"
  - "리소스 참조"
  - "리소스, 정의"
  - "리소스, 참조"
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 리소스 정의 및 참조
이 예제에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]의 특성을 사용하여 리소스를 정의하고 참조하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 두 가지 리소스 형식 즉, 한 개의 <xref:System.Windows.Media.SolidColorBrush> 리소스와 여러 개의 <xref:System.Windows.Style> 리소스를 정의합니다.  <xref:System.Windows.Media.SolidColorBrush> 리소스 `MyBrush`는 각 <xref:System.Windows.Media.Brush> 형식 값을 사용하는 여러 속성의 값을 제공하는 데 사용됩니다.  <xref:System.Windows.Style> 리소스 `PageBackground`, `TitleText` 및 `Label`은 특정 컨트롤 형식을 대상으로 합니다.  해당 스타일 리소스가 리소스 키에 의해 참조되고 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 정의된 여러 특정 컨트롤 요소의 <xref:System.Windows.FrameworkElement.Style%2A> 속성을 설정하는 데 사용되는 경우 스타일은 대상 컨트롤에서 다양한 속성을 설정합니다.  
  
 또한 `Label` 스타일의 setter 내 속성 중 하나는 앞에서 정의한 `MyBrush` 리소스를 참조합니다.  이는 일반적인 기법에 해당되지만, 리소스는 제공된 순서로 구분 분석되어 리소스 사전에 입력됨을 알아야 합니다.  또한 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)을 사용하여 다른 리소스 내에서 리소스를 참조하는 경우 사전 내에서 발견되는 순서로 리소스가 요청됩니다.  참조하는 리소스가 리소스 컬렉션 내에서 리소스가 요청되는 위치보다 앞쪽에 정의되어 있는지 확인해야 합니다.  필요에 따라 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)을 사용하여 엄격한 리소스 참조의 생성 순서를 적용하여 대신 런타임에 리소스를 참조하게 만들 수 있지만 이 DynamicResource 기법은 성능과 관련되어 있습니다.  자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하십시오.  
  
 [!code-xml[FEResource#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## 참고 항목  
 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)