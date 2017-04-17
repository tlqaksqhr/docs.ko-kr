---
title: "방법: Windows Forms의 ToolStrip 컨트롤에 대한 사용자 지정 렌더러 만들기 및 설정 | Microsoft Docs"
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
  - "예제[Windows Forms], 도구 모음"
  - "도구 모음[Windows Forms], 렌더링"
  - "ToolStrip 컨트롤[Windows Forms], 사용자 지정 렌더링"
  - "ToolStrip 컨트롤[Windows Forms], 렌더링"
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: Windows Forms의 ToolStrip 컨트롤에 대한 사용자 지정 렌더러 만들기 및 설정
<xref:System.Windows.Forms.ToolStrip> 컨트롤은 테마와 스타일을 쉽게 사용할 수 있도록 지원합니다.  <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=fullName> 속성이나 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=fullName> 속성을 사용자 지정 렌더러로 설정하여 사용자 지정 모양과 동작\(모양과 느낌\)을 완전히 구현할 수 있습니다.  
  
 각각의 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip> 또는 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 렌더러를 할당하거나 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=fullName> 속성을 <xref:System.Windows.Forms.ToolStripRenderMode?displayProperty=fullName>로 설정하여 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> 속성을 통해 모든 개체에 영향을 줄 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>는 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=fullName>의 값이 `null`이 아닌 경우에만 <xref:System.Windows.Forms.ToolStripRenderMode>을 반환합니다.  
  
### 사용자 지정 렌더러를 만들려면  
  
1.  <xref:System.Windows.Forms.ToolStripRenderer> 클래스를 확장합니다.  
  
2.  적절한 *On…* 멤버를 재정의하여 원하는 사용자 지정 렌더링을 구현합니다.  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)   
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
  
    ```  
  
     \[C\#\]  
  
    ```  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
  
    ```  
  
### 사용자 지정 렌더러를 현재 렌더러로 설정하려면  
  
1.  한 <xref:System.Windows.Forms.ToolStrip>의 사용자 지정 렌더러를 설정하려면 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=fullName> 속성을 사용자 지정 렌더러로 설정합니다.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
  
    ```  
  
     \[C\#\]  
  
    ```  
    toolStrip1.Renderer = new RedTextRenderer();  
  
    ```  
  
2.  또는 응용 프로그램에 포함된 모든 <xref:System.Windows.Forms.ToolStrip> 클래스의 사용자 지정 렌더러를 설정하려면 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=fullName> 속성을 사용자 지정 렌더러로 설정하고 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 속성을 <xref:System.Windows.Forms.ToolStripRenderMode>로 설정합니다.  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
  
    ```  
  
     \[C\#\]  
  
    ```  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>   
 <xref:System.Windows.Forms.ToolStripRenderer>   
 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>   
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [ToolStrip 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [ToolStrip 기술 요약](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)