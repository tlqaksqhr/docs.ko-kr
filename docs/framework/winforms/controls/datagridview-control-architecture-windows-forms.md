---
title: "DataGridView 컨트롤 아키텍처(Windows Forms) | Microsoft Docs"
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
  - "DataGridView 컨트롤[Windows Forms], 아키텍처"
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# DataGridView 컨트롤 아키텍처(Windows Forms)
<xref:System.Windows.Forms.DataGridView> 컨트롤과 이 컨트롤의 관련 클래스는 표 형식 데이터를 표시하고 편집하기 위한 융통성 있고 확장 가능한 시스템으로 디자인되었습니다.  이러한 클래스는 모두 <xref:System.Windows.Forms?displayProperty=fullName> 네임스페이스에 포함되며 "DataGridView"라는 접두사가 클래스의 이름에 포함됩니다.  
  
## 아키텍처 요소  
 기본 <xref:System.Windows.Forms.DataGridView> 동반 클래스는 <xref:System.Windows.Forms.DataGridViewElement>에서 파생됩니다.  다음 개체 모델은 <xref:System.Windows.Forms.DataGridViewElement> 상속 계층 구조를 보여 줍니다.  
  
 ![DataGridViewElement 개체 모델](../../../../docs/framework/winforms/controls/media/datagridviewelement.png "DataGridViewElement")  
DataGridViewElement 개체 모델  
  
 <xref:System.Windows.Forms.DataGridViewElement> 클래스는 부모 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조를 제공하며, <xref:System.Windows.Forms.DataGridViewElementStates> 열거형의 값 조합을 나타내는 값이 포함된 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 속성을 갖습니다.  
  
 다음 단원에서는 <xref:System.Windows.Forms.DataGridView> 동반 클래스에 대해 자세히 설명합니다.  
  
### DataGridViewElementStates  
 <xref:System.Windows.Forms.DataGridViewElementStates> 열거형은 다음과 같은 값을 포함합니다.  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
 이 열거형의 값은 비트 논리 연산자와 결합될 수 있기 때문에 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 속성은 여러 상태를 한 번에 표시할 수 있습니다.  예를 들어, <xref:System.Windows.Forms.DataGridViewElement>는 동시에 <xref:System.Windows.Forms.DataGridViewElementStates>, <xref:System.Windows.Forms.DataGridViewElementStates> 및 <xref:System.Windows.Forms.DataGridViewElementStates>이 될 수 있습니다.  
  
### 셀 및 밴드  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 셀과 밴드라는 기본적인 두 종류의 개체로 구성됩니다.  모든 셀은 <xref:System.Windows.Forms.DataGridViewCell> 기본 클래스에서 파생됩니다.  <xref:System.Windows.Forms.DataGridViewColumn> 및 <xref:System.Windows.Forms.DataGridViewRow>라는 두 종류의 밴드는 모두 <xref:System.Windows.Forms.DataGridViewBand> 기본 클래스에서 파생됩니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 여러 클래스와 상호 운용되지만, 그 중에서도 <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn> 및 <xref:System.Windows.Forms.DataGridViewRow>와 함께 가장 많이 사용됩니다.  
  
### DataGridViewCell  
 셀은 <xref:System.Windows.Forms.DataGridView>의 상호 작용에 사용되는 기본 단위입니다.  셀을 중심으로 표시 작업이 수행되고 주로 셀을 통해 데이터 입력이 수행됩니다.  <xref:System.Windows.Forms.DataGridViewRow> 클래스의 <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> 컬렉션을 사용하여 셀에 액세스할 수 있으며, <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 컬렉션을 사용하여 선택한 셀에 액세스할 수 있습니다.  다음 개체 모델은 이 사용 방법을 보여 주고 <xref:System.Windows.Forms.DataGridViewCell> 상속 계층 구조를 보여 줍니다.  
  
 ![DataGridViewCell 개체 모델](../../../../docs/framework/winforms/controls/media/datagridviewcell.png "DataGridViewCell")  
DataGridViewCell 개체 모델  
  
 <xref:System.Windows.Forms.DataGridViewCell> 형식은 모든 셀 형식이 파생되는 추상 기본 클래스입니다.  <xref:System.Windows.Forms.DataGridViewCell>과 해당 파생 형식은 Windows Forms 컨트롤이 아니지만 그 중 일부는 Windows Forms 컨트롤을 호스팅합니다.  셀에서 지원되는 모든 편집 기능은 일반적으로 호스팅된 컨트롤에서 처리됩니다.  
  
 <xref:System.Windows.Forms.DataGridViewCell> 개체는 고유 모양 및 그리기 기능을 Windows Forms 컨트롤과 똑같은 방법으로 제어하지 않습니다.  대신 <xref:System.Windows.Forms.DataGridView>가 해당 <xref:System.Windows.Forms.DataGridViewCell> 개체의 모양을 처리합니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤의 속성 및 이벤트와의 상호 작용을 통해 셀의 모양과 동작에 상당한 영향을 줄 수 있습니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤 기능 이상의 특별한 사용자 지정 작업이 필요한 경우에는 <xref:System.Windows.Forms.DataGridViewCell> 또는 그 자식 클래스에서 파생되는 고유 클래스를 구현할 수 있습니다.  
  
 다음 목록에서는 <xref:System.Windows.Forms.DataGridViewCell>에서 파생된 클래스를 보여 줍니다.  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewImageCell>  
  
