---
title: "샘플 OpenType 글꼴 팩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- OpenType font pack [WPF]
- fonts [WPF], OpenType font pack
- typography [WPF], OpenType font pack
ms.assetid: 56b46fa1-a44e-419b-8f14-25ad51c715c3
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bbc5caeab5a77518e160bacb9722e50ff7abbfb4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="sample-opentype-font-pack"></a>샘플 OpenType 글꼴 팩
이 항목에서는 [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)]를 통해 배포되는 샘플 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴을 간략하게 설명합니다. 샘플 글꼴은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램에서 사용될 수 있는 확장 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 기능을 지원합니다.  
  
  
<a name="overview"></a>   
## <a name="fonts-in-the-opentype-font-pack"></a>OpenType 글꼴 팩의 글꼴  
 [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)]는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램을 만드는 데 사용할 수 있는 샘플 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴 집합을 제공합니다. 샘플 글꼴은 Ascender Corporation으로부터 사용 허가를 받아 제공됩니다. 이러한 글꼴은 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 서식을 통해 정의된 총 기능의 하위 집합만 구현합니다. 다음 테이블에는 샘플 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴의 이름이 나와 있습니다.  
  
|**Name**|**파일**|  
|--------------|--------------|  
|Kootenay|Kooten.ttf|  
|Lindsey|Linds.ttf|  
|Miramonte|Miramo.ttf|  
|Miramonte Bold|Miramob.ttf|  
|Pericles|Peric.ttf|  
|Pericles Light|Pericl.ttf|  
|Pescadero|Pesca.ttf|  
|Pescadero Bold|Pescab.ttf|  
  
 다음 그림에서는 다음과 같은 샘플 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴을 보여 줍니다.  
  
 ![샘플 글꼴 팩의 글꼴 이름 목록](../../../../docs/framework/wpf/advanced/media/samplefontpack01.gif "samplefontpack01")  
OpenType 글꼴 팩의 글꼴  
  
 샘플 글꼴은 Ascender Corporation으로부터 사용 허가를 받아 제공됩니다. Ascender는 고급 글꼴 제품의 공급자입니다. 샘플 글꼴의 확장 또는 사용자 지정 버전을 사용 허가하려면 [Ascender Corporation의 웹 사이트](http://go.microsoft.com/fwlink/?LinkId=182627)를 참조하세요.  
  
> [!NOTE]
>  응용 프로그램 내에 포함하거나 재배포할 글꼴에 대한 필요한 라이선스 권한이 있는지 확인하는 것은 개발자의 책임입니다.  
  
<a name="installing_the_fonts"></a>   
## <a name="installing-the-fonts"></a>글꼴 설치  
 샘플 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴을 기본 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 글꼴 디렉터리 **\WINDOWS\Fonts**에 설치할 수 있습니다. [글꼴] 컨트롤 패널을 사용하여 글꼴을 설치합니다. 이러한 글꼴이 컴퓨터에 있으면 기본 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 글꼴을 참조하는 모든 응용 프로그램에 액세스할 수 있습니다. 글꼴 파일을 두 번 클릭하여 대표 문자 집합을 여러 글꼴 크기로 표시할 수 있습니다. 다음 스크린샷은 Lindsey 글꼴 파일인 Linds.ttf를 보여 줍니다.  
  
 ![Lindsey 글꼴 &#40; OpenType &#41; ] (../../../../docs/framework/wpf/advanced/media/typographyinwpf-04.png "TypographyInWPF_04")  
Lindsey 글꼴 표시  
  
<a name="using_the_fonts"></a>   
## <a name="using-the-fonts"></a>글꼴 사용  
 응용 프로그램에서 글꼴을 사용할 수 있는 두 가지 방법이 있습니다. 어셈블리 내에 리소스로 포함되지 않은 프로젝트 콘텐츠 항목으로 응용 프로그램에 글꼴을 추가할 수 있습니다. 또는 응용 프로그램의 어셈블리 파일에 포함된 프로젝트 리소스 항목으로 응용 프로그램에 글꼴을 추가할 수 있습니다. 자세한 내용은 [응용 프로그램과 함께 글꼴 패키징](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Documents.Typography>  
 [OpenType 글꼴 기능](../../../../docs/framework/wpf/advanced/opentype-font-features.md)  
 [응용 프로그램과 함께 글꼴 패키징](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md)
