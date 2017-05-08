---
title: "Windows Forms DataGridView 컨트롤에서 새 레코드에 행 사용 | Microsoft Docs"
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
  - "DataGridView 컨트롤[Windows Forms], 새 레코드의 행 추가"
  - "DataGridView 컨트롤[Windows Forms], 데이터 입력"
  - "행, 새 레코드"
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Windows Forms DataGridView 컨트롤에서 새 레코드에 행 사용
<xref:System.Windows.Forms.DataGridView>를 사용하여 응용 프로그램에서 데이터를 편집하는 경우 사용자에게 새 데이터 행을 데이터 저장소에 추가하는 기능을 제공할 수 있습니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤은 새 레코드에 행을 제공하여 이 기능을 지원합니다. 이 행은 항상 마지막 행으로 표시되며  행 머리글에 별표\(\*\)가 표시됩니다.  다음 단원에서는 새 레코드에 대한 행으로 프로그래밍할 때 고려할 몇 가지 사항에 대해 설명합니다.  
  
## 새 레코드에 대한 행 표시  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 속성을 사용하여 새 레코드에 대한 행을 표시할지 여부를 나타냅니다.  이 속성의 기본값은 `true`입니다.  
  
 데이터 바인딩의 경우 컨트롤의 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 속성과 데이터 소스의 <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=fullName> 속성이 모두 `true`이면 새 레코드에 대한 행이 표시됩니다.  두 속성 중 하나가 `false`이면 이 행이 표시되지 않습니다.  
  
## 기본 데이터로 새 레코드에 대한 행 채우기  
 사용자가 새 레코드에 대한 행을 현재 행으로 선택하면 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 이벤트를 발생시킵니다.  
  
 이 이벤트는 새 <xref:System.Windows.Forms.DataGridViewRow>에 대한 액세스를 제공하고 새 행을 기본 데이터로 채울 수 있게 해줍니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 새 행에 기본값 지정](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)를 참조하십시오.  
  
## 행 컬렉션  
 새 레코드에 대한 행은 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션에 포함되지만 다음과 같은 두 가지 점에서 다르게 동작합니다.  
  
-   <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션에서 새 레코드에 대한 행을 프로그래밍 방식으로 제거할 수 없습니다.  이를 시도하면 <xref:System.InvalidOperationException>이 throw됩니다.  사용자 또한 새 레코드에 대한 행을 삭제할 수 없습니다.  <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=fullName> 메서드는 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션에서 이 행을 제거하지 않습니다.  
  
-   새 레코드에 대한 행 뒤에는 행을 추가할 수 없습니다.  이를 시도하면 <xref:System.InvalidOperationException>이 발생합니다.  따라서 새 레코드에 대한 행은 항상 <xref:System.Windows.Forms.DataGridView> 컨트롤의 마지막 행이 됩니다.  행을 추가하는 <xref:System.Windows.Forms.DataGridViewRowCollection>의 모든 메서드\(<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A> 및 <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>\)는 새 레코드에 대한 행이 표시되면 삽입 메서드를 내부적으로 호출합니다.  
  
## 새 레코드에 대한 행을 시각적으로 사용자 지정  
 새 레코드에 대한 행을 만드는 경우 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 속성에 지정된 행을 기반으로 합니다.  이 행에 지정되지 않은 셀 스타일은 다른 속성에서 상속됩니다.  셀 스타일 상속에 대한 자세한 내용은 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
 새 레코드에 대한 행의 셀에 표시되는 초기 값은 각 셀의 <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> 속성에서 검색됩니다.  <xref:System.Windows.Forms.DataGridViewImageCell> 형식의 셀인 경우 이 속성은 자리 표시자 이미지를 반환하고,  그렇지 않은 경우 `null`을 반환합니다.  사용자 지정 값을 반환하도록 이 속성을 재정의할 수 있습니다.  그러나 이러한 초기 값은 포커스가 새 레코드에 대한 행을 입력할 때 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 이벤트 처리기로 바꿀 수 있습니다.  
  
 이 행의 머리글에 대한 표준 아이콘\(화살표 또는 별표\)은 공개적으로 노출되지 않습니다.  아이콘을 사용자 지정하려면 사용자 지정 <xref:System.Windows.Forms.DataGridViewRowHeaderCell> 클래스를 만들어야 합니다.  
  
 표준 아이콘은 행 머리글 셀에 사용되는 <xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> 속성을 사용합니다.  표준 아이콘은 공간이 부족하여 전체를 표시할 수 없는 경우 렌더링되지 않습니다.  
  
 행 머리글 셀에 문자열 값 집합이 있고 텍스트 및 아이콘을 표시할 공간이 부족한 경우 아이콘이 먼저 삭제됩니다.  
  
## 정렬  
 바인딩되지 않은 모드에서는 사용자가 <xref:System.Windows.Forms.DataGridView>의 내용을 정렬했더라도 새 레코드는 항상 <xref:System.Windows.Forms.DataGridView>의 끝에 추가됩니다.  행을 올바른 위치에 정렬하려면 정렬을 다시 적용해야 합니다. 이 동작은 <xref:System.Windows.Forms.ListView> 컨트롤의 동작과 비슷합니다.  
  
 데이터 바인딩된 모드 및 가상 모드에서는 정렬이 적용될 때의 삽입 동작이 데이터 모델의 구현에 따라 달라집니다.  [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]의 경우 행이 올바른 위치에 즉시 정렬됩니다.  
  
## 새 레코드에 대한 행의 기타 참고 사항  
 이 행의 <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> 속성은 `false`로 설정할 수 없습니다.  이를 시도하면 <xref:System.InvalidOperationException>이 발생합니다.  
  
 새 레코드에 대한 행은 항상 선택되지 않은 상태로 만들어집니다.  
  
## 가상 모드  
 가상 모드를 구현하는 경우 데이터 모델에 새 레코드에 대한 행이 필요한 시기와 행 추가를 롤백할 시기를 추적해야 합니다.  이 기능의 정확한 구현은 데이터 모델 구현 및 해당 트랜잭션 의미\(예: 커밋 범위가 셀 수준인지 행 수준인지 여부\)에 따라 달라집니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤의 가상 모드](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤의 데이터 입력](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤에서 새 행에 기본값 지정](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)