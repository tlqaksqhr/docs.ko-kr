---
title: "RichTextBox 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "컨트롤, RichTextBox"
  - "RichTextBox 컨트롤[WPF], RichTextBox 컨트롤 정보"
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# RichTextBox 개요
<xref:System.Windows.Controls.RichTextBox> 컨트롤을 사용하면 단락, 이미지, 표 등을 비롯한 유동 콘텐츠를 표시하거나 편집할 수 있습니다.  이 항목에서는 <xref:System.Windows.Controls.TextBox> 클래스를 소개하고 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 및 [!INCLUDE[TLA#tla_lhcshrp](../../../../includes/tlasharptla-lhcshrp-md.md)]에서 이 클래스를 사용하는 방법에 대한 예제를 제공합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="textbox_or_richtextbox"></a>   
## TextBox 또는 RichTextBox?  
 <xref:System.Windows.Controls.RichTextBox> 및 <xref:System.Windows.Controls.TextBox>에서는 사용자가 텍스트를 편집하는 것이 모두 허용되지만 다른 시나리오에서 두 개의 컨트롤이 사용됩니다.  서식 있는 텍스트, 이미지, 표 또는 기타 풍부한 콘텐츠를 편집해야 할 경우에는 <xref:System.Windows.Controls.RichTextBox>가 더 적합합니다.  예를 들어 서식, 이미지 등이 필요한 문서, 기사 또는 블로그를 편집할 때는 <xref:System.Windows.Controls.RichTextBox>를 사용하는 것이 가장 좋습니다.  <xref:System.Windows.Controls.TextBox>에는 <xref:System.Windows.Controls.RichTextBox>보다 적은 시스템 리소스가 필요하므로 일반 텍스트만 편집해야 하는 경우\(예: 폼에서 사용\)에  적합합니다.  <xref:System.Windows.Controls.TextBox>에 대한 자세한 내용은 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)를 참조하십시오.  아래 표에서는 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.RichTextBox>의 기본 기능을 요약하여 보여 줍니다.  
  
|컨트롤|실시간 맞춤법 검사|상황에 맞는 메뉴|<xref:System.Windows.Documents.EditingCommands.ToggleBold%2A>\(Ctr\+B\)와 같은 서식 명령|이미지, 단락, 표 등과 같은 <xref:System.Windows.Documents.FlowDocument> 콘텐츠|  
|---------|----------------|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|예|예|아니요|아니요.|  
|<xref:System.Windows.Controls.RichTextBox>|예|예|예|예|  
  
 **참고:** <xref:System.Windows.Controls.TextBox>에서는 <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A>\(Ctr\+B\)와 같은 서식 관련 명령이 지원되지 않지만 <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>와 같은 대부분의 기본 명령은 두 컨트롤 모두에서 지원됩니다.  
  
 위 표의 기능은 뒷부분에서 자세히 설명합니다.  
  
<a name="creating_a_richtextbox"></a>   
## RichTextBox 만들기  
 아래 코드에서는 사용자가 풍부한 콘텐츠를 편집할 수 있는 <xref:System.Windows.Controls.RichTextBox>를 만드는 방법을 보여 줍니다.  
  
 [!code-xml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]  
  
 특히 <xref:System.Windows.Controls.RichTextBox>에서 편집된 콘텐츠는 유동 콘텐츠입니다.  유동 콘텐츠에는 서식 있는 텍스트, 이미지, 목록 및 표를 비롯하여 요소의 많은 형식이 포함될 수 있습니다.  유동 문서에 대한 자세한 내용은 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)를 참조하십시오.  유동 콘텐츠를 포함할 수 있도록 <xref:System.Windows.Controls.RichTextBox>는 <xref:System.Windows.Documents.FlowDocument> 개체를 호스팅하고 이 개체에는 편집 가능한 콘텐츠가 포함됩니다.  <xref:System.Windows.Controls.RichTextBox>의 유동 콘텐츠를 설명하기 위해 다음 코드에서는 단락 및 몇 개의 굵게 표시된 텍스트를 사용하여 <xref:System.Windows.Controls.RichTextBox>를 만드는 방법을 보여 줍니다.  
  
 [!code-xml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]  
  
 [!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
 [!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]  
  
 다음 그림에서는 이 샘플이 렌더링되는 방식을 보여 줍니다.  
  
 ![콘텐츠가 있는 RichTextBox](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-content.png "Editing\_RichTextBox\_with\_Content")  
  
 <xref:System.Windows.Documents.Paragraph> 및 <xref:System.Windows.Documents.Bold>와 같은 요소는 <xref:System.Windows.Controls.RichTextBox> 내의 콘텐츠가 표시되는 방식을 결정합니다.  사용자가 <xref:System.Windows.Controls.RichTextBox> 콘텐츠를 편집하면 이 유동 콘텐츠가 변경됩니다.  유동 콘텐츠의 기능 및 그 사용 방법에 대한 자세한 내용은 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)를 참조하십시오.  
  
 **참고:** <xref:System.Windows.Controls.RichTextBox> 내의 유동 콘텐츠는 다른 컨트롤에 포함된 유동 콘텐츠와 동일하게 작동하지 않습니다.  예를 들어 <xref:System.Windows.Controls.RichTextBox>에는 열이 없으므로 자동 크기 조정 동작이 발생하지 않습니다.  또한 검색, 보기 모드, 페이지 탐색, 확대\/축소 등과 같은 기본 제공 기능을 <xref:System.Windows.Controls.RichTextBox> 내에서 사용할 수 없습니다.  
  
