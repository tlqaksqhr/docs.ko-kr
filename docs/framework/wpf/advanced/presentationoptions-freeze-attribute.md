---
title: PresentationOptions:Freeze 특성
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: 896f7b24599b68f178d2a006e5ddc07278564bde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546073"
---
# <a name="presentationoptionsfreeze-attribute"></a>PresentationOptions:Freeze 특성
설정의 <xref:System.Windows.Freezable.IsFrozen%2A> 상태 `true` 포함 하는에 <xref:System.Windows.Freezable> 요소입니다. 기본 동작에 대 한는 <xref:System.Windows.Freezable> 없이 `PresentationOptions:Freeze` 지정 된 특성은 <xref:System.Windows.Freezable.IsFrozen%2A> 은 `false` 로드 시간 및 일반에 의존 하는 <xref:System.Windows.Freezable> 런타임에 동작 합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`PresentationOptions`|XML 네임 스페이스 접두사를 XML 1.0 사양에 따라 모든 올바른 접두사 문자열을 지정할 수 있습니다. 접두사 `PresentationOptions` 이 설명서에서 확인 목적으로 사용 됩니다.|  
|`freezableElement`|요소 하나를 인스턴스화하는 파생 클래스의 <xref:System.Windows.Freezable>합니다.|  
  
## <a name="remarks"></a>설명  
 `Freeze` 특성은 유일한 특성 또는 기타 프로그래밍 요소에 정의 된 `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML 네임 스페이스입니다. `Freeze` 특성이 무시 하도록를 사용 하 여 지정 될 수 있도록이 특수 네임 스페이스에 존재 [mc: Ignorable 특성](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) 루트 요소 선언의 일부로 합니다. 이유는 `Freeze` 무시할 수 있어야 것이 아니기 때문 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 고정할 수 있는 프로세서 구현은 <xref:System.Windows.Freezable> 로드 시이 기능은 하지 않습니다의 일부가 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 사양입니다.  
  
 처리 하는 기능에서 `Freeze` 특성은 특히에 내장 되어는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 처리 하는 프로세서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 컴파일된 응용 프로그램에 대 한 합니다. 모든 클래스는 특성이 지원 되지 않습니다 되며 특성 구문은 없습니다 확장 가능 하거나 수정할 수 없습니다. 구현 하는 경우 사용자 고유의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서의 고정 동작은 선택할 수 있습니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 처리 하는 경우 프로세서는 `Freeze` 특성을 <xref:System.Windows.Freezable> 로드 시 요소입니다.  
  
 에 대 한 모든 값은 `Freeze` 이외의 특성 `true` (하지 대/소문자 구분) 로드 시간 오류를 생성 합니다. (지정 하는 `Freeze` 특성은 `false` 는 오류는 있지만 그 이름은 이미 기본, 따라서 설정을 `false` 는 아무 작업도 수행).  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Freezable>  
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [mc:Ignorable 특성](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)
