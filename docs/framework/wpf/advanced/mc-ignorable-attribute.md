---
title: "mc:Ignorable 특성 | Microsoft Docs"
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
  - "mc XML 네임스페이스 접두사"
  - "mc:Ignorable 특성"
  - "mc:ProcessContent 특성"
  - "XAML, mc:Ignorable 특성"
  - "XAML, mc:ProcessContent 특성"
  - "XML, mc 네임스페이스 접두사"
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# mc:Ignorable 특성
태그 파일에서 발견되는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임스페이스 접두사 중 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 무시할 수 있는 접두사를 지정합니다.  `mc:Ignorable` 특성은 사용자 지정 네임스페이스 매핑과 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 버전 관리 모두에 대해 태그 호환성을 지원합니다.  
  
## XAML 특성 사용\(단일 접두사\)  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## XAML 특성 사용\(두 개의 접두사\)  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|*ignorablePrefix, ignorablePrefix1 등*|모든 유효한 접두사 문자열\(XML 1.0 사양 기준\)|  
|*ignorableUri*|네임스페이스를 지정하는 모든 유효한 URI\(XML 1.0 사양 기준\)|  
|*ThisElementCanBeIgnored*|내부 형식을 확인할 수 없는 경우 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 프로세서 구현에서 무시할 수 있는 요소|  
  
## 설명  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 호환성 네임스페이스 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]을 매핑할 때 권장되는 접두사 규칙은 `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임스페이스 접두사입니다.  
  
 요소 이름의 접두사 부분이 `mc:Ignorable`로 식별되는 요소 또는 특성은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 처리될 때 오류를 발생시키지 않습니다.  해당 특성을 내부 형식 또는 프로그래밍 구문으로 해석할 수 없을 경우 해당 요소가 무시됩니다.  하지만 이렇게 무시된 요소가 여전히 추가적인 요소 요구 사항에 대해 추가적인 구문 분석 오류를 생성할 수 있으며 이는 해당 요소가 처리되지 않기 때문에 발생하는 의도하지 않은 결과입니다.  예를 들어 특정 요소 콘텐츠 모델에 정확히 하나의 자식 요소가 필요하지만 지정된 자식 요소에 `mc:Ignorable` 접두사가 있고 지정된 자식 요소를 형식으로 확인하지 못한 경우에는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 오류가 발생할 수 있습니다.  
  
 `mc:Ignorable`은 식별자 문자열에 대한 네임스페이스 매핑에만 적용됩니다.  `mc:Ignorable`은 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 네임스페이스와 어셈블리를 지정하는\(또는 기본적으로 현재 실행 파일을 어셈블리로 사용하는\) 어셈블리에 대한 네임스페이스 매핑에 적용되지 않습니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서를 구현하는 경우 프로세서 구현에서는 `mc:Ignorable`로 식별되는 접두사로 정규화된 모든 요소 또는 특성에 대해 형식 변환 처리 오류 또는 구문 오류를 발생시키지 않아야 합니다.  하지만 프로세서 구현에서는 앞의 예제에 나온 자식이 하나인 요소처럼 로드 또는 처리에 실패한 요소로 인한 부차적인 결과인 예외를 발생시킬 수 있습니다.  
  
 기본적으로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서는 무시된 요소에 포함되어 있는 콘텐츠를 무시합니다.  하지만 추가 특성인 [mc:ProcessContent 특성](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md)을 지정하여 무시된 요소 내의 콘텐츠를 다음으로 사용 가능한 부모 요소에서 계속 처리하도록 요청할 수 있습니다.  
  
 `mc:Ignorable="ignore1 ignore2"`와 같이, 하나 이상의 공백 문자를 구분 기호로 사용하여 특성에 여러 개의 접두사를 지정할 수 있습니다.  
  
 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] 네임스페이스는 [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]의 이 영역에 기술되어 있지 않은 기타 요소와 특성을 정의합니다.  자세한 내용은 [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Markup.XamlReader>   
 [PresentationOptions:Freeze 특성](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)   
 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)