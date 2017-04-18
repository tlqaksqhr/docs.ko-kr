---
title: "FolderBrowserDialog 구성 요소 개요(Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "FolderBrowserDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "디렉터리[Windows Forms], 응용 프로그램에서 찾아보기 사용"
  - "FolderBrowserDialog 구성 요소[Windows Forms], FolderBrowserDialog 정보"
  - "폴더[Windows Forms], 응용 프로그램에서 찾아보기 사용"
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# FolderBrowserDialog 구성 요소 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소는 폴더를 찾아서 선택하는 데 사용되는 모달 대화 상자입니다.  <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소 내에서 새 폴더를 만들 수도 있습니다.  
  
> [!NOTE]
>  폴더 대신 파일을 선택하려면 [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) 구성 요소를 사용하십시오.  
  
 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소는 런타임에 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용하여 표시됩니다.  <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> 속성을 설정하여 대화 상자의 트리 뷰에서 맨 위에 표시될 폴더와 하위 폴더를 지정하십시오.  대화 상자가 표시되면 <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> 속성을 사용하여 선택된 폴더의 경로를 가져올 수 있습니다.  
  
 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소가 폼에 추가되면 Windows Forms 디자이너의 아래쪽에 있는 트레이에 나타납니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.FolderBrowserDialog>   
 [방법: Windows Forms FolderBrowserDialog 구성 요소를 사용하여 폴더 선택](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)   
 [FolderBrowserDialog 구성 요소](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)