---
title: "x:Shared Attribute | Microsoft Docs"
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
  - "XAML [XAML Services], x:Shared attribute"
  - "x:Shared attribute [XAML Services]"
  - "Shared attribute in XAML [XAML Services]"
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
caps.latest.revision: 16
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 16
---
# x:Shared Attribute
`false`로 설정된 경우 WPF 리소스 검색 동작을 수정하여 특성화된 리소스를 요청하는 경우 모든 리소스 요청에 대해 동일한 인스턴스를 공유하는 대신 각 요청에 대해 새 인스턴스를 만듭니다.  
  
## XAML 특성 사용  
  
```  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## 설명  
 `x:Shared`는 XAML 언어 XAML 네임스페이스로 매핑되고 .NET Framework XAML 서비스 및 XAML 판독기에 의해 유효한 XAML 언어 요소로 인식됩니다.  그러나 `x:Shared`의 설명한 기능이 WPF 응용 프로그램 및 WPF XAML 파서에만 관련이 있습니다.  WPF에서 `x:Shared`는 WPF <xref:System.Windows.ResourceDictionary> 내에 존재하는 개체에 적용될 때만 특성으로 유용합니다.  다른 사용은 구문 분석 예외나 기타 오류를 throw하지 않지만 효과는 없습니다.  
  
 `x:Shared` 의 의미는 XAML 언어 사양에 지정되어 있지 않습니다.  .NET Framework XAML 서비스에 빌드하는 것처럼 다른 XAML 구현은 반드시 리소스 공유 지원을 제공하지는 않습니다.  이러한 XAML 구현은 `x:Shared` 값을 사용하는 지원 프레임워크에서 유사한 동작을 제공할 수 있습니다.  
  
 WPF에서 리소스에 대한 기본 `x:Shared` 조건은 `true`입니다.  이는 모든 리소스 요청이 동일한 인스턴스를 반환함을 의미합니다.  
  
 <xref:System.Windows.FrameworkElement.FindResource%2A>와 같은 리소스 API를 통해 반환되는 개체를 수정하거나, <xref:System.Windows.ResourceDictionary> 내에서 개체를 직접 수정하면 원본 리소스가 변경됩니다.  해당 리소스에 대한 참조가 동적 리소스 참조인 경우 리소스 사용자는 변경된 리소스를 받습니다.  
  
 리소스에 대한 참조가 정적 리소스 참조인 경우 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 처리 시간 이후의 리소스 변경 내용은 적용되지 않습니다.  고정 및 동적 리소스 참조에 대한 자세한 내용은 [XAML 리소스](../../../ocs/framework/wpf/advanced/xaml-resources.md)를 참조하십시오.  
  
 `x:Shared="true"`를 명시적으로 지정하는 경우는 기본값이 이미 지정되었으므로 거의 없습니다.  WPF 개체 모델에서 `x:Shared`와 동일한 직접 코드가 없습니다. XAML 사용에서만 지정할 수 있으며 .NET Framework XAML 서비스 및 XAML 판독기를 사용하여 처리되는 경우 기본 WPF 동작 또는 로드 경로에 있는 임시 XAML 노드 스트림에서 처리되어야 합니다.  
  
 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>에서 파생된 클래스를 리소스로 정의하고 요소 리소스를 콘텐츠 모델에 추가하는 경우에는 `x:Shared="false"`로 지정해야 합니다.  `x:Shared="false"` 설정을 사용하면 같은 컬렉션\(예: <xref:System.Windows.Controls.UIElementCollection>\)에서 요소 리소스를 여러 번 사용할 수 있습니다.  컬렉션 내의 모든 콘텐츠는 고유해야 하기 때문에 `x:Shared="false"` 없이는 유효하지 않습니다.  그러나 `x:Shared="false"` 동작은 동일한 인스턴스를 반환하는 대신 리소스의 동일한 또 다른 인스턴스를 만듭니다.  
  
 <xref:System.Windows.Freezable> 리소스를 애니메이션 값으로 사용하면서 애니메이션별로 리소스를 수정하려는 경우에도 `x:Shared="false"` 설정을 사용합니다.  
  
 `false` 문자열은 대\/소문자를 구분하지 않습니다.  
  
 WPF에서 `x:Shared`는 다음과 같은 경우에만 사용할 수 있습니다.  
  
-   `x:Shared`가 설정된 항목이 포함된 <xref:System.Windows.ResourceDictionary>를 컴파일해야 하는 경우.  <xref:System.Windows.ResourceDictionary>는 느슨한 XAML에 포함되거나 테마에 사용될 수 없습니다.  
  
-   항목이 포함된 <xref:System.Windows.ResourceDictionary>가 다른 <xref:System.Windows.ResourceDictionary>에 중첩될 수 없는 경우.  예를 들어 이미 <xref:System.Windows.ResourceDictionary> 항목인 <xref:System.Windows.Style>에 포함된 <xref:System.Windows.ResourceDictionary> 항목에 대해서는 `x:Shared`를 사용할 수 없습니다.  
  
## 참고 항목  
 <xref:System.Windows.ResourceDictionary>   
 [XAML 리소스](../../../ocs/framework/wpf/advanced/xaml-resources.md)   
 [기본 요소](../../../ocs/framework/wpf/advanced/base-elements.md)