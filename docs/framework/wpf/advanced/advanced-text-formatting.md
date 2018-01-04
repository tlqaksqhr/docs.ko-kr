---
title: "고급 텍스트 서식 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [WPF]
- text [WPF]
- typography [WPF], text formatting
ms.assetid: f0a7986e-f5b2-485c-a27d-f8e922022212
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9bb2664b267301fdf1e3a67e385595a5d28212bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="advanced-text-formatting"></a>고급 텍스트 서식 지정
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 강력한 집합을 제공 [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] 응용 프로그램에서 텍스트를 포함 하는 데 있습니다. 레이아웃 및 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]와 같은 <xref:System.Windows.Controls.TextBlock>, 가장 일반적인 제공 하 고 일반 텍스트 표현에 요소를 사용 합니다. 그리기 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]와 같은 <xref:System.Windows.Media.GlyphRunDrawing> 및 <xref:System.Windows.Media.FormattedText>, 드로잉에 서식 있는 텍스트를 포함 하는 방법을 제공 합니다. 고급 회원 가장 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 서식 엔진이 텍스트 표현 텍스트 저장소 관리, 실행 텍스트 서식 지정 관리, 포함 된 개체 관리 등의 모든 측면을 제어 하는 확장 가능한 텍스트를 제공 합니다.  
  
 이 항목에서는에 소개 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 텍스트 서식 지정 합니다. 용도 및 클라이언트 구현에 중점을 둡니다는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 텍스트 서식 엔진이 있습니다.  
  
> [!NOTE]
>  이 문서에서 모든 코드 예제에서 확인할 수 있습니다는 [고급 텍스트 서식 지정 샘플](http://go.microsoft.com/fwlink/?LinkID=159965)합니다.  
  

  
<a name="prereq"></a>   
## <a name="prerequisites"></a>필수 구성 요소  
 이 항목에서는 상위 수준으로 익숙한 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 텍스트 표시 하는 데 사용 합니다. 대부분의 사용자 시나리오에 고급 텍스트 서식 지정 필요 하지 것입니다 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 이 항목에서 설명 합니다. 다양 한 텍스트에 대 한 소개 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], 참조 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)합니다.  
  
<a name="section1"></a>   
## <a name="advanced-text-formatting"></a>고급 텍스트 서식 지정  
 텍스트 레이아웃 및 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 컨트롤에 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 쉽게 응용 프로그램에 서식 있는 텍스트를 포함할 수 있도록 하는 서식 속성을 제공 합니다. 이러한 컨트롤은 텍스트의 표현을 처리하는 다양한 속성을 표시하며 서체, 크기 및 색을 포함합니다. 일반적인 상황에서 이러한 컨트롤은 응용 프로그램에서 대부분의 텍스트 표현을 처리할 수 있습니다. 그러나 일부 고급 시나리오는 텍스트 표현 뿐만 아니라 텍스트 저장소 컨트롤이 필요합니다. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 이러한 목적으로 확장 가능한 텍스트 서식 지정 엔진을 제공합니다.  
  
 서식 지정 기능 고급 텍스트에서 찾을 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 텍스트 서식 엔진, 텍스트 저장소 구성 됩니다. 텍스트 서식 엔진이, <xref:System.Windows.Media.TextFormatting.TextFormatter>, 줄의 텍스트를 표시 하는 데 사용할를 만듭니다. 이 줄 포맷 프로세스를 시작 하 고 텍스트 포맷터를 호출 하 여 달성 <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>합니다. 텍스트 포맷터의 저장소를 호출 하 여 텍스트 저장소에서 텍스트 실행을 검색 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> 메서드. <xref:System.Windows.Media.TextFormatting.TextRun> 개체도 합한 다음 <xref:System.Windows.Media.TextFormatting.TextLine> 텍스트 포맷터가 개체를 검사 또는 표시에 대 한 응용 프로그램에 제공 합니다.  
  
