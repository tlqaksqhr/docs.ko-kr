---
title: RichTextBox 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], RichTextBox
- RichTextBox control [WPF], about RichTextBox control
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
ms.openlocfilehash: 319dc43c0953b82da94eb6dd698f1a6afd582dbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="richtextbox-overview"></a>RichTextBox 개요
<xref:System.Windows.Controls.RichTextBox> 컨트롤 표시 하거나 단락, 이미지, 테이블 등 유동 콘텐츠를 편집할 수 있습니다. 이 항목에서는 소개는 <xref:System.Windows.Controls.TextBox> 모두에서 사용 하는 방법의 예제를 제공 하 고 클래스 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 및 C#입니다.  
  
  
<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>TextBox 또는 RichTextBox?  
 둘 다 <xref:System.Windows.Controls.RichTextBox> 및 <xref:System.Windows.Controls.TextBox> 두 컨트롤은 다양 한 시나리오에서 사용 되는 반면, 사용자가 텍스트를 편집할 수 있도록 합니다. A <xref:System.Windows.Controls.RichTextBox> 서식 있는 텍스트, 이미지, 테이블 또는 기타 풍부한 콘텐츠를 편집 하려면 사용자에 대 한 필요한 경우에 더 유용 합니다. 예를 들어, 문서, 문서 또는 서식, 필요한 블로그 편집 이미지, 등을 사용 하 여 훌륭하게 수행할는 <xref:System.Windows.Controls.RichTextBox>합니다. A <xref:System.Windows.Controls.TextBox> 적은 시스템 리소스를 필요 없으면 <xref:System.Windows.Controls.RichTextBox> 는 일반 텍스트 해야 함 (즉, 형태로 사용)를 편집 합니다. 참조 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md) 대 한 자세한 내용은 <xref:System.Windows.Controls.TextBox>합니다. 다음 표에서의 주요 기능을 요약 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.RichTextBox>합니다.  
  
|Control|실시간 맞춤법 검사|상황에 맞는 메뉴|서식 명령 처럼 <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B)|<xref:System.Windows.Documents.FlowDocument> 이미지, 단락, 테이블 등과 같은 콘텐츠입니다.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|예|예|아니요|아니요.|  
|<xref:System.Windows.Controls.RichTextBox>|예|예|예|예|  
  
 **참고:** 있지만 <xref:System.Windows.Controls.TextBox> 포맷 등의 관련된 명령을 지원 하지 않는 <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B)와 같은 많은 기본 명령은 두 컨트롤 모두에서 지원 됩니다 <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>합니다.  
  
 위 테이블의 기능은 나중에 더 자세히 설명합니다.  
  
