---
title: "PresentationOptions:Freeze 특성 | Microsoft Docs"
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
  - "Freezable 요소"
  - "Freeze 특성"
  - "PresentationOptions 접두사"
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# PresentationOptions:Freeze 특성
포함하는 <xref:System.Windows.Freezable> 요소에서 <xref:System.Windows.Freezable.IsFrozen%2A> 상태를 `true`로 설정합니다.  `PresentationOptions:Freeze` 특성이 지정되지 않은 <xref:System.Windows.Freezable>의 기본 동작은 로드 시에는 <xref:System.Windows.Freezable.IsFrozen%2A>이 `false`이고 런타임에는 일반적인 <xref:System.Windows.Freezable> 동작을 따르는 것입니다.  
  
## XAML 특성 사용  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`PresentationOptions`|XML 1.0 사양을 따르는 모든 유효한 접두사가 될 수 있는 XML 네임스페이스 접두사입니다.  이 설명서에서는 식별을 위해 `PresentationOptions` 접두사가 사용됩니다.|  
|`freezableElement`|<xref:System.Windows.Freezable>의 파생 클래스를 인스턴스화하는 요소입니다.|  
  
## 설명  
 `Freeze` 특성은 `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML 네임스페이스에 정의된 유일한 특성 또는 기타 프로그래밍 요소입니다.  `Freeze` 특성은 루트 요소 선언의 일부로 [mc:Ignorable 특성](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)을 사용하여 무시하도록 지정할 수 있기 때문에 이 특수한 네임스페이스에만 존재합니다.  `Freeze`를 무시할 수 있어야 하는 이유는 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 구현에서 로드 시에 <xref:System.Windows.Freezable>을 고정할 수 있는 것이 아니기 때문입니다. 이 기능은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 사양에 속하지 않습니다.  
  
 `Freeze` 특성을 처리하는 기능은 컴파일된 응용 프로그램을 위한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 처리하는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에만 포함됩니다.  이 특성은 어떤 클래스도 지원하지 않으며 특성 구문을 확장하거나 수정할 수 없습니다.  고유한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서를 구현하는 경우 로드 시 <xref:System.Windows.Freezable> 요소에서 `Freeze` 특성을 처리할 때 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서의 동작을 고정하는 작업이 동시에 수행되도록 선택할 수 있습니다.  
  
 `true` 이외의 다른 모든 `Freeze` 특성 값\(대소문자 구분 안 함\)은 로드 시 오류가 발생합니다.  `Freeze` 특성을 `false`로 지정하는 것은 오류가 아니지만 이 값은 이미 기본값이므로 `false`로 설정해도 아무 동작도 수행되지 않습니다.  
  
## 참고 항목  
 <xref:System.Windows.Freezable>   
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [mc:Ignorable 특성](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)