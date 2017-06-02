---
title: "XAML 로드 및 종속성 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "사용자 지정 종속성 속성"
  - "종속성 속성, XAML 로드"
  - "XML 데이터 로드"
ms.assetid: 6eea9f4e-45ce-413b-a266-f08238737bf2
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# XAML 로드 및 종속성 속성
현재 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 구현할 때는 기본적으로 종속성 속성을 인식합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서는 이진 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 로드하고 종속성 속성인 특성을 처리할 때 종속성 속성에 대해 속성 시스템 메서드를 사용합니다.  이렇게 하면 속성 래퍼를 효과적으로 우회할 수 있습니다.  사용자 지정 종속성 속성을 구현할 때는 이 동작을 고려하고 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A> 속성 시스템 메서드 이외의 다른 코드를 속성 래퍼에 사용하지 않아야 합니다.  
  
   
  
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목에서는 사용자가 소비자와 작성자의 입장에서 종속성 속성을 이해하고 있으며 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) 및 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)을 읽었다고 가정합니다.  또한 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) 및 [XAML 구문 정보](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)도 읽어야 합니다.  
  
<a name="implementation"></a>   
## WPF XAML 로더 구현 및 성능  
 구현상의 이유로, 속성 래퍼와 setter를 사용하는 것보다 속성을 종속성 속성으로 식별하고 속성 시스템 <xref:System.Windows.DependencyObject.SetValue%2A> 메서드에 액세스하여 설정하는 것이 계산적인 측면에서 비용이 덜 듭니다.  이는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 태그 구조 및 여러 문자열로 나타나는 형식과 멤버 관계만 보고 백업 코드의 전체 개체 모델을 유추해야 하기 때문입니다.  
  
 형식을 조회할 때는 xmlns와 어셈블리 특성을 함께 사용하지만, 멤버를 확인하고 어떤 멤버가 특성으로 설정되는 것을 지원하는지 판단하고 속성 값이 지원하는 형식을 결정하려면 <xref:System.Reflection.PropertyInfo>를 사용한 많은 리플렉션이 필요합니다.  특정 형식에 대한 종속성 속성은 속성 시스템을 통해 저장소 테이블로 액세스할 수 있기 때문에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 구현할 때는 이 테이블을 바탕으로 종속성 속성 식별자 *ABCProperty*를 사용하여, 포함 <xref:System.Windows.DependencyObject> 파생 형식에 대해 <xref:System.Windows.DependencyObject.SetValue%2A>를 호출함으로써 모든 지정된 속성 *ABC*를 더 효율적으로 설정할 수 있음을 유추합니다.  
  
<a name="implications"></a>   
## 사용자 지정 종속성 속성의 의미  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서의 속성 설정 동작으로 현재 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 구현할 때는 래퍼를 완전히 우회하기 때문에 사용자 지정 종속성 속성에 대한 래퍼 집합 정의에 추가 논리를 넣지 않아야 합니다.  집합 정의에 이러한 논리를 넣으면 속성이 코드가 아닌 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]로 설정된 경우 논리가 실행되지 않습니다.  
  
 이와 마찬가지로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 처리로 속성 값을 가져오는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서의 다른 측면 역시 래퍼를 사용하는 대신 <xref:System.Windows.DependencyObject.GetValue%2A>를 사용합니다.  따라서 `get` 정의에 <xref:System.Windows.DependencyObject.GetValue%2A> 호출 이외의 추가 구현을 사용하지 않아야 합니다.  
  
 다음 예제는 래퍼에 권장되는 종속성 속성 정의로서, 여기서 속성 식별자는 `public` `static` `readonly` 필드로 저장되고, `get` 및 `set` 정의에는 종속성 속성 백업을 정의하는 필수 속성 시스템 메서드 이외의 코드는 포함되어 있지 않습니다.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## 참고 항목  
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [컬렉션 형식 종속성 속성](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)   
 [종속성 속성 보안](../../../../docs/framework/wpf/advanced/dependency-property-security.md)   
 [DependencyObject의 안전한 생성자 패턴](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)