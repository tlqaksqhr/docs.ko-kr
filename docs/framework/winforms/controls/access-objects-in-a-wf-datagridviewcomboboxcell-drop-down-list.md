---
title: "방법: Windows Forms DataGridViewComboBoxCell 드롭다운 목록의 개체 액세스 | Microsoft Docs"
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
  - "콤보 상자, DataGridViewComboBoxCell 드롭다운 목록의 개체 액세스"
  - "콤보 상자, DataGridView 컨트롤"
  - "DataGridView 컨트롤[Windows Forms], 콤보 상자 셀의 개체 액세스"
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: Windows Forms DataGridViewComboBoxCell 드롭다운 목록의 개체 액세스
<xref:System.Windows.Forms.DataGridViewComboBoxColumn> 및 <xref:System.Windows.Forms.DataGridViewComboBoxCell> 형식을 사용하면 <xref:System.Windows.Forms.ComboBox> 컨트롤과 마찬가지로 컨트롤의 드롭다운 목록에 임의의 개체를 추가할 수 있습니다.  이 기능을 사용하면 별도의 컬렉션에 상태를 나타내는 개체를 저장하지 않고도 드롭다운 목록에 복잡한 상태를 나타낼 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView> 형식에는 <xref:System.Windows.Forms.ComboBox> 컨트롤과 달리 현재 선택된 개체를 검색하기 위한 <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> 속성이 없습니다.  대신 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=fullName> 또는 <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=fullName> 속성을 비즈니스 개체의 속성 이름으로 설정해야 합니다.  사용자가 비즈니스 개체를 선택하면 해당 비즈니스 개체의 지정된 속성에 따라 셀의 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> 속성이 설정됩니다.  
  
 셀 값을 통해 비즈니스 개체를 검색하려면 `ValueMember` 속성에 비즈니스 개체 자체에 대한 참조를 반환하는 속성을 지정해야 합니다.  따라서 비즈니스 개체의 형식을 제어할 수 있는 권한이 없으면 상속을 통해 형식을 확장하여 이러한 속성을 추가해야 합니다.  
  
 다음 절차에서는 드롭다운 목록에 비즈니스 개체를 채우고 셀의 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> 속성을 통해 개체를 검색하는 방법을 보여 줍니다.  
  
### 드롭다운 목록에 비즈니스 개체를 추가하려면  
  
1.  새 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>을 만들고 해당 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> 컬렉션을 채웁니다.  또는 열의 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> 속성을 비즈니스 개체의 컬렉션으로 설정합니다.  그러나 이 경우 컬렉션에 드롭다운 목록에 "unassigned"를 추가하려면 해당 비즈니스 개체를 만들어야 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2.  <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> 및 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 속성을 설정합니다.  <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A>는 드롭다운 목록에 표시할 비즈니스 개체의 속성을 나타내고,  <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>는 비즈니스 개체에 대한 참조를 반환하는 속성을 나타냅니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3.  비즈니스 개체 형식에 현재 인스턴스에 대한 참조를 반환하는 속성이 들어 있는지 확인합니다.  이 속성의 이름은 이전 단계에서 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>에 지정된 값을 사용하여 지정해야 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### 현재 선택된 비즈니스 개체를 검색하려면  
  
-   셀의 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> 속성을 가져와서 비즈니스 개체 형식으로 캐스팅합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## 예제  
 전체 예제에서는 드롭다운 목록에 비즈니스 개체를 사용하는 방법을 보여 줍니다.  이 예제에서는 <xref:System.Windows.Forms.DataGridView> 컨트롤이 `Task` 개체의 컬렉션에 바인딩됩니다.  각 `Task` 개체에는 해당 작업에 현재 할당된 `Employee` 개체를 나타내는 `AssignedTo` 속성이 있습니다.  `Assigned To` 열에는 할당된 각 직원에 대한 `Name` 속성 값이 표시되거나, `Task.AssignedTo` 속성 값이 `null`인 경우 "unassigned"가 표시됩니다.  
  
 이 예제의 동작을 보려면 다음 단계를 수행하십시오.  
  
1.  드롭다운 목록에서 다른 값을 선택하고 콤보 상자 셀에서 Ctrl\+0을 눌러 `Assigned To` 열의 할당을 변경합니다.  
  
2.  `Generate Report`를 클릭하여 현재 할당을 표시합니다.  이렇게 하면 `Assigned To` 열의 변경 내용에 따라 `tasks` 컬렉션이 자동으로 업데이트됩니다.  
  
3.  `Request Status` 단추를 클릭하여 해당 행에 대한 현재 `Employee` 개체의 `RequestStatus` 메서드를 호출합니다.  이렇게 하면 선택된 개체가 성공적으로 검색됩니다.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System 및 System.Windows.Forms 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxCell>   
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ComboBox>   
 [Windows Forms DataGridView 컨트롤에서 데이터 표시](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)