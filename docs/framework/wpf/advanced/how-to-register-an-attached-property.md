---
title: "방법: 연결된 속성 등록 | Microsoft Docs"
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
  - "연결된 속성, 등록"
  - "연결된 속성 등록"
ms.assetid: eb47bd94-0451-4f8d-8fb6-95f7812ac05b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 연결된 속성 등록
이 예제에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 및 코드 모두에서 속성을 사용할 수 있도록 [연결된 속성](GTMT)을 등록하고 public 접근자를 제공하는 방법을 보여 줍니다.  연결된 속성은 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 정의하는 구문 개념입니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 형식에 사용되는 대부분의 연결된 속성은 [종속성 속성](GTMT)으로도 구현됩니다.  모든 <xref:System.Windows.DependencyObject> 형식에 [종속성 속성](GTMT)을 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 메서드를 사용하여 연결된 속성을 종속성 속성으로 등록하는 방법을 보여 줍니다.  공급자 클래스는 클래스가 메타데이터를 재정의하지 않는 경우 다른 클래스에서 속성이 사용될 때 적용되는 속성의 기본 메타데이터를 제공할 수 있습니다.  이 예제에서는 `IsBubbleSource` 속성의 기본값이 `false`로 설정되어 있습니다.  
  
 연결된 속성\(종속성 속성으로 등록되어 있지 않은 경우에도 해당\)의 공급자 클래스는 `Set`*\[AttachedPropertyName\]* 및 `Get`*\[AttachedPropertyName\]* 명명 규칙에 따라 정적 get 및 set 접근자를 제공해야 합니다. 이 두 접근자는 실행 중인 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 판독기가 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 특성으로 속성을 인식하고 적절한 형식을 확인하는 데 필요합니다.  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
## 참고 항목  
 <xref:System.Windows.DependencyProperty>   
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [방법 항목](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)