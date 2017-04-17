---
title: "방법: Windows Forms 패널의 배경 설정 | Microsoft Docs"
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
  - "배경색, Windows Forms Panel 컨트롤"
  - "배경 이미지, Windows Forms Panel 컨트롤"
  - "색, Windows Forms Panel 컨트롤"
  - "Panel 컨트롤[Windows Forms], 배경"
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Forms 패널의 배경 설정
Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤은 배경색과 배경 이미지를 모두 표시할 수 있습니다.  <xref:System.Windows.Forms.Control.BackColor%2A> 속성은 레이블과 라디오 단추와 같이 포함된 컨트롤의 배경색을 설정합니다.  <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정되어 있지 않으면 전체 패널이 <xref:System.Windows.Forms.Control.BackColor%2A>에서 선택한 색으로 채워집니다.  <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정되어 있으면 포함된 컨트롤 뒤에 이미지가 표시됩니다.  
  
### 프로그래밍 방식으로 배경을 설정하려면  
  
1.  패널의 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 <xref:System.Drawing.Color?displayProperty=fullName> 형식의 값으로 설정합니다.  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2.  <xref:System.Drawing.Image?displayProperty=fullName> 클래스의 <xref:System.Drawing.Image.FromFile%2A> 메서드를 사용하여 패널의 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성을 설정합니다.  
  
    ```vb  
    ' You should replace the bolded image   
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
  
    ```  
  
    ```csharp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
  
    ```  
  
    ```cpp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.Control.BackColor%2A>   
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>   
 [Panel 컨트롤](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)   
 [Panel 컨트롤 개요](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)