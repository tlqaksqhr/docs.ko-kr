---
title: "Windows Forms DataGridView 컨트롤의 열 형식 | Microsoft Docs"
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
  - "열[Windows Forms], 형식"
  - "데이터 표, 열"
  - "DataGridView 컨트롤[Windows Forms], 열 형식"
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Windows Forms DataGridView 컨트롤의 열 형식
<xref:System.Windows.Forms.DataGridView> 컨트롤은 여러 열 형식을 사용하여 해당 정보를 표시하고 사용자가 정보를 추가 또는 수정할 수 있게 해줍니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤을 바인딩하고 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> 속성을 `true`로 설정하면 바인딩된 데이터 소스에 포함된 데이터 형식에 적합한 기본 열 형식을 사용하여 열이 자동으로 생성됩니다.  
  
 또한 모든 열 클래스의 인스턴스를 사용자가 직접 만들 수 있으며 이 인스턴스를 <xref:System.Windows.Forms.DataGridView.Columns%2A> 속성에서 반환하는 컬렉션에 추가할 수 있습니다.  인스턴스를 만들어서 바인딩되지 않은 열로 사용할 수도 있고 이러한 인스턴스를 수동으로 바인딩할 수도 있습니다.  수동으로 바인딩된 열은 자동으로 생성된 형식 열을 다른 형식 열로 바꾸려는 경우에 유용합니다.  
  
 다음 표에서는 <xref:System.Windows.Forms.DataGridView> 컨트롤에 사용할 수 있는 다양한 열 클래스를 설명합니다.  
  
|클래스|설명|  
|---------|--------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|텍스트 기반 값과 함께 사용됩니다.  숫자 및 문자열에 바인딩할 때 자동으로 생성됩니다.|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|<xref:System.Boolean> 및 <xref:System.Windows.Forms.CheckState> 값과 함께 사용됩니다.  이러한 형식의 값에 바인딩할 때 자동으로 생성됩니다.|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|이미지를 표시하는 데 사용됩니다.  바이트 배열, <xref:System.Drawing.Image> 개체 또는 <xref:System.Drawing.Icon> 개체에 바인딩할 때 자동으로 생성됩니다.|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|셀에서 단추를 표시하는 데 사용됩니다.  바인딩할 때 자동으로 생성되지 않습니다.  일반적으로 바인딩되지 않은 열로 사용됩니다.|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|셀에서 드롭다운 목록을 표시하는 데 사용됩니다.  바인딩할 때 자동으로 생성되지 않습니다.  일반적으로 수동으로 데이터 바인딩됩니다.|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|셀에서 링크를 표시하는 데 사용됩니다.  바인딩할 때 자동으로 생성되지 않습니다.  일반적으로 수동으로 데이터 바인딩됩니다.|  
|사용자 지정 열 형식|<xref:System.Windows.Forms.DataGridViewColumn> 클래스 또는 이 클래스의 파생 클래스를 상속하여 고유한 열 클래스를 만들면 사용자 지정 모양, 동작 또는 호스팅된 컨트롤을 제공할 수 있습니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 동작 및 모양을 확장하여 셀과 열 사용자 지정](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)를 참조하십시오.|  
  
 이러한 열 형식은 다음 단원에서 자세하게 설명됩니다.  
  
## DataGridViewTextBoxColumn  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn>은 숫자 및 문자열과 같은 텍스트 기반 값에 사용되는 일반적인 목적의 열 형식입니다.  <xref:System.Windows.Forms.TextBox> 컨트롤은 편집 모드에서 활성 셀에 표시되며 사용자가 셀 값을 수정할 수 있게 합니다.  
  
 셀 값은 표시할 문자열로 자동 변환됩니다.  사용자가 입력 또는 수정한 값은 자동으로 구문 분석되어 해당 데이터 형식의 셀 값을 만듭니다.  이러한 변환은 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CellFormatting> 및 <xref:System.Windows.Forms.DataGridView.CellParsing> 이벤트를 처리하여 사용자 지정할 수 있습니다.  
  
 열의 셀 값 데이터 형식은 열의 <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A> 속성에 지정됩니다.  
  
## DataGridViewCheckBoxColumn  
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>은 <xref:System.Boolean> 및 <xref:System.Windows.Forms.CheckState> 값과 함께 사용됩니다.  <xref:System.Boolean> 값은 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> 속성 값에 따라 두 가지 상태 또는 세 가지 상태 확인란으로 표시됩니다.  열이 <xref:System.Windows.Forms.CheckState> 값에 바인딩되면 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> 속성의 기본값은 `true`입니다.  
  
 일반적으로 확인란 셀 값은 다른 데이터처럼 저장소용이거나 대량 작업을 수행하기 위한 것입니다.  사용자가 확인란 셀을 클릭할 때 바로 응답하려면 <xref:System.Windows.Forms.DataGridView.CellClick> 이벤트를 처리하면 되지만 이 이벤트는 셀 값이 업데이트되기 전에 발생합니다.  셀이 클릭될 때 새 값이 필요하면 현재 값을 기준으로 예상 값을 계산하거나  변경 사항을 바로 커밋하고 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 이벤트를 처리하여 이 이벤트에 응답합니다.  셀이 클릭될 때 변경 사항을 커밋하려면 <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged> 이벤트를 처리해야 합니다.  처리기에서 현재 셀이 확인란 셀이면 <xref:System.Windows.Forms.DataGridView.CommitEdit%2A> 메서드를 호출하여 <xref:System.Windows.Forms.DataGridViewDataErrorContexts> 값에 전달합니다.  
  
