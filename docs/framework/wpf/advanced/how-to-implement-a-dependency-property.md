---
title: "방법: 종속성 속성 구현 | Microsoft Docs"
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
  - "종속성 속성, 속성 백업"
  - "속성, 종속성 속성으로 백업"
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 방법: 종속성 속성 구현
이 예제에서는 <xref:System.Windows.DependencyProperty> 필드로 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성을 지원하여 [종속성 속성](GTMT)을 정의하는 방법을 보여 줍니다.  사용자 고유의 속성을 정의하고 이 속성이 스타일, 데이터 바인딩, 상속, 애니메이션 및 기본값을 포함하여 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 기능의 여러 측면을 지원하도록 하려면 해당 속성을 [종속성 속성](GTMT)으로 구현해야 합니다.  
  
## 예제  
 다음 예제에서는 먼저 <xref:System.Windows.DependencyProperty.Register%2A> 메서드를 호출하여 [종속성 속성](GTMT)을 등록합니다.  [종속성 속성](GTMT)의 이름과 특성을 저장하는 데 사용하는 식별자 필드의 이름은 <xref:System.Windows.DependencyProperty.Register%2A> 호출의 일부로 종속성 속성에 대해 선택한 <xref:System.Windows.DependencyProperty.Name%2A>에 리터럴 문자열 `Property`를 추가한 이름이어야 합니다.  예를 들어 종속성 속성을 `Location`의 <xref:System.Windows.DependencyProperty.Name%2A>에 등록한 경우 종속성 속성에 대해 정의하는 식별자 필드 이름은 `LocationProperty`여야 합니다.  
  
 이 예제에서 [종속성 속성](GTMT) 및 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 접근자의 이름은 `State`이고, 식별자 필드는 `StateProperty`이고, 속성의 유형은 <xref:System.Boolean>이며, [종속성 속성](GTMT)을 등록하는 유형은 `MyStateControl`입니다.  
  
 이 이름 지정 패턴을 준수하지 않으면 디자이너가 속성을 올바르게 보고하지 않거나 속성 시스템 스타일 응용 프로그램의 특정 측면이 예상대로 동작하지 않을 수 있습니다.  
  
 [종속성 속성](GTMT)에 대한 기본 메타데이터를 지정할 수도 있습니다.  이 예제에서는 `State` [종속성 속성](GTMT)의 기본값을 `false`로 등록합니다.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성을 전용 필드로 지원하는 대신 [종속성 속성](GTMT)을 구현하는 방법과 이유에 대한 자세한 내용은 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하십시오.  
  
## 참고 항목  
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)