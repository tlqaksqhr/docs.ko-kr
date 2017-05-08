---
title: "TableLayoutPanel 컨트롤의 AutoSize 동작 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "자동 크기 조정"
  - "AutoSize 속성, TableLayoutPanel 컨트롤"
  - "AutoSizeMode 속성"
  - "컨트롤[Windows Forms], 크기 조정"
  - "레이아웃[Windows Forms], AutoSize"
  - "폼 지역화"
  - "크기 조정, 자동"
  - "TableLayoutPanel 컨트롤[Windows Forms], AutoSize 동작"
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# TableLayoutPanel 컨트롤의 AutoSize 동작
## 고유한 AutoSize 동작  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 다음과 같은 방법으로 자동 크기 조정 동작을 지원합니다.  
  
-   <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 통해  
  
-   <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 열 및 행 스타일에 대한 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성을 통해  
  
### 행 및 열 스타일의 AutoSize 속성  
 다음 표에서는 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성과 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 열 및 행 스타일 사이의 상호 작용을 설명합니다.  
  
|AutoSize 설정|스타일 상호 작용|  
|-----------------|---------------|  
|`false`|<xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 왼쪽에서 오른쪽으로 진행하며 열이나 행에 공간을 할당하거나 다음 순서대로 공간을 할당합니다.<br /><br /> 1.  <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성을 <xref:System.Windows.Forms.SizeType>로 설정하면 <xref:System.Windows.Forms.ColumnStyle.Width%2A> 또는 <xref:System.Windows.Forms.RowStyle.Height%2A>에서 지정한 픽셀 수가 할당됩니다.<br />2.  <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 속성을 <xref:System.Windows.Forms.SizeType>로 설정하면 자식 컨트롤의 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 메서드에서 반환되는 픽셀 수가 할당됩니다.<br />3.  모든 <xref:System.Windows.Forms.SizeType> 및 <xref:System.Windows.Forms.SizeType> 열 또는 행에 공간이 할당된 다음에는 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A>이 <xref:System.Windows.Forms.SizeType>로 설정된 모든 열이나 행이 나머지 공간을 비례적으로 할당하는 데 사용됩니다.|  
|`true`|<xref:System.Windows.Forms.SizeType> 열이나 행의 크기가 자동으로 조정된다는 점을 제외하면 위의 상호 작용과 비슷합니다.<br /><br /> <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 스타일이 <xref:System.Windows.Forms.SizeType>인 열이나 행에서 해당 내용이 잘리지 않도록 열이나 행을 확장하여 사용 가능한 공간을 만듭니다.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 <xref:System.Windows.Forms.ColumnStyle.Width%2A> 또는 <xref:System.Windows.Forms.RowStyle.Height%2A> 속성에 따라 새 공간을 비례적으로 할당합니다.|  
  
## 참고 항목  
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [TableLayoutPanel 컨트롤 개요](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)