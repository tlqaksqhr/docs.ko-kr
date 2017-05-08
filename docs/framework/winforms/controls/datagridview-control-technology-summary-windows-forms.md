---
title: "DataGridView 컨트롤 기술 요약(Windows Forms) | Microsoft Docs"
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
  - "데이터 표, 데이터 표 정보"
  - "DataGridView 컨트롤[Windows Forms], DataGridView 컨트롤 정보"
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# DataGridView 컨트롤 기술 요약(Windows Forms)
이 항목에서는 `DataGridView` 컨트롤에 대한 정보와 이 컨트롤을 사용할 수 있도록 지원하는 클래스에 대한 정보를 요약하여 설명합니다.  
  
 데이터를 표 형식으로 표시해야 하는 경우가 많이 있습니다.  `DataGridView` 컨트롤은 데이터를 표로 나타내는 데 필요한 모든 기능을 갖춘 솔루션입니다.  
  
## Keywords  
 DataGridView, BindingSource, 테이블, 셀, 데이터 바인딩, 가상 모드  
  
## 네임스페이스  
 <xref:System.Windows.Forms?displayProperty=fullName>  
  
 <xref:System.Data?displayProperty=fullName>  
  
## 관련 기술  
 `BindingSource`  
  
## Background  
 UI\(사용자 인터페이스\) 디자이너에서는 표 형식 데이터를 사용자에게 표시해야 하는 경우가 자주 있습니다.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서 데이터를 테이블이나 표로 나타내는 방법은 여러 가지가 있습니다.  `DataGridView` 컨트롤은 Windows Forms 응용 프로그램에 이 기술을 적용할 수 있도록 설계된 최신 컨트롤입니다.  
  
 `DataGridView` 컨트롤은 데이터 저장소의 데이터 행을 표시할 수 있습니다.  많은 형식의 데이터 저장소가 지원됩니다.  데이터 저장소에는 1차원 배열과 같이 간단하고 형식화되지 않은 데이터나 <xref:System.Data.DataSet>과 같은 형식화된 데이터를 저장할 수 있습니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
 `DataGridView` 컨트롤에서는 데이터를 표 형식으로 표시하는 강력하고 유연한 방법을 제공합니다.  이 컨트롤을 사용하면 적은 양의 데이터뿐만 아니라 매우 큰 데이터 집합의 읽기 전용 또는 편집 가능 뷰를 표시할 수 있습니다.  
  
 `DataGridView` 컨트롤을 여러 가지 방식으로 확장하여 응용 프로그램에 사용자 지정 동작을 만들 수 있습니다.  예를 들어, 고유한 정렬 알고리즘을 프로그래밍 방식으로 지정하고 고유한 형식의 셀을 만들 수 있습니다.  여러 속성을 선택하여 `DataGridView` 컨트롤의 모양을 손쉽게 사용자 지정할 수 있습니다.  `DataGridView` 컨트롤은 다양한 형식의 데이터 저장소를 데이터 소스로 사용할 수 있을 뿐만 아니라 바인딩된 데이터 소스 없이도 작동할 수 있습니다.  
  
## DataGridView 클래스 구현  
 여러 가지 방법으로 `DataGridView` 컨트롤의 확장 기능을 사용할 수 있습니다.  이벤트와 속성을 통해 컨트롤의 많은 기능을 사용자 지정할 수 있지만 일부 사용자 지정을 수행하기 위해서는 기존 `DataGridView` 클래스에서 파생된 새 클래스를 만들어야 합니다.  
  
 가장 일반적으로 사용되는 기본 클래스는 `DataGridViewCell` 및 `DataGridViewColumn`입니다.  `DataGridViewCell` 또는 그 자식 클래스에서 고유한 셀 클래스를 파생시킬 수 있습니다.  열에 모든 셀 형식을 추가할 수 있지만 대개는 기본적으로 사용자 지정 셀 형식의 셀을 호스팅하는 `DataGridViewColumn`에서 동반 열 클래스를 파생시킵니다.  
  
 파생된 셀 클래스에서 `IDataGridViewEditingCell` 인터페이스를 구현하여 편집 기능을 가진 셀 형식을 만들 수 있습니다. 그러나 이 셀 형식은 편집 모드에서 컨트롤을 호스팅하지 않습니다.  편집 모드에서 셀을 호스팅할 수 있는 컨트롤을 만들려면 <xref:System.Windows.Forms.Control>에서 파생된 클래스에서 `IDataGridViewEditingControl` 인터페이스를 구현합니다.  
  
 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 동작 및 모양을 확장하여 셀과 열 사용자 지정](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) 및 [방법: Windows Forms DataGridView 셀에서 컨트롤 호스팅](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)을 참조하십시오.  
  
## DataGridView 클래스 요약  
 <xref:System.Windows.Forms>  
  
|기술 영역|클래스\/인터페이스\/구성 요소|  
|-----------|-----------------------|  
|데이터 바인딩|<xref:System.Windows.Forms.BindingSource>|  
|데이터 표시|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell> 및 파생 클래스<br /><br /> <xref:System.Windows.Forms.DataGridViewRow> 및 파생 클래스<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> 및 파생 클래스<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|<xref:System.Windows.Forms.DataGridView> 확장성|<xref:System.Windows.Forms.DataGridViewCell> 및 파생 클래스<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> 및 파생 클래스<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## 새로운 기능  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 Windows Forms에서 표 형식 데이터를 표시하는 데 필요한 모든 기능을 갖춘 솔루션입니다.  새 응용 프로그램을 만들 때는 <xref:System.Windows.Forms.DataGrid>와 같은 다른 솔루션을 사용하기 전에 <xref:System.Windows.Forms.DataGridView> 컨트롤을 먼저 사용하는 것이 좋습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.BindingSource> 구성 요소와 함께 사용할 수 있습니다.  이 구성 요소는 폼의 주 데이터 소스로 사용할 수 있습니다.  이 구성 요소는 데이터 소스 형식에 관계없이 <xref:System.Windows.Forms.DataGridView> 컨트롤과 해당 데이터 소스의 상호 작용을 관리할 수 있습니다.  
  
## 참고 항목  
 [DataGridView 컨트롤 개요](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)   
 [DataGridView 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)   
 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)