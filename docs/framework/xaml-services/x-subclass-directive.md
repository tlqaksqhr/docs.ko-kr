---
title: "x:Subclass Directive | Microsoft Docs"
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
  - "Subclass"
  - "xSubclass"
  - "x:Subclass"
helpviewer_keywords: 
  - "x:Subclass attribute [XAML Services]"
  - "XAML [XAML Services], x:Subclass attribute"
  - "Subclass attribute in XAML [XAML Services]"
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
caps.latest.revision: 20
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 20
---
# x:Subclass Directive
`x:Class`도 제공되는 경우 XAML 태그 컴파일 동작을 수정합니다.  `x:Class`를 기반으로 partial 클래스를 만드는 대신, 제공된 `x:Class`가 중간 클래스로 만들어지고 제공된 파생 클래스는 `x:Class`를 기반으로 하는 것으로 간주됩니다.  
  
## XAML 특성 사용  
  
```  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`namespace`|선택적 요소.  `classname`이 포함된 CLR 네임스페이스를 지정합니다.  `namespace`를 지정하는 경우 점\(.\)으로 `namespace`와 `classname`을 분리합니다.|  
|`classname`|필수 요소.  로드된 XAML 및 해당 XAML의 코드 숨김을 연결하는 partial 클래스의 CLR 이름을 지정합니다.  설명 부분을 참조하십시오.|  
|`subclassNamespace`|선택적 요소.  각 네임스페이스가 서로 해결할 수 있는 경우 `namespace`과 다를 수 있습니다.  `subclassName`이 포함된 CLR 네임스페이스를 지정합니다.  `subclassName`를 지정하는 경우 점\(.\)으로 `subclassNamespace`와 `subclassName`을 분리합니다.|  
|`subclassName`|필수 요소.  서브클래스의 CLR 이름을 지정합니다.|  
  
## 종속성  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)도 동일한 개체에서 제공되어야 하며 해당 개체는 XAML 프로덕션페이지의 루트 요소여야 합니다.  
  
## 설명  
 `x:Subclass`는 기본적으로 partial 클래스 선언을 지원하지 않는 언어를 위해 사용됩니다.  
  
 `x:Subclass`로 사용되는 클래스는 중첩된 클래스가 될 수 없으며 `x:Subclass`은 "종속성" 섹션에서 설명하는 것처럼 루트 개체를 참조해야 합니다.  
  
 그렇지 않으면 `x:Subclass`의 개념적 의미는 .NET Framework XAML 서비스 구현에서 정의하지 않습니다.  그 이유는 .NET Framework XAML 서비스 동작이 XAML 태그와 백업 코드가 연결되어 있는 전체 프로그래밍 모델을 지정하지 않기 때문입니다.  `x:Class` 및 `x:Subclass`와 관련된 추가 개념은 XAML 태그, 컴파일된 태그 및 CLR 기반 코드 숨김을 연결하는 방법을 정의하기 위해 프로그래밍 모델 또는 응용 프로그램 모델을 사용하는 특정 프레임워크에서 구현합니다.  각 프레임워크는 각 동작이나 빌드 환경에서 포함되어야 하는 특정 구성 요소 중 일부를 사용하는 자체 빌드 작업이 있을 수 있습니다.  프레임워크 내에서 빌드 작업은 코드 숨김에 사용된 특정 CLR 언어에 따라 다를 수도 있습니다.  
  
## WPF 사용 정보  
 `x:Subclass`는 이미  `x:Class`를 가진 응용 프로그램 정의에서 페이지 루트 또는 <xref:System.Windows.Application> 루트에 있을 수 있습니다.  `x:Subclass` 를 페이지 또는 응용 프로그램 루트 이외의 요소에 대해 선언하거나 `x:Class`가 없는 위치에서 지정하면 컴파일 타임 오류가 발생합니다.  
  
 `x:Subclass` 시나리오에서 올바르게 동작하는 파생 클래스를 만드는 것은 꽤 복잡합니다.  중간 파일\(태그 컴파일에 의해 프로젝트의 obj 폴더에 생성되며 .xaml 파일 이름이 통합된 이름의 .g 파일\)을 검사해야 할 수 있습니다.  이러한 중간 파일은 컴파일된 응용 프로그램에서 결합된 partial 클래스의 프로그래밍 구문에 대한 출처를 확인하는 데 도움이 될 수 있습니다.  
  
 컴파일 도중 중간 클래스에서 만들어질 때 처리기의 스텁을 재정의하려면 파생 클래스의 이벤트 처리기는 `internal override`\([!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)]의 `Friend Overrides`\)여야 합니다.  그렇지 않으면 파생 클래스 구현은 중간 클래스 구현을 숨기고 중간 클래스 처리기가 호출되지 않습니다.  
  
 `x:Class`와 `x:Subclass`를 모두 정의하는 경우 `x:Class`에서 참조하는 클래스에 대한 구현을 제공할 필요가 없습니다.  중간 파일에 만드는 클래스에 대한 지침이 컴파일러에 있으므로 이에 따라 `x:Class` 특성을 통해 이름만 지정하기만 하면 됩니다\(이 경우 컴파일러는 기본 이름을 선택하지 않음\).  `x:Class` 클래스를 구현할 수 있으나, 이 경우는 `x:Class`와 `x:Subclass`를 모두 사용하기 위한 일반적인 시나리오가 아닙니다.  
  
## 참고 항목  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [WPF에 대한 XAML 및 사용자 지정 클래스](../../../ocs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)