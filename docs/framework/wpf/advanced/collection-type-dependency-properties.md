---
title: "컬렉션 형식 종속성 속성 | Microsoft Docs"
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
  - "컬렉션 형식 속성"
  - "종속성 속성"
  - "속성, 컬렉션 형식"
  - "속성, 종속성"
ms.assetid: 99f96a42-3ab7-4f64-a16b-2e10d654e97c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 컬렉션 형식 종속성 속성
이 항목에서는 속성의 형식이 컬렉션 형식인 [종속성 속성](GTMT)을 구현하는 방법에 대한 지침 및 제안 패턴을 제공합니다.  
  
   
  
<a name="implementing"></a>   
## 컬렉션 형식 종속성 속성 구현  
 일반적으로 종속성 속성의 경우에는 속성이 필드 또는 다른 구문이 아니라 <xref:System.Windows.DependencyProperty> 식별자에 기반하는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성 래퍼를 정의하는 구현 패턴을 따릅니다.  컬렉션 형식 속성을 구현할 때도 이와 같은 패턴을 따릅니다.  하지만 컬렉션 안에 포함된 형식 자체가 <xref:System.Windows.DependencyObject> 또는 <xref:System.Windows.Freezable> 파생 클래스인 경우에는 컬렉션 형식 속성으로 인해 패턴이 약간 복잡해집니다.  
  
<a name="initializing"></a>   
## 기본값을 벗어나 컬렉션 초기화  
 종속성 속성을 만들 때는 속성 기본값을 초기 필드 값으로 지정하지 않습니다.  대신 종속성 속성 메타데이터를 통해 기본값을 지정합니다.  속성이 참조 형식인 경우 종속성 속성 메타데이터에 지정된 기본값은 인스턴스별 기본값이 아니라 해당 형식의 모든 인스턴스에 적용되는 기본값입니다.  따라서 특정 형식으로 새로 만들어진 인스턴스의 기본값에 대한 작업을 수행할 때 컬렉션 속성 메타데이터로 정의된 단일 정적 컬렉션을 사용하지 않도록 주의해야 합니다.  대신 클래스 생성자 논리의 일부로 컬렉션 값을 고유한 \(인스턴스\) 컬렉션으로 설정해야 합니다.  그렇지 않으면 예상치 못한 singleton 클래스가 만들어집니다.  
  
 다음 예제를 살펴보십시오.  예제의 다음 섹션에서는 클래스 `Aquarium`의 정의를 보여 줍니다.  클래스는 <xref:System.Windows.FrameworkElement> 형식 제약 조건이 있는 제네릭 <xref:System.Collections.Generic.List%601> 형식을 사용하는 컬렉션 형식 종속성 속성 `AquariumObjects`를 정의합니다.  종속성 속성에 대한 <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29> 호출에서 메타데이터는 기본값을 새 제네릭 <xref:System.Collections.Generic.List%601>로 설정합니다.  
  
 <!-- TODO: review snippet reference [!code-csharp[PropertiesOvwSupport#CollectionProblemDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemdefinition)]  -->
 [!code-vb[PropertiesOvwSupport#CollectionProblemDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemdefinition)]  
[!code-csharp[PropertiesOvwSupport#CollectionProblemEndB](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemendb)]
[!code-vb[PropertiesOvwSupport#CollectionProblemEndB](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemendb)]  
  
 하지만 설명한 것처럼 코드를 벗어나면 `Aquarium`의 모든 인스턴스에서 단일 목록 기본값을 공유합니다.  두 개의 개별적인 `Aquarium` 인스턴스를 인스턴스화하고 서로에게 하나의 서로 다른 `Fish`를 추가하는 방법을 보여 주는 다음 테스트 코드를 실행하면 놀라운 결과를 보게 됩니다.  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemTestCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemtestcode)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemTestCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemtestcode)]  
  
 각 컬렉션의 숫자는 1이 아니라 2입니다.  이는 각 `Aquarium`이 해당 `Fish`를 메타데이터의 단일 생성자 호출의 결과이며 따라서 모든 인스턴스 사이에서 공유되는 기본값 컬렉션에 추가했기 때문입니다.  이것은 결코 의도하지 않은 상황입니다.  
  
 이 문제를 해결하려면 클래스 생성자 호출의 일부로 컬렉션 종속성 속성 값을 고유한 인스턴스로 재설정해야 합니다.  속성이 읽기 전용 종속성 속성이기 때문에 클래스 안에서만 액세스 가능한 <xref:System.Windows.DependencyPropertyKey>를 사용하여 <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> 메서드로 이 속성을 설정합니다.  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemctor)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemctor)]  
  
 이제 샘플 테스트 코드를 다시 실행하면 원하는 대로 각 `Aquarium`이 자체의 고유한 컬렉션을 지원하는 결과를 볼 수 있습니다.  
  
 컬렉션 속성을 읽기\-쓰기로 지정한 경우 이 패턴에 약간의 변형이 있습니다.  이 경우 생성자에서 public set 접근자를 호출하여 초기화를 수행할 수 있습니다. 이 경우 여전히 public <xref:System.Windows.DependencyProperty> 식별자를 사용하여 집합 래퍼 안에서 <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29>의 비 키 시그니처를 호출합니다.  
  
## 컬렉션 속성에서 바인딩 값 변경 보고  
 그 자체로 종속성 속성인 컬렉션 속성은 변경 내용을 자동으로 하위 속성에 보고하지 않습니다.  컬렉션에 대한 바인딩을 만들 때 이로 인해 보고서 변경 내용을 바인딩하지 못하게 되어 일부 데이터 바인딩 시나리오가 무효화될 수 있습니다.  하지만 컬렉션 형식 <xref:System.Windows.FreezableCollection%601>을 컬렉션 형식으로 사용하는 경우 컬렉션의 포함된 요소에 대한 하위 속성 변경 내용이 적절하게 보고되고 바인딩이 예상대로 작동합니다.  
  
 종속성 개체 컬렉션에서 하위 속성 바인딩을 사용할 수 있게 하려면 컬렉션 속성을 <xref:System.Windows.FreezableCollection%601> 형식으로 만들고 해당 컬렉션의 형식 제약 조건을 모든 <xref:System.Windows.DependencyObject> 파생 클래스로 지정합니다.  
  
## 참고 항목  
 <xref:System.Windows.FreezableCollection%601>   
 [WPF에 대한 XAML 및 사용자 지정 클래스](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)