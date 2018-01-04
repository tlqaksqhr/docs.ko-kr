---
title: "mc:Ignorable 특성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9767b721321b34030a2f276a90c618c658645207
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="mcignorable-attribute"></a>mc:Ignorable 특성
지정 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 마크업 파일에서 발생 하는 네임 스페이스 접두사가 무시 되는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서. `mc:Ignorable` 특성에 대 한 및 사용자 지정 네임 스페이스 매핑에 대 한 태그 호환성 지원 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 버전 관리 합니다.  
  
## <a name="xaml-attribute-usage-single-prefix"></a>XAML 특성 사용 (단일 접두사)  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a>XAML 특성 사용 (두 개의 접두사)  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|*ignorablePrefix ignorablePrefix1, 등입니다.*|XML 1.0 사양에 따라 모든 유효한 접두사 문자열입니다.|  
|*ignorableUri*|모든 유효한 URI XML 1.0 사양에 따라 네임 스페이스를 지정 합니다.|  
|*ThisElementCanBeIgnored*|무시할 수 있는 요소 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 내부 형식을 확인할 수 없는 경우 프로세서 구현 합니다.|  
  
## <a name="remarks"></a>설명  
 `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임 스페이스 접두사는 매핑할 때 권장 되는 접두사 규칙의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 호환성 네임 스페이스 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]합니다.  
  
 요소 또는 특성으로 요소 이름의 접두사 부분은 표시 되는 위치 `mc:Ignorable` 에서 처리 될 때 오류가 발생 하지 것입니다는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서. 해당 특성을 내부 형식 또는 프로그래밍 구문에 확인할 수 없는, 해당 요소가 무시 됩니다. 그러나 note 무시 요소는 처리 되지 않고 해당 요소의 부작용이 추가적인 요소 요구 사항에 대 한 추가 구문 분석 오류를 생성할 여전히 수 있습니다. 예를 들어, 특정 요소 콘텐츠 모델 지정한 자식 요소가 닫힌 경우 하지만 자식 요소가 하나만 필요할는 `mc:Ignorable` 접두사 및 지정된 된 자식 요소 확인할 수 없는 형식에는 다음 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 수 오류가 발생 합니다.  
  
 `mc:Ignorable`네임 스페이스 매핑을 식별자 문자열에만 적용 됩니다. `mc:Ignorable`지정 하는 어셈블리에 네임 스페이스 매핑을에 적용 되지 않습니다는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 네임 스페이스 및 어셈블리 (또는 기본적으로 어셈블리는 현재 실행 파일).  
  
 구현 하는 경우는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서, 프로세서 구현 해야 발생 시 키 지 처리 모든 요소 또는 특성으로 식별 되는 접두사에 의해 한정 됩니다에 대 한 형식 변환 오류 또는 구문 `mc:Ignorable`합니다. 하지만 프로세서 구현 로드 또는 위의 한 자식 요소가 예제와 같은 처리에 실패 하는 요소 중 보조 결과 예외를 발생 시킬 수 있습니다.  
  
 기본적으로는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서는 무시 요소 내에서 콘텐츠를 무시 합니다. 그러나는 추가 특성을 지정할 수 [mc:ProcessContent 특성](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), 다음 사용 가능한 부모 요소에 의해 무시 된 요소 내에서 콘텐츠의 계속된 처리를 필요로 하도록 합니다.  
  
 예를 들어 구분 기호로 사용 하나 이상의 공백 문자를 사용 하는 특성에 여러 개의 접두사를 지정할 수 있습니다: `mc:Ignorable="ignore1 ignore2"`합니다.  
  
 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] 다른 요소와 특성의이 영역에 문서화 되지 않은 네임 스페이스를 정의 고 [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]합니다. 자세한 내용은 참조 [XML 태그 호환성 사양](http://go.microsoft.com/fwlink/?LinkId=73824)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Markup.XamlReader>  
 [PresentationOptions:Freeze 특성](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)  
 [XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
