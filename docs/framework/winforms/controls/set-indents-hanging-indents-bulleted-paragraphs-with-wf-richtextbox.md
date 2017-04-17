---
title: "방법: Windows Forms RichTextBox 컨트롤을 사용하여 들여쓰기, 내어쓰기 및 글머리 기호 단락 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - ".rtf 파일, RichTextBox 컨트롤에서 형식 지정"
  - "예제[Windows Forms], 텍스트 상자"
  - "RichTextBox 컨트롤[Windows Forms], 들여쓰기 및 글머리 설정"
  - "RTF 파일, RichTextBox 컨트롤에서 형식 지정"
  - "텍스트 상자, 글머리 기호"
  - "텍스트 상자, 들여쓰기 설정"
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Windows Forms RichTextBox 컨트롤을 사용하여 들여쓰기, 내어쓰기 및 글머리 기호 단락 설정
Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤에는 표시되는 텍스트의 서식을 지정하기 위한 옵션이 많이 있습니다.  <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> 속성을 설정하면 선택한 단락의 서식을 글머리 기호 목록으로 지정할 수 있습니다.  또한 <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> 및 <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> 속성을 사용하여 컨트롤의 왼쪽\/오른쪽 가장자리와 다른 텍스트 줄의 왼쪽 가장자리를 기준으로 단락 들여쓰기를 설정할 수도 있습니다.  
  
### 단락의 서식을 글머리 기호 목록으로 지정하려면  
  
1.  <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> 속성을 `true`으로 설정합니다.  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### 단락을 들여쓰려면  
  
1.  컨트롤의 왼쪽 가장자리와 텍스트의 왼쪽 가장자리 사이의 거리를 픽셀 단위로 나타내는 정수를 <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> 속성에 설정합니다.  
  
2.  단락에서 첫 번째 텍스트 줄의 왼쪽 가장자리와 같은 단락에서 나머지 줄의 왼쪽 가장자리 사이의 거리를 픽셀 단위로 나타내는 정수를 <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> 속성에 설정합니다.  <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> 속성의 값은 단락에서 첫 번째 줄을 제외하고 줄 바꿈된 나머지 줄에만 적용됩니다.  
  
3.  컨트롤의 오른쪽 가장자리와 텍스트의 오른쪽 가장자리 사이의 거리를 픽셀 단위로 나타내는 정수를 <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> 속성에 설정합니다.  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    >  이러한 모든 속성은 선택한 텍스트가 포함된 단락 및 현재 삽입 지점 이후로 입력하는 텍스트에 영향을 줍니다.  예를 들어 단락에서 단어를 선택한 다음 들여쓰기를 조정하면 이 단어가 포함된 전체 단락뿐만 아니라 선택한 단락 이후에 입력되는 모든 단락에 새 설정이 적용됩니다.  프로그래밍 방식으로 텍스트를 선택하는 데 대한 내용은 [TextBoxBase.Select 메서드](frlrfSystemWindowsFormsTextBoxBaseClassSelectTopic)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox 컨트롤](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)