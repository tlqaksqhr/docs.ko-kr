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
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="3e65e-102">PresentationOptions:Freeze 특성</span><span class="sxs-lookup"><span data-stu-id="3e65e-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="3e65e-103">설정의 <xref:System.Windows.Freezable.IsFrozen%2A> 상태 `true` 포함 하는에 <xref:System.Windows.Freezable> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3e65e-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="3e65e-104">기본 동작에 대 한는 <xref:System.Windows.Freezable> 없이 `PresentationOptions:Freeze` 지정 된 특성은 <xref:System.Windows.Freezable.IsFrozen%2A> 은 `false` 로드 시간 및 일반에 의존 하는 <xref:System.Windows.Freezable> 런타임에 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e65e-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="3e65e-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="3e65e-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="3e65e-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="3e65e-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="3e65e-107">XML 네임 스페이스 접두사를 XML 1.0 사양에 따라 모든 올바른 접두사 문자열을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e65e-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="3e65e-108">접두사 `PresentationOptions` 이 설명서에서 확인 목적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e65e-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="3e65e-109">요소 하나를 인스턴스화하는 파생 클래스의 <xref:System.Windows.Freezable>합니다.</span><span class="sxs-lookup"><span data-stu-id="3e65e-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e65e-110">설명</span><span class="sxs-lookup"><span data-stu-id="3e65e-110">Remarks</span></span>  
 <span data-ttu-id="3e65e-111">`Freeze` 특성은 유일한 특성 또는 기타 프로그래밍 요소에 정의 된 `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3e65e-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="3e65e-112">`Freeze` 특성이 무시 하도록를 사용 하 여 지정 될 수 있도록이 특수 네임 스페이스에 존재 [mc: Ignorable 특성](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) 루트 요소 선언의 일부로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e65e-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="3e65e-113">이유는 `Freeze` 무시할 수 있어야 것이 아니기 때문 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 고정할 수 있는 프로세서 구현은 <xref:System.Windows.Freezable> 로드 시이 기능은 하지 않습니다의 일부가 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="3e65e-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="3e65e-114">처리 하는 기능에서 `Freeze` 특성은 특히에 내장 되어는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 처리 하는 프로세서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 컴파일된 응용 프로그램에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e65e-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="3e65e-115">모든 클래스는 특성이 지원 되지 않습니다 되며 특성 구문은 없습니다 확장 가능 하거나 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e65e-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="3e65e-116">구현 하는 경우 사용자 고유의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서의 고정 동작은 선택할 수 있습니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 처리 하는 경우 프로세서는 `Freeze` 특성을 <xref:System.Windows.Freezable> 로드 시 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3e65e-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="3e65e-117">에 대 한 모든 값은 `Freeze` 이외의 특성 `true` (하지 대/소문자 구분) 로드 시간 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e65e-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="3e65e-118">(지정 하는 `Freeze` 특성은 `false` 는 오류는 있지만 그 이름은 이미 기본, 따라서 설정을 `false` 는 아무 작업도 수행).</span><span class="sxs-lookup"><span data-stu-id="3e65e-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e65e-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e65e-119">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 [<span data-ttu-id="3e65e-120">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="3e65e-120">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="3e65e-121">mc:Ignorable 특성</span><span class="sxs-lookup"><span data-stu-id="3e65e-121">mc:Ignorable Attribute</span></span>](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)
