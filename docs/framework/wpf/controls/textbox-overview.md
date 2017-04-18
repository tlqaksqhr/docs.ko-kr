---
title: "TextBox 개요 | Microsoft Docs"
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
  - "컨트롤, TextBox"
  - "TextBox 컨트롤, TextBox 컨트롤 정보"
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# TextBox 개요
<xref:System.Windows.Controls.TextBox> 클래스를 사용하면 서식 없는 텍스트를 표시하거나 편집할 수 있습니다.  <xref:System.Windows.Controls.TextBox>의 일반적인 용도는 폼에 있는 서식 없는 텍스트를 편집하는 것입니다.  예를 들어 사용자의 이름, 전화 번호 등을 묻는 폼은 텍스트 입력을 위한 <xref:System.Windows.Controls.TextBox> 컨트롤을 사용할 것입니다.  이 항목에서는 <xref:System.Windows.Controls.TextBox> 클래스를 소개하고 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 및 [!INCLUDE[TLA#tla_lhcshrp](../../../../includes/tlasharptla-lhcshrp-md.md)]에서 이 클래스를 사용하는 방법에 대한 예제를 제공합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="textbox_or_richtextbox"></a>   
## TextBox 또는 RichTextBox?  
 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.RichTextBox>에서는 사용자가 텍스트를 입력하는 것이 모두 허용되지만 다른 시나리오를 위한 두 개의 컨트롤이 사용됩니다.  <xref:System.Windows.Controls.TextBox>에는 <xref:System.Windows.Controls.RichTextBox>보다 적은 시스템 리소스가 필요하므로 일반 텍스트만 편집해야 하는 경우\(예: 폼에서 사용\)에 적합합니다.  서식 있는 텍스트, 이미지, 테이블 또는 기타 지원되는 콘텐츠를 편집해야 할 경우에는 <xref:System.Windows.Controls.RichTextBox>가 더 적합합니다.  예를 들어 서식, 이미지 등이 필요한 문서, 기사 또는 블로그를 편집할 때는 <xref:System.Windows.Controls.RichTextBox>를 사용하는 것이 가장 좋습니다.  아래 표에서는 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.TextBox>의 기본 기능을 요약하여 보여 줍니다.  
  
|컨트롤|실시간 맞춤법 검사|상황에 맞는 메뉴|<xref:System.Windows.Documents.EditingCommands.ToggleBold%2A>\(Ctr\+B\)와 같은 서식 명령|이미지, 단락, 표 등과 같은 <xref:System.Windows.Documents.FlowDocument> 콘텐츠|  
|---------|----------------|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|예|예|아니요|아니요.|  
|<xref:System.Windows.Controls.RichTextBox>|예|예|예\([RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md) 참조\)|예\([RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md) 참조\)|  
  
> [!NOTE]
>  <xref:System.Windows.Controls.TextBox>에서는 <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A>\(Ctr\+B\)와 같은 서식 관련 편집 명령이 지원되지 않지만 <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>와 같은 대부분의 기본 명령은 두 컨트롤 모두에서 지원됩니다.  자세한 내용은 <xref:System.Windows.Documents.EditingCommands>를 참조하십시오.  
  
 <xref:System.Windows.Controls.TextBox>에서 지원되는 기능은 아래 단원에 설명되어 있습니다.  <xref:System.Windows.Controls.RichTextBox>에 대한 자세한 내용은 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)를 참조하십시오.  
  
### 실시간 맞춤법 검사  
 <xref:System.Windows.Controls.TextBox> 또는 <xref:System.Windows.Controls.RichTextBox>에서 실시간 맞춤법 검사를 사용하도록 설정할 수 있습니다.  맞춤법 검사가 설정된 경우 맞춤법이 틀린 모든 단어 아래에 빨간색 줄이 나타납니다\(아래 그림 참조\).  
  
 ![맞춤법 검사 기능이 있는 Textbox](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing\_TextBox\_with\_Spellchecking")  
  
 맞춤법 검사를 사용하도록 설정하는 방법은 [텍스트 편집 컨트롤에서 맞춤법 검사 사용](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)을 참조하십시오.  
  
### 상황에 맞는 메뉴  
 기본적으로 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.RichTextBox> 모두에는 사용자가 컨트롤 안에서 마우스 오른쪽 단추를 클릭했을 때 표시되는 상황에 맞는 메뉴가 있습니다.  상황에 맞는 메뉴를 사용하여 잘라내기, 복사 또는 붙여넣기를 수행할 수 있습니다\(아래 그림 참조\).  
  
 ![상황에 맞는 메뉴가 있는 TextBox](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing\_TextBox\_with\_Context\_Menu")  
  
 사용자 지정된 고유한 상황에 맞는 메뉴를 만들어 기본 동작을 재정의할 수 있습니다.  자세한 내용은 [TextBox에 사용자 지정 컨텍스트 메뉴 사용](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)을 참조하십시오.  
  
<a name="creating_textboxes"></a>   
## TextBox 만들기  
 <xref:System.Windows.Controls.TextBox>는 한 줄 높이가 되거나 여러 줄로 구성될 수 있습니다.  한 줄의 <xref:System.Windows.Controls.TextBox>는 작은 양의 일반 텍스트\(예: 폼에 있는 "  이름", "전호 번호" 등\)를  입력하는 데 적합합니다.  다음 예제에서는 한 줄의 <xref:System.Windows.Controls.TextBox>를 만드는 방법을 보여 줍니다.  
  
 [!code-xml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 또한 사용자가 여러 줄의 텍스트를 입력할 수 있게 하는 <xref:System.Windows.Controls.TextBox>를 만들 수 있습니다.  예를 들어 사용자의 약력을 묻는 폼이 있을 경우 여러 줄의 텍스트를 지원하는 <xref:System.Windows.Controls.TextBox>를 사용할 수 있습니다.  다음 예제에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 사용하여 여러 줄의 텍스트를 수용하도록 자동으로 확장되는 <xref:System.Windows.Controls.TextBox> 컨트롤을 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 <xref:System.Windows.Controls.TextBox.TextWrapping%2A> 특성을 `Wrap`으로 설정하면 <xref:System.Windows.Controls.TextBox> 컨트롤의 가장자리에 도달할 때 텍스트가 새 줄로 바뀌고, 필요한 경우 <xref:System.Windows.Controls.TextBox> 컨트롤이 자동으로 늘어나 새 줄을 위한 공간이 확보됩니다.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> 특성을 `true`로 설정하면 Return 키를 눌렀을 때 새 줄이 삽입되고 한 번 더 누르면 필요한 경우 <xref:System.Windows.Controls.TextBox> 컨트롤이 자동으로 늘어나 새 줄을 위한 공간이 확보됩니다.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> 특성은 스크롤 막대를 <xref:System.Windows.Controls.TextBox>에 추가하므로 둘러싼 프레임이나 창의 크기를 초과하여 <xref:System.Windows.Controls.TextBox>가 늘어날 경우에도 <xref:System.Windows.Controls.TextBox>의 내용을 스크롤할 수 있습니다.  
  
 <xref:System.Windows.Controls.TextBox> 사용과 연관된 다른 작업에 대한 자세한 내용은 [방법 항목](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md)을 참조하십시오.  
  
<a name="editing_commands"></a>   
## 콘텐츠가 변경되는 시점 감지  
 일반적으로 <xref:System.Windows.Controls.TextBox> 또는 <xref:System.Windows.Controls.RichTextBox>의 텍스트가 변경되는 시점을 감지하려면 예상과 달리 <xref:System.Windows.UIElement.KeyDown>이 아닌 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트를 사용해야 합니다.  예제는 [TextBox에서 텍스트가 변경되는 시점 감지](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md)를 참조하십시오.  
  
## 참고 항목  
 [방법 항목](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md)   
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)