-   <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
-   사용자 지정 셀 형식  
  
### DataGridViewColumn  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에 연결된 데이터 저장소의 스키마는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 열에 표시됩니다.  <xref:System.Windows.Forms.DataGridView.Columns%2A> 컬렉션을 사용하여 <xref:System.Windows.Forms.DataGridView> 컨트롤의 열에 액세스할 수 있습니다.  <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 컬렉션을 사용하여 선택한 열에 액세스할 수 있습니다.  다음 개체 모델은 이 사용 방법을 보여 주고 <xref:System.Windows.Forms.DataGridViewColumn> 상속 계층 구조를 보여 줍니다.  
  
 ![DataGridViewColumn 개체 모델](../../../../docs/framework/winforms/controls/media/datagridviewcolumn.png "DataGridViewColumn")  
DataGridViewColumn 개체 모델  
  
 주요 셀 형식 중 일부는 해당 열 형식을 갖습니다.  이러한 형식은 <xref:System.Windows.Forms.DataGridViewColumn> 기본 클래스에서 파생됩니다.  
  
 다음 목록에서는 <xref:System.Windows.Forms.DataGridViewColumn>에서 파생된 클래스를 보여 줍니다.  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   사용자 지정 열 형식  
  
### DataGridView 편집 컨트롤  
 고급 편집 기능을 지원하는 셀은 일반적으로 Windows Forms 컨트롤에서 파생되는 호스팅된 컨트롤을 사용합니다.  또한 이러한 컨트롤은 <xref:System.Windows.Forms.IDataGridViewEditingControl> 인터페이스를 구현합니다.  다음 개체 모델은 이러한 컨트롤의 사용 방법을 보여 줍니다.  
  
 ![DataGridView 편집 컨트롤 개체 모델](../../../../docs/framework/winforms/controls/media/datagridviewediting.png "DataGridViewEditing")  
DataGridView 편집 컨트롤 개체 모델  
  
 다음과 같은 편집 컨트롤이 <xref:System.Windows.Forms.DataGridView> 컨트롤과 함께 제공됩니다.  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 고유한 편집 컨트롤을 만드는 방법에 대한 자세한 내용은 [방법: Windows Forms DataGridView 셀에서 컨트롤 호스팅](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)을 참조하십시오.  
  
 다음 표에서는 셀 형식, 열 형식 및 편집 컨트롤 간의 관계를 보여 줍니다.  
  
|셀 형식|호스팅되는 컨트롤|열 형식|  
|----------|---------------|----------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|n\/a|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|n\/a|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|n\/a|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|n\/a|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### DataGridViewRow  
 <xref:System.Windows.Forms.DataGridViewRow> 클래스는 <xref:System.Windows.Forms.DataGridView> 컨트롤이 연결된 데이터 저장소에 있는 레코드의 데이터 필드를 표시합니다.  <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션을 사용하여 <xref:System.Windows.Forms.DataGridView> 컨트롤의 행에 액세스할 수 있습니다.  <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 컬렉션을 사용하여 선택한 행에 액세스할 수 있습니다.  다음 개체 모델은 이 사용 방법을 보여 주고 <xref:System.Windows.Forms.DataGridViewRow> 상속 계층 구조를 보여 줍니다.  
  
 ![DataGridViewRow 개체 모델](../../../../docs/framework/winforms/controls/media/datagridviewrow.png "DataGridViewRow")  
DataGridViewRow 개체 모델  
  
 일반적으로 필요한 경우는 아니지만 <xref:System.Windows.Forms.DataGridViewRow> 클래스에서 고유한 형식을 파생시킬 수 있습니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤에는 해당 <xref:System.Windows.Forms.DataGridViewRow> 개체의 동작을 사용자 지정하는 데 사용되는 여러 가지 행 관련 이벤트와 속성이 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 속성을 활성화하면 새 행을 추가할 수 있는 특수 행이 마지막 행으로 표시됩니다.  이 행은 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션의 일부이지만 특수 기능을 가지므로 주의가 필요합니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤에서 새 레코드에 행 사용](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
## 참고 항목  
 [DataGridView 컨트롤 개요](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)   
 [Windows Forms DataGridView 컨트롤 사용자 지정](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤에서 새 레코드에 행 사용](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)