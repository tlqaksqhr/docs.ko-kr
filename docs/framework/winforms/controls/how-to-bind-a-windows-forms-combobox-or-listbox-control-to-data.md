---
title: "방법: 데이터에 Windows Forms ComboBox 또는 ListBox 컨트롤 바인딩 | Microsoft Docs"
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
  - "바인딩 컨트롤, 콤보 상자"
  - "콤보 상자, 데이터 바인딩"
  - "ComboBox 컨트롤[Windows Forms], 데이터 바인딩"
  - "데이터[Windows Forms], 컨트롤에 바인딩"
  - "데이터 바인딩, 콤보 상자"
  - "데이터 바인딩 컨트롤, Windows Forms"
  - "목록 상자, 데이터 바인딩"
  - "ListBox 컨트롤[Windows Forms], 데이터 바인딩"
  - "Windows Forms 컨트롤, 데이터 바인딩"
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 데이터에 Windows Forms ComboBox 또는 ListBox 컨트롤 바인딩
<xref:System.Windows.Forms.ComboBox> 및 <xref:System.Windows.Forms.ListBox>를 바인딩하여 데이터베이스에서 데이터를 찾거나 새 데이터를 입력하거나 기존 데이터를 편집하는 등의 작업을 수행할 수 있습니다.  
  
### ComboBox 또는 ListBox 컨트롤을 바인딩하려면  
  
1.  `DataSource` 속성을 데이터 소스 개체로 설정합니다.  가능한 데이터 소스에는 데이터에 바인딩된 <xref:System.Windows.Forms.BindingSource>, 데이터 테이블, 데이터 뷰, 데이터 집합, 데이터 뷰 관리자, 배열 또는 <xref:System.Collections.IList> 인터페이스를 구현하는 모든 클래스 등이 있습니다.  자세한 내용은 [Windows Forms에서 지원하는 데이터 소스](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)를 참조하십시오.  
  
2.  테이블에 바인딩하는 경우에는`DisplayMember` 속성을 데이터 소스에 있는 열 이름으로 설정합니다.  
  
     \-또는\-  
  
     <xref:System.Collections.IList>에 바인딩하는 경우에는 표시 번호를 목록에 있는 형식의 공용 속성으로 설정합니다.  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
  
    ```  
  
    > [!NOTE]
    >  사용자가 <xref:System.Collections.ArrayList>와 같은 <xref:System.ComponentModel.IBindingList> 인터페이스를 구현하지 않는 데이터 소스에 바인딩한 경우 데이터 소스가 업데이트되더라도 바인딩된 컨트롤의 데이터는 업데이트되지 않습니다.  즉, <xref:System.Collections.ArrayList>에 바인딩된 콤보 상자가 있고 데이터가 <xref:System.Collections.ArrayList>에 추가되는 경우 이러한 새 항목은 콤보 상자에 표시되지 않습니다.  그러나 컨트롤이 바인딩되는 <xref:System.Windows.Forms.BindingContext> 클래스의 인스턴스에서 <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> 및 <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> 메서드를 호출하여 콤보 상자를 강제로 업데이트할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 [Windows Forms 데이터 바인딩](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [데이터 바인딩 및 Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [옵션 목록 표시에 사용하는 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)