## DataGridViewImageColumn  
 <xref:System.Windows.Forms.DataGridViewImageColumn>은 이미지를 표시하는 데 사용됩니다.  이미지 열은 데이터 소스에서 자동으로 채우거나, 바인딩되지 않은 열에 대해 수동으로 채우거나, <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트의 처리기에서 동적으로 채울 수 있습니다.  
  
 데이터 소스에서 이미지 열을 자동으로 채우는 방법은 <xref:System.Drawing.Image> 클래스에서 지원하는 모든 형식 및 Microsoft® Access와 Northwind 샘플 데이터베이스에서 사용되는 OLE Picture 형식을 비롯하여 여러 이미지 형식으로 바이트 배열에 사용됩니다.  
  
 이미지 열을 수동으로 채우는 방법은 <xref:System.Windows.Forms.DataGridViewButtonColumn>의 기능을 사용자 지정된 모양으로 제공하려는 경우에 유용합니다.  <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=fullName> 이벤트를 처리하여 이미지 셀에서 클릭 시 응답할 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트의 처리기에서 이미지 열의 셀을 채우는 방법은 계산된 값이나 이미지가 아닌 형식의 값에 이미지를 제공하려는 경우에 유용합니다.  예를 들어, 아이콘으로 표시할 문자열 값으로 `"high"`, `"middle"` 및 `"low"`와 같은 문자열이 있는 "Risk" 열이 있을 수 있습니다.  또는 "Image" 열에 이미지의 이진 내용이 아니라 로드해야 하는 이미지 위치가 포함되어 있을 수 있습니다.  
  
## DataGridViewButtonColumn  
 <xref:System.Windows.Forms.DataGridViewButtonColumn>을 사용하여 단추가 포함된 셀의 열을 표시할 수 있습니다.  사용자가 특정 레코드에 대해 순서 지정 또는 별도의 창에 자식 레코드 표시와 같은 작업을 쉽게 수행하는 방법을 제공하려는 경우에 유용합니다.  
  
 단추 열은 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 바인딩할 때 자동으로 생성되지 않습니다.  단추 열을 사용하려면 수동으로 단추 열을 만든 다음 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=fullName> 속성에서 반환된 컬렉션에 추가해야 합니다.  
  
 <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=fullName> 이벤트를 처리하면 사용자가 단추 셀을 클릭하는 경우 응답이 이루어지도록 할 수 있습니다.  
  
## DataGridViewComboBoxColumn  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>을 사용하여 드롭다운 목록 상자가 포함된 셀의 열을 표시할 수 있습니다.  Northwind 샘플 데이터베이스에 있는 Products 테이블의 Category 열처럼 특정 값만 포함할 수 있는 필드에 데이터를 입력하는 경우에 유용합니다.  
  
 <xref:System.Windows.Forms.ComboBox> 드롭다운 목록을 채우는 방법과 동일한 방법 즉, <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> 속성에서 반환된 컬렉션을 통해 수동으로 또는 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> 및 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 속성을 통해 드롭다운 목록을 데이터 소스에 바인딩하여 모든 셀에 사용된 드롭다운 목록을 채울 수 있습니다.  자세한 내용은 [ComboBox 컨트롤](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md)을 참조하십시오.  
  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=fullName>의 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> 속성을 설정하여 실제 셀 값을 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 사용하는 데이터 소스에 바인딩할 수 있습니다.  
  
 콤보 상자 열은 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 바인딩할 때 자동으로 생성되지 않습니다.  콤보 상자 열을 사용하려면 수동으로 콤보 상자 열을 만든 다음 <xref:System.Windows.Forms.DataGridView.Columns%2A> 속성에서 반환된 컬렉션에 추가해야 합니다.  
  
## DataGridViewLinkColumn  
 <xref:System.Windows.Forms.DataGridViewLinkColumn>을 사용하면 하이퍼링크가 포함된 셀의 열을 표시할 수 있습니다.  이렇게 하면 데이터 소스에 URL 값이 있는 경우 또는 자식 레코드가 있는 창을 여는 동작처럼 특별한 동작에 대한 단추 열을 대체하려는 경우에 유용합니다.  
  
 링크 열은 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 바인딩할 때 자동으로 생성되지 않습니다.  링크 열을 사용하려면 수동으로 링크 열을 만든 다음 <xref:System.Windows.Forms.DataGridView.Columns%2A> 속성에서 반환된 컬렉션에 추가해야 합니다.  
  
 <xref:System.Windows.Forms.DataGridView.CellContentClick> 이벤트를 처리하면 사용자가 링크 클릭 시 응답할 수 있습니다.  이 이벤트는 사용자가 셀의 아무 곳이나 클릭했을 때 발생하는 <xref:System.Windows.Forms.DataGridView.CellClick> 및 <xref:System.Windows.Forms.DataGridView.CellMouseClick> 이벤트와 다릅니다.  
  
 <xref:System.Windows.Forms.DataGridViewLinkColumn> 클래스는 링크를 클릭하기 전, 클릭하는 동안, 그리고 클릭한 후의 링크 모양을 수정하기 위한 몇 가지 속성을 제공합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn>   
 <xref:System.Windows.Forms.DataGridViewButtonColumn>   
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>   
 <xref:System.Windows.Forms.DataGridViewImageColumn>   
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn>   
 <xref:System.Windows.Forms.DataGridViewLinkColumn>   
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [방법: Windows Forms DataGridView 컨트롤의 셀에 이미지 표시](../../../../docs/framework/winforms/controls/how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤에서 이미지 열 작업](../../../../docs/framework/winforms/controls/how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤 사용자 지정](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)