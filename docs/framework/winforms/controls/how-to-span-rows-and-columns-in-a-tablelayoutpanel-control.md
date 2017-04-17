---
title: "방법: TableLayoutPanel 컨트롤에서 행과 열 확장 | Microsoft Docs"
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
  - "net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "셀, 병합"
  - "열[Windows Forms], 확장"
  - "셀 병합"
  - "행[Windows Forms], 확장"
  - "TableLayoutPanel 컨트롤[Windows Forms], 행 및 열 확장"
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: TableLayoutPanel 컨트롤에서 행과 열 확장
<xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 있는 컨트롤을 사용하여 인접한 행과 열을 확장할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 열과 행을 확장하려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 폼으로 끌어 옵니다.  
  
2.  **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 왼쪽 위 셀로 끌어 옵니다.  
  
3.  <xref:System.Windows.Forms.Button> 컨트롤의 **ColumnSpan** 속성을 2로 설정합니다.  <xref:System.Windows.Forms.Button> 컨트롤은 첫째 및 둘째 열을 확장합니다.  
  
4.  <xref:System.Windows.Forms.Button> 컨트롤의 **RowSpan** 속성을 2로 설정합니다.  <xref:System.Windows.Forms.Button> 컨트롤은 첫째 및 둘째 행을 확장합니다.  
  
5.  <xref:System.Windows.Forms.Button> 컨트롤의 **ColumnSpan** 속성을 1로 설정합니다.  <xref:System.Windows.Forms.Button> 컨트롤은 첫째 열로 이동하며 첫째 및 둘째 행을 확장합니다.  
  
## 참고 항목  
 [TableLayoutPanel 컨트롤](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)