<a name="creating_a_richtextbox"></a>   
## <a name="creating-a-richtextbox"></a>RichTextBox 만들기  
 아래 코드를 만드는 방법을 보여는 <xref:System.Windows.Controls.RichTextBox> 풍부한 콘텐츠를 편집할 수 있습니다.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]  
  
 특히,에서 편집 된 콘텐츠는 <xref:System.Windows.Controls.RichTextBox> 는 유동 콘텐츠입니다. 유동 콘텐츠에는 서식 있는 텍스트, 이미지, 목록 및 테이블과 같은 다양한 요소 형식이 포함될 수 있습니다. 유동 문서에 대한 자세한 내용은 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)를 참조하세요. 유동 콘텐츠를 포함 하기 위해 한 <xref:System.Windows.Controls.RichTextBox> 호스트는 <xref:System.Windows.Documents.FlowDocument> 개체 편집 가능한 콘텐츠를 포함 합니다. 유동 콘텐츠를 설명 하기 위해는 <xref:System.Windows.Controls.RichTextBox>, 다음 코드를 만드는 방법을 보여 줍니다는 <xref:System.Windows.Controls.RichTextBox> 단락 및 일부 굵게 표시 된 텍스트와 함께 합니다.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]  
  
 [!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
 [!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]  
  
 다음 그림은 이 샘플에서 렌더링하는 방법을 보여줍니다.  
  
 ![콘텐츠가 있는 RichTextBox](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")  
  
 같은 요소 <xref:System.Windows.Documents.Paragraph> 및 <xref:System.Windows.Documents.Bold> 확인 방법을 내부 콘텐츠는 <xref:System.Windows.Controls.RichTextBox> 나타납니다. 사용자 편집 <xref:System.Windows.Controls.RichTextBox> 유동 콘텐츠를이 변경 내용입니다. 유동 콘텐츠의 기능 및 이를 사용하는 방법에 대한 자세한 내용은 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)를 참조하세요.  
  
 **참고:** 내의 유동 콘텐츠는 <xref:System.Windows.Controls.RichTextBox> 유동 콘텐츠를 다른 컨트롤에 포함 된 경우와 동일 하 게 작동 하지 않습니다. 예를 들어 열이 없는에 <xref:System.Windows.Controls.RichTextBox> 따라서 아니요 자동 크기 조정 동작 하 고 있습니다. 또한 검색, 보기 모드, 페이지 탐색 및 확대/축소 내에서 사용할 수 없는 같이 기능에서 기본적으로 <xref:System.Windows.Controls.RichTextBox>합니다.  
  
<a name="realtime_spellechecking"></a>   
## <a name="real-time-spell-checking"></a>실시간 맞춤법 검사  
 실시간 맞춤법 검사를 사용 하도록 설정할 수는 <xref:System.Windows.Controls.TextBox> 또는 <xref:System.Windows.Controls.RichTextBox>합니다. 맞춤법 검사 기능이 켜져 있으면 맞춤법이 틀린 단어 밑에 빨간색 선이 나타납니다(아래 그림 참조).  
  
 ![맞춤법 검사 기능이 있는 Textbox](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 맞춤법 검사를 사용하도록 설정하는 방법에 대한 자세한 내용은 [텍스트 편집 컨트롤에서 맞춤법 검사 사용](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)을 참조하세요.  
  
<a name="context_menu"></a>   
## <a name="context-menu"></a>상황에 맞는 메뉴  
 기본적으로 둘 다 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.RichTextBox> 컨트롤 내부에 단추로 클릭할 때 표시 되는 상황에 맞는 메뉴를 가질 수 있습니다. 상황에 맞는 메뉴를 통해 사용자는 항목을 잘라내거나, 복사하거나, 붙여넣을 수 있습니다(아래 그림 참조).  
  
 ![상황에 맞는 메뉴가 있는 TextBox](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 자체적인 사용자 지정 상황에 맞는 메뉴를 만들어 기본 상황에 맞는 메뉴를 재정의할 수 있습니다. 자세한 내용은 [RichTextBox에서 사용자 지정 상황에 맞는 메뉴의 위치 지정](../../../../docs/framework/wpf/controls/how-to-position-a-custom-context-menu-in-a-richtextbox.md)을 참조하세요.  
  
<a name="detect_when_content_changes"></a>   
## <a name="editing-commands"></a>편집 명령  
 편집 명령을 사용 하면 사용자가 내에 편집 가능한 콘텐츠 형식을 지정 하는 <xref:System.Windows.Controls.RichTextBox>합니다. 기본 편집 명령, 외 <xref:System.Windows.Controls.RichTextBox> 포함 하는 서식 지정 명령이 <xref:System.Windows.Controls.TextBox> 지원 하지 않습니다. 예를 들어에서 편집할 때는 <xref:System.Windows.Controls.RichTextBox>, 사용자 수 Ctr + B를 눌러 굵은 텍스트 서식을 설정/해제 합니다. 참조 <xref:System.Windows.Documents.EditingCommands> 사용할 수 있는 명령의 전체 목록은 합니다. 바로 가기 키를 사용하는 방법 외에 단추와 같은 다른 컨트롤에 명령을 연결할 수 있습니다. 다음 예제에서는 사용자가 텍스트 서식을 변경하는 데 사용할 수 있는 단추가 포함된 간단한 도구 모음을 만드는 방법을 보여 줍니다.  
  
 [!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]  
  
 다음 그림은 이 샘플에서 표시하는 방법을 보여줍니다.  
  
 ![가 있는 RichTextBox](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>콘텐츠가 변경되는 시점 감지  
 일반적으로 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트 감지 하는 데 사용 해야의 텍스트는 <xref:System.Windows.Controls.TextBox> 또는 <xref:System.Windows.Controls.RichTextBox> 아니라 변경 <xref:System.Windows.UIElement.KeyDown> 예상 대로 합니다. 예제를 보려면 [TextBox에서 텍스트가 변경되는 시점 감지](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md)를 참조하세요.  
  
<a name="save_load_and_print_richtextbox_content"></a>   
## <a name="save-load-and-print-richtextbox-content"></a>RichTextBox 콘텐츠 저장, 로드 및 인쇄  
 내용을 저장 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.RichTextBox> 로드에 다시 해당 파일에 <xref:System.Windows.Controls.RichTextBox>, 내용을 인쇄 하 고 있습니다. 예제에 대한 태그는 다음과 같습니다.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
 예제에 대한 코드 숨김은 다음과 같습니다.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목  
 [방법 항목](../../../../docs/framework/wpf/controls/richtextbox-how-to-topics.md)  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)
