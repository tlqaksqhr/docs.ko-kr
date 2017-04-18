---
title: "방법: Windows Forms TabControl의 모양 변경 | Microsoft Docs"
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
  - "단추, 탭 표시"
  - "아이콘, 탭에 표시"
  - "TabControl 컨트롤[Windows Forms], 페이지 모양 변경"
  - "탭, 모양 제어"
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: Windows Forms TabControl의 모양 변경
Windows Forms의 탭 모양은 <xref:System.Windows.Forms.TabControl> 개체의 속성과 컨트롤의 개별 탭을 구성하는 <xref:System.Windows.Forms.TabPage> 개체의 속성을 사용하여 변경할 수 있습니다.  이러한 속성을 설정하면 탭에 이미지를 표시하고, 가로 대신 세로로 탭을 표시하고, 탭을 여러 행으로 표시하고, 프로그래밍 방식으로 탭을 활성화하거나 비활성화할 수 있습니다.  
  
### 탭의 레이블 부분에 아이콘을 표시하려면  
  
1.  폼에 <xref:System.Windows.Forms.ImageList> 컨트롤을 추가합니다.  
  
2.  이미지 목록에 이미지를 추가합니다.  
  
     이미지 목록에 대한 자세한 내용은 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) 및 [방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)를 참조하십시오.  
  
3.  <xref:System.Windows.Forms.TabControl>의 <xref:System.Windows.Forms.TabControl.ImageList%2A> 속성을 <xref:System.Windows.Forms.ImageList> 컨트롤로 설정합니다.  
  
4.  <xref:System.Windows.Forms.TabPage>의 <xref:System.Windows.Forms.TabPage.ImageIndex%2A> 속성을 목록에서 적절한 이미지의 인덱스로 설정합니다.  
  
### 여러 행의 탭을 만들려면  
  
1.  원하는 개수만큼 탭 페이지를 추가합니다.  
  
2.  <xref:System.Windows.Forms.TabControl>의 <xref:System.Windows.Forms.TabControl.Multiline%2A> 속성을 `true`로 설정합니다.  
  
3.  탭이 여러 행으로 나타나지 않으면 <xref:System.Windows.Forms.TabControl>의 <xref:System.Windows.Forms.Control.Width%2A> 속성을 모든 탭의 너비보다 좁게 설정합니다.  
  
### 탭을 컨트롤의 측면에 정렬하려면  
  
-   <xref:System.Windows.Forms.TabControl>의 <xref:System.Windows.Forms.TabControl.Alignment%2A> 속성을 <xref:System.Windows.Forms.TabAlignment> 또는 <xref:System.Windows.Forms.TabAlignment>로 설정합니다.  
  
### 탭의 모든 컨트롤을 프로그래밍 방식으로 활성화하거나 비활성화하려면  
  
1.  <xref:System.Windows.Forms.TabPage>의 <xref:System.Windows.Forms.TabPage.Enabled%2A> 속성을 `true` 또는 `false`로 설정합니다.  
  
    ```vb  
    TabPage1.Enabled = False  
  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### 탭을 단추로 표시하려면  
  
-   <xref:System.Windows.Forms.TabControl>의 <xref:System.Windows.Forms.TabControl.Appearance%2A> 속성을 <xref:System.Windows.Forms.TabAppearance> 또는 <xref:System.Windows.Forms.TabAppearance>로 설정합니다.  
  
## 참고 항목  
 [TabControl 컨트롤](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)   
 [TabControl 컨트롤 개요](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)   
 [방법: 탭 페이지에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)   
 [방법: 탭 페이지 사용 안 함](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)   
 [방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)