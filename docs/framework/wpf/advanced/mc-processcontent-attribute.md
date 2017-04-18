---
title: "mc:ProcessContent 특성 | Microsoft Docs"
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
  - "mc:ProcessContent 특성"
  - "XAML, mc:ProcessContent 특성"
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# mc:ProcessContent 특성
[mc:Ignorable 특성](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)을 지정한 이유로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 바로 위 부모 요소가 무시되는 경우에도, 관련 부모 요소로 처리되는 콘텐츠를 계속 가지고 있어야 하는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 요소를 지정합니다.  `mc:ProcessContent` 특성은 사용자 지정 네임스페이스 매핑과 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 버전 관리 모두에 대해 태그 호환성을 지원합니다.  
  
## XAML 특성 사용  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|*ignorablePrefix*|모든 유효한 접두사 문자열\(XML 1.0 사양 기준\)|  
|*ignorableUri*|네임스페이스를 지정하는 모든 유효한 URI\(XML 1.0 사양 기준\)|  
|*ThisElementCanBeIgnored*|내부 형식을 확인할 수 없는 경우 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 프로세서 구현에서 무시할 수 있는 요소|  
|*\[content\]*|*ThisElementCanBeIgnored*를 무시할 수 있는 항목으로 표시됩니다.  프로세서에서 이 요소를 무시하면 *\[content\]*는 개체에 의해 처리됩니다.|  
  
## 설명  
 기본적으로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서는 무시된 요소에 포함되어 있는 콘텐츠를 무시합니다.  이런 경우 `mc:ProcessContent`를 사용하여 특정 요소를 지정하면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서가 무시된 요소에 포함된 콘텐츠를 계속 처리하게 됩니다.  이는 콘텐츠가 여러 개의 태그 안에 중첩되어 있고 그 중 무시할 수 있는 태그와 무시할 수 없는 태그가 적어도 하나씩 있을 때 유용합니다.  
  
 특성에 접두사를 여러 개 지정할 때에는 `mc:ProcessContent="ignore:Element1 ignore:Element2"`와 같은 공백 구분 기호를 사용합니다.  
  
 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] 네임스페이스는 [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]의 이 영역에 기술되어 있지 않은 기타 요소와 특성을 정의합니다.  자세한 내용은 [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824)을 참조하십시오.  
  
## 참고 항목  
 [mc:Ignorable 특성](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)   
 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)