<a name="realtime_spellechecking"></a>   
## 실시간 맞춤법 검사  
 <xref:System.Windows.Controls.TextBox> 또는 <xref:System.Windows.Controls.RichTextBox>에서 실시간 맞춤법 검사를 설정할 수 있습니다.  맞춤법 검사가 설정된 경우 맞춤법이 틀린 모든 단어 아래에 빨간색 줄이 나타납니다\(아래 그림 참조\).  
  
 ![맞춤법 검사 기능이 있는 Textbox](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing\_TextBox\_with\_Spellchecking")  
  
 맞춤법 검사를 사용하도록 설정하는 방법은 [텍스트 편집 컨트롤에서 맞춤법 검사 사용](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)을 참조하십시오.  
  
<a name="context_menu"></a>   
## 상황에 맞는 메뉴  
 기본적으로 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.RichTextBox> 모두에는 사용자가 컨트롤 안에서 마우스 오른쪽 단추를 클릭했을 때 표시되는 상황에 맞는 메뉴가 있습니다.  상황에 맞는 메뉴를 사용하여 잘라내기, 복사 또는 붙여넣기를 수행할 수 있습니다\(아래 그림 참조\).  
  
 ![상황에 맞는 메뉴가 있는 TextBox](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing\_TextBox\_with\_Context\_Menu")  
  
 사용자 지정된 고유한 상황에 맞는 메뉴를 만들어 기본 메뉴를 재정의할 수 있습니다.  자세한 내용은 [RichTextBox에서 사용자 지정 상황에 맞는 메뉴의 위치 지정](../../../../docs/framework/wpf/controls/how-to-position-a-custom-context-menu-in-a-richtextbox.md)을 참조하십시오.  
  
<a name="detect_when_content_changes"></a>   
## 편집 명령  
 편집 명령을 사용하면 <xref:System.Windows.Controls.RichTextBox> 내에서 편집 가능한 콘텐츠의 서식을 지정할 수 있습니다.  기본 편집 명령 외에 <xref:System.Windows.Controls.RichTextBox>에는 <xref:System.Windows.Controls.TextBox>에서 지원하지 않는 서식 지정 명령이 포함됩니다.  예를 들어 <xref:System.Windows.Controls.RichTextBox>에서 편집할 때 사용자는 Ctr\+B를 눌러 굵은 텍스트 서식을 전환할 수 있습니다.  사용할 수 있는 명령의 전체 목록을 보려면 <xref:System.Windows.Documents.EditingCommands>를 참조하십시오.  바로 가기 키를 사용하는 것 외에도 단추 같은 다른 컨트롤에 명령을 후크할 수 있습니다.  다음 예제에서는 사용자가 텍스트 서식 변경에 사용할 수 있는 단추가 포함된 간단한 도구 모음을 만드는 방법을 보여 줍니다.  
  
 [!code-xml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]  
  
 다음 그림에서는 이 샘플이 표시되는 방식을 보여 줍니다.  
  
 ![도구 모음이 있는 RichTextBox](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-toobar.png "Editing\_RichTextBox\_with\_TooBar")  
  
<a name="editing_commands"></a>   
## 콘텐츠가 변경되는 시점 감지  
 일반적으로 <xref:System.Windows.Controls.TextBox> 또는 <xref:System.Windows.Controls.RichTextBox>의 텍스트가 변경되는 시점을 감지하려면 예상과 달리 <xref:System.Windows.UIElement.KeyDown>이 아닌 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트를 사용해야 합니다.  예제는 [TextBox에서 텍스트가 변경되는 시점 감지](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md)를 참조하십시오.  
  
<a name="save_load_and_print_richtextbox_content"></a>   
## RichTextBox 콘텐츠 저장, 로드 및 인쇄  
 다음 예제에서는 <xref:System.Windows.Controls.RichTextBox>의 콘텐츠를 파일에 저장하고 이를 다시 <xref:System.Windows.Controls.RichTextBox>에 로드하며 해당 콘텐츠를 인쇄하는 방법을 보여 줍니다.  다음은 예제의 태그입니다.  
  
 [!code-xml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
 다음은 예제의 코드 숨김입니다.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## 참고 항목  
 [방법 항목](../../../../docs/framework/wpf/controls/richtextbox-how-to-topics.md)   
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)