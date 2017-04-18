---
title: "방법: 디자이너를 사용하여 형식에 Windows Forms 컨트롤 바인딩 | Microsoft Docs"
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
  - "BindingSource 구성 요소[Windows Forms], 형식에 바인딩"
  - "컨트롤[Windows Forms], 형식에 바인딩"
  - "형식[Windows Forms], 컨트롤 바인딩"
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 디자이너를 사용하여 형식에 Windows Forms 컨트롤 바인딩
데이터와 상호 작용하는 컨트롤을 작성할 때 개체 대신 형식에 컨트롤을 바인딩해야 하는 경우가 있습니다.  일반적으로 디자인 타임에 컨트롤을 형식에 바인딩해야 하는데, 이때는 데이터가 사용 가능하지 못할 수도 있지만 데이터 바인딩된 컨트롤이 형식의 공용 인터페이스에서 데이터를 표시하도록 하려는 경우가 있습니다.  다음 절차에서는 형식에 바인딩된 새 <xref:System.Windows.Forms.BindingSource>를 만든 다음 형식의 속성 중 하나를 <xref:System.Windows.Forms.TextBox>의 <xref:System.Windows.Forms.TextBox.Text%2A> 속성에 바인딩하는 방법을 보여 줍니다.  
  
### BindingSource를 형식에 바인딩하려면  
  
1.  Windows Forms 프로젝트를 만듭니다.  
  
     자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하십시오.  
  
2.  **디자인** 뷰에서 <xref:System.Windows.Forms.BindingSource> 구성 요소를 끌어서 폼에 놓습니다.  
  
3.  **속성** 창에서 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 속성에 대한 화살표를 클릭합니다.  
  
4.  **DataSource UI 형식 편집기**에서 **프로젝트 데이터 소스 추가**를 클릭합니다.  
  
5.  **데이터 소스 형식 선택** 페이지에서 **개체**를 선택하고 **다음**을 클릭합니다.  
  
6.  바인딩할 형식을 선택합니다.  
  
    -   바인딩할 형식이 현재 프로젝트에 있거나 해당 형식을 포함한 어셈블리가 이미 참조로 추가된 경우에는 노드를 확장하여 형식을 찾아서 선택합니다.  
  
         또는  
  
    -   바인딩할 형식이 다른 어셈블리에 있고 참조 목록에 포함되어 있지 않는 경우에는 **참조 추가**를 클릭한 다음 **프로젝트** 탭을 클릭합니다.  원하는 비즈니스 개체가 들어 있는 프로젝트를 선택한 다음 **확인**을 클릭합니다.  이 프로젝트는 어셈블리 목록에 표시되므로 노드를 확장하여 원하는 형식을 찾아서 선택할 수 있습니다.  
  
        > [!NOTE]
        >  프레임워크 또는 Microsoft 어셈블리에 있는 형식에 바인딩하려면 **Microsoft 또는 System으로 시작되는 어셈블리 숨기기** 확인란 선택을 취소합니다.  
  
7.  **다음**을 클릭하고 **마침**을 클릭합니다.  
  
### 컨트롤을 BindingSource에 바인딩하려면  
  
1.  <xref:System.Windows.Forms.TextBox>을 폼에 추가합니다.  
  
2.  **속성** 창에서 **\(DataBindings\)** 노드를 확장합니다.  
  
3.  <xref:System.Windows.Forms.TextBox.Text%2A> 속성 옆의 화살표를 클릭합니다.  
  
4.  **DataSource UI 형식 편집기**에서 이전에 추가된 <xref:System.Windows.Forms.BindingSource> 노드를 확장한 다음 <xref:System.Windows.Forms.TextBox>의 <xref:System.Windows.Forms.TextBox.Text%2A> 속성에 바인딩할 바인딩된 형식의 속성을 선택합니다.  
  
## 참고 항목  
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [방법: 형식에 Windows Forms 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../Topic/Bind%20controls%20to%20data%20in%20Visual%20Studio.md)