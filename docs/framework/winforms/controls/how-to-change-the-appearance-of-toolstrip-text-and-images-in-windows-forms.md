---
title: "방법: Windows Forms에서 ToolStrip 텍스트 및 이미지의 모양 변경 | Microsoft Docs"
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
  - "도구 모음[Windows Forms], 모양"
  - "도구 모음[Windows Forms], 이미지"
  - "도구 모음[Windows Forms], 텍스트"
  - "ToolStrip 컨트롤[Windows Forms], 모양"
  - "ToolStrip 컨트롤[Windows Forms], 이미지"
  - "ToolStrip 컨트롤[Windows Forms], 텍스트"
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Windows Forms에서 ToolStrip 텍스트 및 이미지의 모양 변경
<xref:System.Windows.Forms.ToolStripItem>에 텍스트와 이미지를 표시할지 여부와 서로 상대적으로 맞추거나 <xref:System.Windows.Forms.ToolStrip>을 기준으로 맞추는 방법을 제어할 수 있습니다.  
  
### ToolStripItem에 표시할 항목을 정의하려면  
  
-   <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 속성을 원하는 값으로 설정합니다.  가능한 값으로는 `Image`, `ImageAndText`, `None` 및 `Text`가 있습니다.  기본값은 `ImageAndText`입니다.  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
  
    ```  
  
### ToolStripItem에서 텍스트를 맞추려면  
  
-   <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> 속성을 원하는 값으로 설정합니다.  위쪽, 중간, 아래쪽과 왼쪽, 가운데, 오른쪽을 조합하여 사용할 수 있습니다.  기본값은 `MiddleCenter`입니다.  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
  
    ```  
  
### ToolStripItem에서 이미지를 맞추려면  
  
-   <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> 속성을 원하는 값으로 설정합니다.  위쪽, 중간, 아래쪽과 왼쪽, 가운데, 오른쪽을 조합하여 사용할 수 있습니다.  기본값은 `MiddleLeft`입니다.  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
  
    ```  
  
### ToolStripItem 텍스트와 이미지를 서로 상대적으로 표시할 방법을 정의하려면  
  
-   <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> 속성을 원하는 값으로 설정합니다.  가능한 값으로는 `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage` 및 `TextBeforeImage`가 있습니다.  기본값은 `ImageBeforeText`입니다.  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStrip>   
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [ToolStrip 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [ToolStrip 기술 요약](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)