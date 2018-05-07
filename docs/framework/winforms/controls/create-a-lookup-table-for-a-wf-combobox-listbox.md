---
title: '방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 조회 테이블 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
ms.openlocfilehash: 212cc229d8a496be11c84e30dbf3a0eedb952006
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 조회 테이블 만들기
경우에 따라 Windows Form에서는 친숙한 형식으로 데이터를 표시하지만 프로그램에서는 더 의미 있는 형식으로 데이터를 저장하는 데 유용합니다. 예를 들어 음식 주문 양식의 목록 상자에는 메뉴 항목이 이름별로 표시될 수 있습니다. 그러나 주문을 기록하는 데이터 테이블에는 음식을 나타내는 고유 ID 번호가 포함됩니다. 다음 표에서는 음식에 대한 주문 양식 데이터를 저장 및 표시하는 방법의 예를 보여 줍니다.  
  
### <a name="orderdetailstable"></a>OrderDetailsTable  
  
|OrderID|ItemID|Quantity|  
|-------------|------------|--------------|  
|4085|12|1|  
|4086|13|3|  
  
### <a name="itemtable"></a>ItemTable  
  
|ID|이름|  
|--------|----------|  
|12|Potato|  
|13|Chicken|  
  
 이 시나리오에서는 한 테이블 **OrderDetailsTable**, 표시 및 저장 고려 하는 실제 정보를 저장 합니다. 하지만 공간을 절약하기 위해 매우 복잡한 방식으로 작업이 수행됩니다. 또 하나의 테이블인 **ItemTable**, 모양 관련 정보만 포함 하는 ID에 대 한 번호 됩니다 하 고 실제 음식 주문에 대 한 nothing 어떤 음식 이름에 해당 합니다.  
  
 **ItemTable** 에 연결 되어는 <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, 또는 <xref:System.Windows.Forms.CheckedListBox> 세 가지 속성을 통해 제어 합니다. `DataSource` 속성이이 테이블의 이름을 포함 합니다. `DisplayMember` 속성 컨트롤 (음식 이름)에 표시할 해당 테이블의 데이터 열을 포함 합니다. `ValueMember` 속성은 저장 된 정보 (ID 번호) 해당 테이블의 데이터 열을 포함 합니다.  
  
 **OrderDetailsTable** 를 통해 액세스 하는 바인딩 컬렉션에 의해 컨트롤에 연결 된는 <xref:System.Windows.Forms.Control.DataBindings%2A> 속성입니다. 데이터 원본의 특정 데이터 멤버 (ID 번호 열)에 컨트롤 속성을 연결 하는 컬렉션에 바인딩 개체를 추가 하는 경우 (의 **OrderDetailsTable**). 컨트롤에서 항목을 선택하면 양식 입력이 이 테이블에 저장됩니다.  
  
### <a name="to-create-a-lookup-table"></a>조회 테이블을 만들려면  
  
1.  양식에 <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> 또는 <xref:System.Windows.Forms.CheckedListBox> 컨트롤을 추가합니다.  
  
2.  데이터 소스에 연결합니다.  
  
3.  두 테이블 간에 데이터 관계를 설정합니다. 참조 [DataRelation 개체 소개](http://msdn.microsoft.com/library/89d8a881-8265-41f2-a88b-61311ab06192)합니다.  
  
4.  다음 속성을 설정합니다. 코드 또는 디자이너에서 설정할 수 있습니다.  
  
    |속성|설정|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|어떤 ID 번호가 어떤 항목에 해당하는지에 대한 정보를 포함하는 테이블입니다. 이 이전 시나리오에서 `ItemTable`합니다.|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|컨트롤에 표시하려는 데이터 소스 테이블의 열입니다. 이 이전 시나리오에서 `"Name"` (코드를 설정 하려면 따옴표 사용).|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|저장된 정보를 포함하는 데이터 소스 테이블의 열입니다. 이 이전 시나리오에서 `"ID"` (코드를 설정 하려면 따옴표 사용).|  
  
5.  프로시저에서 <xref:System.Windows.Forms.ControlBindingsCollection> 클래스의 <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> 메서드를 호출하여 양식 입력을 기록하는 테이블에 컨트롤의 <xref:System.Windows.Forms.ListControl.SelectedValue%2A> 속성을 바인딩합니다. 수 또한 이렇게 하면 코드에서 지정 하는 대신 디자이너에서 컨트롤의에 액세스 하 여 <xref:System.Windows.Forms.Control.DataBindings%2A> 속성에는 **속성** 창. 이 이전 시나리오에서 `OrderDetailsTable`, 열은 `"ItemID"`합니다.  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 바인딩 및 Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [ListBox 컨트롤 개요](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)  
 [ComboBox 컨트롤 개요](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)  
 [CheckedListBox 컨트롤 개요](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)  
 [옵션 목록 표시에 사용된 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
