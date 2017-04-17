---
title: "방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 조회 테이블 만들기 | Microsoft Docs"
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
  - "CheckedListBox 컨트롤[Windows Forms], 조회 테이블 만들기"
  - "콤보 상자, 조회 테이블"
  - "ComboBox 컨트롤[Windows Forms], 조회 테이블"
  - "목록 상자, 조회 테이블"
  - "ListBox 컨트롤[Windows Forms], 조회 테이블 만들기"
  - "ListBox 컨트롤[Windows Forms], 조회 테이블"
  - "조회 테이블"
  - "조회 테이블, 컨트롤 만들기"
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 조회 테이블 만들기
경우에 따라 Windows Form에서는 친숙한 형식으로 데이터를 표시하지만 프로그램에서는 더 의미 있는 형식으로 데이터를 저장하는 데 유용합니다.  예를 들어 음식 주문 양식의 목록 상자에는 메뉴 항목이 이름별로 표시될 수 있습니다.  그러나 주문을 기록하는 데이터 테이블에는 음식을 나타내는 고유 ID 번호가 포함됩니다.  다음 표에서는 음식에 대한 주문 양식 데이터를 저장 및 표시하는 방법의 예를 보여 줍니다.  
  
### OrderDetailsTable  
  
|OrderID|ItemID|Quantity|  
|-------------|------------|--------------|  
|4085|12|1|  
|4086|13|3|  
  
### ItemTable  
  
|ID|이름|  
|--------|--------|  
|12|Potato|  
|13|Chicken|  
  
 이 시나리오에서 OrderDetailsTable 테이블에는 표시 및 저장과 관련된 실제 정보가 저장됩니다.  하지만 공간을 절약하기 위해 매우 복잡한 방식으로 작업이 수행됩니다.  다른 테이블인 ItemTable에는 어떤 ID 번호가 어떤 음식 이름에 해당하는지에 대한 모양 관련 정보만 포함되고 실제 음식 주문에 대한 정보는 포함되지 않습니다.  
  
 ItemTable은 세 가지 속성을 통해 <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> 또는 <xref:System.Windows.Forms.CheckedListBox> 컨트롤에 연결됩니다.   `DataSource`  속성은 테이블 이름을 포함합니다.   `DisplayMember` 속성은 컨트롤\(음식 이름\)에 표시할 해당 테이블의 데이터 열을 포함합니다.   `ValueMember`  속성은 저장된 정보\(ID 번호\)가 포함된 해당 테이블의 데이터 열을 포함합니다.  
  
 OrderDetailsTable은 <xref:System.Windows.Forms.Control.DataBindings%2A> 속성을 통해 액세스하는 바인딩 컬렉션에 의해 컨트롤에 연결됩니다.  컬렉션에 바인딩 개체를 추가하면 데이터 소스\(OrderDetailsTable\)에서 특정 데이터 멤버\(ID 번호 열\)에 컨트롤 속성을 연결합니다.  컨트롤에서 항목을 선택하면 양식 입력이 이 테이블에 저장됩니다.  
  
### 조회 테이블을 만들려면  
  
1.  양식에 <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> 또는 <xref:System.Windows.Forms.CheckedListBox> 컨트롤을 추가합니다.  
  
2.  데이터 소스에 연결합니다.  
  
3.  두 테이블 간에 데이터 관계를 설정합니다.  [DataRelation 개체 소개](../Topic/Introduction%20to%20DataRelation%20Objects.md)를 참조하세요.  
  
4.  다음 속성을 설정합니다.  코드 또는 디자이너에서 설정할 수 있습니다.  
  
    |속성|설정|  
    |--------|--------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|어떤 ID 번호가 어떤 항목에 해당하는지에 대한 정보를 포함하는 테이블입니다.  이전 시나리오에서는  `ItemTable`입니다.|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|컨트롤에 표시하려는 데이터 소스 테이블의 열입니다.  이전 시나리오에서는  `"Name"` 입니다\(코드에서 설정하려면 따옴표 사용\).|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|저장된 정보를 포함하는 데이터 소스 테이블의 열입니다.  이전 시나리오에서는  `"ID"` 입니다\(코드에서 설정하려면 따옴표 사용\).|  
  
5.  프로시저에서 <xref:System.Windows.Forms.ControlBindingsCollection> 클래스의 <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> 메서드를 호출하여 양식 입력을 기록하는 테이블에 컨트롤의 <xref:System.Windows.Forms.ListControl.SelectedValue%2A> 속성을 바인딩합니다.  코드가 아니라 디자이너의 **속성** 창에서 컨트롤의 <xref:System.Windows.Forms.Control.DataBindings%2A> 속성에 액세스하여 이 작업을 수행할 수도 있습니다.  이전 시나리오에서는  `OrderDetailsTable`이고 열은  `"ItemID"`입니다.  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
  
    ```  
  
## 참고 항목  
 [데이터 바인딩 및 Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [ListBox 컨트롤 개요](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)   
 [ComboBox 컨트롤 개요](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)   
 [CheckedListBox 컨트롤 개요](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)   
 [옵션 목록 표시에 사용하는 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)