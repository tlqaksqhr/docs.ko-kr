---
title: "방법: Windows Forms LinkLabel 컨트롤에서 웹 페이지 표시(Visual Basic) | Microsoft Docs"
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
  - "LinkLabel1_LinkClicked"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "예제[Windows Forms], LinkLabel 컨트롤"
  - "링크, 폼에서 웹 페이지로"
  - "LinkLabel 컨트롤[Windows Forms], 예제"
  - "웹 페이지, 표시"
  - "Windows Forms, 웹 페이지에 연결"
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: Windows Forms LinkLabel 컨트롤에서 웹 페이지 표시(Visual Basic)
이 예제에서는 Windows Forms <xref:System.Windows.Forms.LinkLabel> 컨트롤을 클릭할 경우 기본 브라우저에 웹 페이지를 표시합니다.  
  
## 예제  
  
```vb  
Private Sub Form1_Load(ByVal sender As System.Object, ByVal e _  
As System.EventArgs) Handles MyBase.Load  
    LinkLabel1.Text = "Click here to get more info."  
    LinkLabel1.Links.Add(6, 4, "www.microsoft.com")  
End Sub  
Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, ByVal _  
e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) Handles _  
LinkLabel1.LinkClicked  
    System.Diagnostics.Process.Start(e.Link.LinkData.ToString())  
End Sub  
```  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `Form1`이라는 Windows Form  
  
-   `LinkLabel1`이라는 <xref:System.Windows.Forms.LinkLabel> 컨트롤  
  
-   활성 인터넷 연결  
  
## .NET Framework 보안  
 <xref:System.Diagnostics.Process.Start%2A> 메서드를 호출하려면 완전 신뢰가 필요합니다.  자세한 내용은 <xref:System.Security.SecurityException>을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.LinkLabel>   
 [LinkLabel 컨트롤](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)