---
title: "x:Class Directive | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "x:Class"
  - "xClass"
  - "Class"
helpviewer_keywords: 
  - "Class attribute in XAML [XAML Services]"
  - "XAML [XAML Services], x:Class attribute"
  - "x:Class attribute [XAML Services]"
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
caps.latest.revision: 27
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 26
---
# x:Class Directive
XAML 태그 컴파일을 구성하여 태그와 코드 숨김 사이에 partial 클래스를 조인합니다.  코드 partial 클래스는 별도의 코드 파일에 [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)] 언어로 정의되고 태그 partial 클래스는 일반적으로 XAML 컴파일 시 코드 생성을 통해 만들어집니다.  
  
## XAML 특성 사용  
  
```  
<object x:Class="namespace.classname"...>  
  ...  
</object>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`namespace`|선택적 요소.  `classname`으로 식별된 partial 클래스가 포함된 [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] 네임스페이스를 지정합니다.  `namespace`를 지정하는 경우 점\(.\)으로 `namespace`와 `classname`을 분리합니다.  설명 부분을 참조하십시오.|  
|`classname`|필수 요소.  로드된 XAML 및 해당 XAML의 코드 숨김을 연결하는 partial 클래스의 [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] 이름을 지정합니다.|  
  
## 종속성  
 `x:Class`는 XAML 프로덕션의 루트 요소에만 지정할 수 있습니다.  `x:Class`는 XAML 프로덕션에서 부모에 있는 모든 개체에 대해 올바르지 않습니다.  자세한 내용은 [\[MS\-XAML\] Section 4.3.1.6](http://go.microsoft.com/fwlink/?LinkId=114525)을 참조하십시오.  
  
## 설명  
 `namespace` 값에는 관련 네임스페이스를 이름 계층 구조로 구성하는 추가 점이 포함될 수 있습니다. 이 계층 구조는 .NET Framework 프로그래밍에서 일반적으로 사용되는 기법입니다.  `x:Class` 값의 문자열에서 마지막 점만 별도의 `namespace` 및 `classname.` 으로 해석됩니다. `x:Class`로 사용되는 클래스는 중첩 클래스가 될 수 없습니다.  중첩 클래스가 허용되면 `x:Class` 문자열에서 점의 의미가 모호해지므로 중첩 클래스는 사용할 수 없습니다.  
  
 `x:Class`를 사용하는 기존의 프로그래밍 모델에서 `x:Class`는 코드 숨김이 없는 XAML 페이지를 사용할 수 있다는 점에서 선택적 요소입니다.  그러나 해당 기능은 XAML을 사용하는 프레임워크에 의해 구현된 빌드 작업과 상호 작용합니다.  `x:Class` 기능은 XAML 지정된 콘텐츠의 여러 분류에 응용 프로그램 모델과 해당 빌드 작업에 있는 역할의 영향도 받습니다.  XAML에서 이벤트 처리 특성 값을 선언하거나, 정의하는 클래스가 코드 숨김 클래스에 있는 사용자 지정 요소를 인스턴스화하는 경우에는 코드 숨김의 적절한 클래스에 `x:Class` 지시문 참조 또는 [x:Subclass](../../../docs/framework/xaml-services/x-subclass-directive.md)를 제공해야 합니다.  
  
 `x:Class` 지시문의 값은 클래스의 정규화된 이름을 지정하지만 어셈블리 정보가 없는 문자열\(<xref:System.Type.FullName%2A?displayProperty=fullName>에 해당\)이어야 합니다.  간단한 응용 프로그램에서는 CLR 네임스페이스 정보를 생략할 수도 있는데 이는 코드 숨김에서도 구조가 동일한 경우, 즉 클래스 수준에서 코드 정의가 시작되는 경우에만 가능합니다.  
  
 페이지 또는 응용 프로그램 정의에 대한 코드 숨김 파일은 컴파일된 응용 프로그램을 생성하는 프로젝트의 일부로 포함되고 태그 컴파일을 포함하는 코드 파일에 들어 있어야 합니다.  CLR 클래스에 대한 이름 규칙을 따라야 합니다.  자세한 내용은 [프레임 워크 디자인 지침](../../../ml/index.xml)를 참조하십시오.  기본적으로 코드 숨김 클래스는 `public`이어야 하지만 [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md)을 사용하여 다른 액세스 수준으로 정의할 수도 있습니다.  
  
 `x:Class` 특성의 정확한 해석은 특히 .NET Framework XAML 서비스에서 CLR 기반 XAML 구현에만 적용됩니다.  CLR에 기반하지 않고 .NET Framework XAML 서비스 클래스를 사용하지 않는 기타 XAML 구현은 다른 확인 방법을 사용하여 XAML 태그를 연결하고 런타임 코드를 지원합니다.  `x:Class`의 일반적인 해석에 대한 자세한 내용은 [\[MS\-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525)을 참조하십시오.  
  
 특정 아키텍처 수준에서는 `x:Class`의 의미가 .NET Framework XAML 서비스에 정의되지 않습니다.  그 이유는 .NET Framework XAML 서비스가 XAML 태그와 백업 코드가 연결되어 있는 프로그래밍 모델을 지정하지 않기 때문입니다.  `x:Class` 지시문과 관련된 추가 사용은 XAML 태그와 CLR 기반 코드 숨김을 연결하는 방법을 정의하기 위해 프로그래밍 모델 또는 응용 프로그램 모델을 사용하는 특정 프레임워크에서 구현될 수 있습니다.  각 프레임워크는 각 동작이나 빌드 환경에서 포함되어야 하는 특정 구성 요소 중 일부를 사용하는 자체 빌드 작업이 있을 수 있습니다.  프레임워크 내에서 빌드 작업은 코드 숨김에 사용된 특정 CLR 언어에 따라 다를 수도 있습니다.  
  
## WPF 프로그래밍 모델의 x:Class  
 WPF 응용 프로그램과 WPF 응용 프로그램 모델에서 `x:Class`는 XAML 파일의 루트이고 컴파일 중인 요소의 특성으로 선언하거나\(이 경우 XAML은 `Page` 빌드 작업이 있는 WPF 응용 프로그램 프로젝트에 포함됨\), 컴파일된 WPF 응용 프로그램의 응용 프로그램 정의에서 <xref:System.Windows.Application> 루트의 특성으로 선언할 수 있습니다.  페이지 루트 또는 응용 프로그램 루트 이외의 다른 요소에 `x:Class`을 선언하거나 컴파일되지 않은 XAML 파일에 선언하면 [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] 및 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] WPF XAML 컴파일러에서 컴파일 타임 오류가 발생합니다.  WPF에서의 `x:Class` 처리의 다른 측면에 대한 자세한 내용은 [WPF의 코드 숨김 및 XAML](../../../ocs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)를 참조하십시오.  
  
## Windows Workflow Foundation의 x:Class  
 Windows Workflow Foundation의 경우 `x:Class`는 전적으로 XAML에서 구성된 사용자 정의 활동의 클래스 이름을 지정하거나 코드 숨김을 사용하여 활동 디자이너에 대한 XAML 페이지의 partial 클래스 이름을 지정합니다.  
  
## Silverlight 사용 정보  
 Silverlight용 `x:Class`는 별도로 문서화되어 있습니다.  자세한 내용은 [XAML Namespace \(x:\) Language Features \(Silverlight\)](http://go.microsoft.com/fwlink/?LinkId=199081)를 참조하십시오.  
  
## 참고 항목  
 [x:Subclass Directive](../../../docs/framework/xaml-services/x-subclass-directive.md)   
 [WPF에 대한 XAML 및 사용자 지정 클래스](../../../ocs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)   
 [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md)   
 [Types Migrated from WPF to System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)