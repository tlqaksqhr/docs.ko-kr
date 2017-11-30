---
title: "mc:ProcessContent 특성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aaf83fe66d5367d5e51428cb8f35aa88c12c9c39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="mcprocesscontent-attribute"></a>mc:ProcessContent 특성
지정 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 요소 관련 부모 요소에 의해 처리 되는 콘텐츠 같아야 직계 부모 요소가 무시 되는 경우에 한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 지정한 이유로 프로세서 [mc: Ignorable 특성](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) . `mc:ProcessContent` 특성에 대 한 및 사용자 지정 네임 스페이스 매핑에 대 한 태그 호환성 지원 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 버전 관리 합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
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
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|*ignorablePrefix*|XML 1.0 사양에 따라 모든 유효한 접두사 문자열입니다.|  
|*ignorableUri*|모든 유효한 URI XML 1.0 사양에 따라 네임 스페이스를 지정 합니다.|  
|*ThisElementCanBeIgnored*|무시할 수 있는 요소 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 내부 형식을 확인할 수 없는 경우 프로세서 구현 합니다.|  
|*[콘텐츠]*|*ThisElementCanBeIgnored* 무시할 수 있는 것으로 표시 됩니다. 프로세서에서이 요소를 무시 하는 경우 *[콘텐츠]* 에서 처리 *개체*합니다.|  
  
## <a name="remarks"></a>설명  
 기본적으로는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서는 무시 요소 내에서 콘텐츠를 무시 합니다. 특정 요소를 지정할 수 있습니다 `mc:ProcessContent`, 및 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 계속 무시 요소 내에서 콘텐츠 처리 됩니다. 이 콘텐츠는 하나 이상와 무시할 수 있는 중 하나를 무시할 수 있는 여러 태그 안에 중첩 되어 있습니다.  
  
 예를 들어 공백 구분 기호를 사용 하 여 특성에 여러 개의 접두사를 지정할 수 있습니다: `mc:ProcessContent="ignore:Element1 ignore:Element2"`합니다.  
  
 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] 다른 요소와 특성의이 영역에 문서화 되지 않은 네임 스페이스를 정의 고 [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]합니다. 자세한 내용은 참조 [XML 태그 호환성 사양](http://go.microsoft.com/fwlink/?LinkId=73824)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [mc:Ignorable 특성](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)  
 [XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
