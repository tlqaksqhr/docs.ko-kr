---
title: "방법: 종속성 속성의 메타데이터 재정의 | Microsoft Docs"
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
  - "종속성 속성, 메타데이터 재정의"
  - "메타데이터, 종속성 속성에 대해 재정의"
  - "종속성 속성에 대해 메타데이터 재정의"
ms.assetid: f90f026e-60d8-428a-933d-edf0dba4441f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 종속성 속성의 메타데이터 재정의
이 예제에서는 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 메서드를 호출하고 형식별 메타데이터를 제공하여 상속된 클래스가 제공하는 기본 종속성 속성 메타데이터를 재정의하는 방법을 보여 줍니다.  
  
## 예제  
 클래스는 해당 <xref:System.Windows.PropertyMetadata>를 정의하여 기본값 및 속성 시스템 콜백과 같은 [종속성 속성](GTMT)의 동작을 정의할 수 있습니다.  대부분의 종속성 속성 클래스의 경우 클래스를 등록하는 동안 기본 메타데이터가 설정됩니다.  여기에는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]의 일부인 종속성 속성이 포함됩니다.  클래스 상속을 통해 종속성 속성을 상속하는 클래스는 메타데이터를 통해 변경할 수 있는 속성의 특성이 모든 서브클래스별 요구 사항과 일치하도록 원래 메타데이터를 재정의할 수 있습니다.  
  
 종속성 속성에 대한 메타데이터 재정의는 속성 시스템에서 사용하도록 해당 속성을 배치하기 전에 수행해야 합니다. 이는 속성을 등록하는 특정 개체 인스턴스가 인스턴스화되는 시점과 일치합니다.  <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 호출은 자신을 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>의 `forType`의 매개 변수로 제공하는 형식의 정적 생성자 내에서 수행해야 합니다.  소유자 형식의 인스턴스가 생성된 후 메타데이터를 변경해도 예외가 발생하지는 않지만 속성 시스템의 동작이 일정하지 않게 됩니다.  뿐만 아니라 메타데이터는 형식 하나당 한 번만 재정의할 수 있습니다.  같은 형식에서 메타데이터를 그 이상 재정의하면 예외가 발생합니다.  
  
 다음 예제에서는 사용자 지정 클래스 `MyAdvancedStateControl`이 `MyAdvancedStateControl`이 제공한 `StateProperty`의 메타데이터를 새 속성 메타데이터로 재정의합니다.  예를 들어, 새로 생성된 `MyAdvancedStateControl` 인스턴스에서 속성을 쿼리하면 `StateProperty`의 기본값이 이제 `true`입니다.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#myadvancedstatecontrol)]
[!code-vb[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#myadvancedstatecontrol)]  
  
## 참고 항목  
 <xref:System.Windows.DependencyProperty>   
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [방법 항목](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)