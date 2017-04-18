---
title: "방법: TextBox에 워터마크 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "배경 이미지를 사용하여 TextBox의 유용성 향상[WPF]"
  - "텍스트 상자 내부에 배경 이미지를 표시하여 사용자 입력 지원[WPF]"
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: TextBox에 워터마크 추가
다음 예제에서는 사용자가 텍스트를 입력하여 이미지가 제거되기 전까지 <xref:System.Windows.Controls.TextBox> 내에 설명 배경 이미지를 표시함으로써 <xref:System.Windows.Controls.TextBox>의 유용성을 높이는 방법을 보여 줍니다.  이 배경 이미지는 사용자가 입력 내용을 제거하면 다시 복원됩니다.  아래 그림을 참조하십시오.  
  
 ![배경 이미지가 있는 TextBox](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing\_TextBox\_using\_background\_image")  
  
> [!NOTE]
>  배경 이미지는 데이터 바인딩을 방해하지 않으므로 이 예제에서는 간단히 <xref:System.Windows.Controls.TextBox>의 <xref:System.Windows.Controls.TextBox.Text%2A> 속성을 조작하는 대신 배경 이미지를 사용합니다.  
  
## 예제  
 [!code-xml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## 참고 항목  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)