<a name="section2"></a>   
## <a name="using-the-text-formatter"></a>텍스트 포맷터 사용  
 <xref:System.Windows.Media.TextFormatting.TextFormatter>이 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 텍스트 서식 엔진 및 서식 및 텍스트 줄 바꿈을에 서비스를 제공 합니다. 텍스트 포맷터는 다양한 텍스트 문자 서식과 단락 스타일을 처리할 수 있으며 국제 텍스트 레이아웃에 대한 지원을 포함합니다.  
  
 일반 텍스트와 달리 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)], <xref:System.Windows.Media.TextFormatting.TextFormatter> 콜백 메서드의 집합을 통해 텍스트 레이아웃 클라이언트와 상호 작용 합니다. 클라이언트의 구현에서 이러한 메서드를 제공할 필요는 <xref:System.Windows.Media.TextFormatting.TextSource> 클래스입니다. 다음 다이어그램에서는 클라이언트 응용 프로그램 간의 텍스트 레이아웃 상호 작용 및 <xref:System.Windows.Media.TextFormatting.TextFormatter>합니다.  
  
 ![텍스트 레이아웃 클라이언트 및 TextFormatter의 다이어그램](../../../../docs/framework/wpf/advanced/media/textformatter01.png "TextFormatter01")  
응용 프로그램과 TextFormatter 간의 상호 작용  
  
 텍스트 포맷터는 텍스트 저장소에서 서식 있는 텍스트 줄을 검색 하는 데 사용 되는의 구현인 <xref:System.Windows.Media.TextFormatting.TextSource>합니다. 사용 하 여 첫 번째 텍스트 포맷터의 인스턴스를 만들고 이렇게는 <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A> 메서드. 이 메서드는 텍스트 포맷터의 인스턴스를 생성하고 최대 선 높이 및 너비 값을 설정합니다. 호출 하 여 줄 생성 프로세스가 시작 되는 텍스트 포맷터의 인스턴스를 만들 되는 즉시는 <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> 메서드. <xref:System.Windows.Media.TextFormatting.TextFormatter>다시 호출 텍스트와 텍스트 실행에 대 한 서식 지정 매개 변수를 검색 하도록 텍스트 원본의 양식을 선입니다.  
  
 다음 예제에서는 텍스트 저장소의 서식 지정 프로세스가 표시됩니다. <xref:System.Windows.Media.TextFormatting.TextFormatter> 개체를 사용 텍스트 줄 텍스트 저장소에서 검색 한 다음 텍스트 줄으로 드로잉에 대 한 서식을 지정 하는 <xref:System.Windows.Media.DrawingContext>합니다.  
  
 [!code-csharp[TextFormatterExample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>   
## <a name="implementing-the-client-text-store"></a>클라이언트 텍스트 저장소 구현  
 텍스트 서식 지정 엔진을 확장하는 경우 텍스트 저장소의 모든 측면을 구현하고 관리해야 합니다. 간단한 작업이 아닙니다. 텍스트 저장소는 텍스트 실행 속성, 단락 속성, 포함된 개체 및 이와 비슷한 콘텐츠를 추적합니다. 또한 텍스트 포맷터를 개별 제공 <xref:System.Windows.Media.TextFormatting.TextRun> 텍스트 포맷터를 사용 하 여 만드는 개체 <xref:System.Windows.Media.TextFormatting.TextLine> 개체입니다.  
  
 파생 해야 텍스트 저장소를 처리 하기 위해 텍스트 저장소 가상화 <xref:System.Windows.Media.TextFormatting.TextSource>합니다. <xref:System.Windows.Media.TextFormatting.TextSource>텍스트 포맷터 사용 하 여 텍스트 저장소에서 텍스트 실행을 검색 하는 메서드를 정의 합니다. <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>선 서식 지정에 사용 되는 텍스트를 검색 하도록 텍스트 포맷터에서 사용 되는 방법은 실행 됩니다. 에 대 한 호출 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> 다음 조건 중 하나가 발생할 때까지 텍스트 포맷터가 반복적으로 수행 합니다.  
  
-   A <xref:System.Windows.Media.TextFormatting.TextEndOfLine> 또는 서브 클래스에서 반환 됩니다.  
  
-   텍스트 실행의 누적 된 너비 초과를 텍스트 포맷터를 만드는 호출 또는 텍스트 포맷터에 대 한 호출에 지정 된 최대 선 두께 <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> 메서드.  
  
-   A [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] "CF", "LF" 또는 "CRLF" 같은 줄 바꿈 시퀀스가 반환 됩니다.  
  
<a name="section4"></a>   
## <a name="providing-text-runs"></a>텍스트 실행 제공  
 텍스트 서식 지정 프로세스의 핵심은 텍스트 포맷터와 텍스트 저장소 간의 상호 작용입니다. 구현 <xref:System.Windows.Media.TextFormatting.TextSource> 텍스트 포맷터에 제공 된 <xref:System.Windows.Media.TextFormatting.TextRun> 개체 및 텍스트를 실행 하는 형식을 지정 하는 데 사용할 속성입니다. 이 상호 작용에 의해 처리 됩니다는 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> 메서드 텍스트 포맷터에 의해 호출 됩니다.  
  
 다음 표에서 미리 정의 된 일부 <xref:System.Windows.Media.TextFormatting.TextRun> 개체입니다.  
  
|TextRun 유형|사용법|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|문자 모양의 표현을 텍스트 포맷터로 다시 전달하는 데 사용된 특수 텍스트 실행.|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|측정, 적중 테스트 및 그리기가 텍스트 내 이미지나 단추에서와 같이 전체적으로 수행되는 컨텐츠를 제공하는 데 사용된 특수 텍스트 실행.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|선의 끝을 표시하는 데 사용되는 특수 텍스트 실행.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|단락의 끝을 표시하는 데 사용되는 특수 텍스트 실행.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|실행 하는 특수 텍스트와 같은 이전 영향을 받는 범위를 종료 하는 세그먼트의 끝을 표시 하는 데 사용 <xref:System.Windows.Media.TextFormatting.TextModifier> 실행 합니다.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|숨겨진 문자 범위를 표시하는 데 사용된 특수 텍스트 실행.|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|해당 범위에서 텍스트 실행의 속성을 수정하는 데 사용된 특수 텍스트 실행. 범위를 일치 하는 다음 확장 <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> 를 실행 하는 텍스트 또는 다음 <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>합니다.|  
  
 미리 정의 된 <xref:System.Windows.Media.TextFormatting.TextRun> 개체 서브클래싱 할 수 있습니다. 이렇게 하면 텍스트 소스가 사용자 지정 데이터를 포함하는 텍스트 포맷터와 텍스트 실행을 제공할 수 있습니다.  
  
 다음 예제는 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> 메서드. 이 텍스트 저장소 반환 <xref:System.Windows.Media.TextFormatting.TextRun> 개체 처리를 위해 텍스트 포맷터를 합니다.  
  
 [!code-csharp[TextFormatterExample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
>  이 예제에서 텍스트 저장소는 모든 텍스트에 동일한 텍스트 속성을 제공합니다. 고급 텍스트 저장소는 자신의 범위 관리를 구현하여 개별 문자가 다른 속성을 가질 수 있도록 해야 합니다.  
  
<a name="section5"></a>   
## <a name="specifying-formatting-properties"></a>서식 속성 지정  
 <xref:System.Windows.Media.TextFormatting.TextRun>개체는 텍스트 저장소에 의해 제공 되는 속성을 사용 하 여 형식이 지정 됩니다. 이러한 속성 두 가지 형식으로 제공 <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> 및 <xref:System.Windows.Media.TextFormatting.TextRunProperties>합니다. <xref:System.Windows.Media.TextFormatting.TextParagraphProperties>와 같은 단락 (포함) 속성 처리 <xref:System.Windows.TextAlignment> 및 <xref:System.Windows.FlowDirection>합니다. <xref:System.Windows.Media.TextFormatting.TextRunProperties>각 텍스트 전경 브러시와 같은 단락 내에서 실행에 대 한 서로 다를 수 있는 속성은 <xref:System.Windows.Media.Typeface>, 및 글꼴 크기입니다. 사용자 지정 단락 및 속성 유형을 실행 하는 사용자 지정 텍스트를 구현 하려면 응용 프로그램에서 파생 된 클래스 만들어야 <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> 및 <xref:System.Windows.Media.TextFormatting.TextRunProperties> 각각.  
  
## <a name="see-also"></a>참고 항목  
 [WPF의 입력 체계](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
