---
title: "방법: 종속성 속성의 소유자 형식 추가 | Microsoft Docs"
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
  - "클래스, 종속성 속성의 소유자로 추가"
  - "종속성 속성, 소유자로 클래스 추가"
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 종속성 속성의 소유자 형식 추가
이 예제에서는 다른 형식에 등록된 종속성 속성의 소유자로 클래스를 추가하는 방법을 보여 줍니다.  이렇게 하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 판독기 및 속성 시스템이 모두 이 클래스를 속성의 추가 소유자로 인식할 수 있습니다.  클래스를 소유자로 추가하는 경우 해당 클래스가 형식별 메타데이터를 제공하도록 할 수 있습니다.  
  
 다음 예제에서 `StateProperty`는 `MyStateControl` 클래스에 등록된 속성입니다.  `UnrelatedStateControl` 클래스는 <xref:System.Windows.DependencyProperty.AddOwner%2A> 메서드를 사용하고 추가 형식에 있는 종속성 속성의 새 메타데이터를 허용하는 시그니처를 사용하여 자신을 `StateProperty`의 소유자로 추가합니다.  [종속성 속성 구현](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) 예제에 나오는 것과 비슷한 속성에는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 접근자를 제공해야 하며 소유자로 추가하는 클래스에서 종속성 속성 식별자를 다시 노출해야 합니다.  
  
 래퍼가 없어도 프로그래밍 방식의 액세스 측면에서 보면 <xref:System.Windows.DependencyObject.GetValue%2A> 또는 <xref:System.Windows.DependencyObject.SetValue%2A>를 사용하여 종속성 속성이 작동합니다.  하지만 이 종속 시스템 동작은 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성 래퍼와 함께 사용하는 것이 일반적입니다.  래퍼가 있으면 종속성 속성을 프로그래밍 방식으로 훨씬 쉽게 설정할 수 있으며 속성을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 특성으로 설정할 수도 있습니다.  
  
 기본 메타데이터를 재정의하는 방법은 [종속성 속성의 메타데이터 재정의](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md)를 참조하십시오.  
  
## 예제  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## 참고 항목  
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)