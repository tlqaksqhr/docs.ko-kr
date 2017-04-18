---
title: "BindingSource 구성 요소 아키텍처 | Microsoft Docs"
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
  - "BindingSource 구성 요소[Windows Forms], BindingSource 구성 요소 정보"
  - "BindingSource 구성 요소, 아키텍처"
  - "데이터 바인딩, BindingSource 구성 요소"
  - "Windows Forms, 데이터 바인딩"
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# BindingSource 구성 요소 아키텍처
<xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하면 일반적으로 모든 Windows Forms 컨트롤을 데이터 소스에 바인딩할 수 있습니다.  
  
 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하면 데이터 소스에 컨트롤을 쉽게 바인딩할 수 있으며 일반적인 데이터 바인딩에 비해 다음과 같은 장점이 있습니다.  
  
-   비즈니스 개체에 대한 디자인 타임 바인딩을 사용합니다.  
  
-   <xref:System.Windows.Forms.CurrencyManager> 기능을 캡슐화하고 <xref:System.Windows.Forms.CurrencyManager> 이벤트를 디자인 타임에 노출합니다.  
  
-   기본적으로 목록 변경 알림을 지원하지 않는 데이터 소스에 대해 목록 변경 알림이 제공되므로 <xref:System.ComponentModel.IBindingList> 인터페이스를 지원하는 목록을 쉽게 만들 수 있습니다.  
  
-   <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=fullName> 메서드에 확장성 지점을 제공합니다.  
  
-   데이터 소스와 컨트롤 간의 간접 참조 수준을 제공합니다.  이 간접 참조 기능은 런타임에 데이터 소스가 변경될 수 있는 경우 중요합니다.  
  
-   다른 데이터 관련 Windows Forms 컨트롤, 특히 <xref:System.Windows.Forms.BindingNavigator> 및 <xref:System.Windows.Forms.DataGridView> 컨트롤과 상호 작용합니다.  
  
 따라서 Windows Forms 컨트롤을 데이터 소스에 바인딩할 때는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하는 것이 좋습니다.  
  
## BindingSource 기능  
 <xref:System.Windows.Forms.BindingSource> 구성 요소는 데이터에 컨트롤을 바인딩하는 여러 가지 기능을 제공합니다.  이러한 기능을 사용하면 코딩을 거의 하지 않고도 대부분의 데이터 바인딩 시나리오를 구현할 수 있습니다.  
  
 <xref:System.Windows.Forms.BindingSource> 구성 요소는 여러 종류의 데이터 소스에 액세스하는 일관된 인터페이스를 제공하므로 이러한 구현이 가능합니다.  즉, 모든 형식의 바인딩에 같은 프로시저를 사용하게 됨을 의미합니다.  예를 들어, <xref:System.Data.DataSet> 또는 비즈니스 개체에 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 속성을 연결할 수 있으며 이 두 경우에 모두 같은 속성, 메서드 및 이벤트 집합을 사용하여 데이터 소스를 조작합니다.  
  
 <xref:System.Windows.Forms.BindingSource> 구성 요소에서 일관된 인터페이스를 제공하므로 컨트롤에 데이터를 바인딩하는 과정이 아주 간단합니다.  변경 알림을 제공하는 데이터 소스 형식의 경우 <xref:System.Windows.Forms.BindingSource> 구성 요소가 컨트롤과 데이터 소스 간에 변경 내용을 자동으로 전달합니다.  변경 알림을 제공하지 않는 데이터 소스 형식의 경우에는 변경 알림이 발생할 수 있도록 이벤트가 제공됩니다.  다음 목록에서는 <xref:System.Windows.Forms.BindingSource> 구성 요소에서 지원하는 기능을 보여 줍니다.  
  
-   간접 참조  
  
-   현재 위치 관리  
  
-   데이터 소스 목록  
  
-   <xref:System.Windows.Forms.BindingSource>의 <xref:System.ComponentModel.IBindingList>  
  
-   사용자 지정 항목 만들기  
  
-   트랜잭션 항목 만들기  
  
-   <xref:System.Collections.IEnumerable> 지원  
  
-   디자인 타임 지원  
  
-   정적 <xref:System.Windows.Forms.ListBindingHelper> 메서드  
  
-   <xref:System.ComponentModel.IBindingListView> 인터페이스로 정렬 및 필터링  
  
-   <xref:System.Windows.Forms.BindingNavigator>와 통합  
  
### 간접 참조  
 <xref:System.Windows.Forms.BindingSource> 구성 요소는 컨트롤과 데이터 소스 간의 간접 참조 수준을 제공합니다.  컨트롤을 데이터 소스에 직접 바인딩하는 대신 <xref:System.Windows.Forms.BindingSource>에 바인딩하고 <xref:System.Windows.Forms.BindingSource> 구성 요소의 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 속성에 데이터 소스를 연결합니다.  
  
 이 간접 참조 수준을 사용하면 컨트롤 바인딩을 다시 설정하지 않고 데이터 소스를 변경할 수 있습니다.  따라서 다음 기능이 제공됩니다.  
  
-   현재 컨트롤 바인딩을 유지하면서 여러 데이터 소스에 <xref:System.Windows.Forms.BindingSource>를 연결할 수 있습니다.  
  
-   데이터 소스의 항목을 변경하고 컨트롤이 바인딩되었음을 알릴 수 있습니다.  자세한 내용은 [방법: BindingSource가 있는 Windows Forms 컨트롤에 데이터 소스 업데이트 내용 반영](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)을 참조하십시오.  
  
-   메모리의 개체 대신 <xref:System.Type>에 바인딩할 수 있습니다.  자세한 내용은 [방법: 형식에 Windows Forms 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)을 참조하십시오.  그러면 런타임에 개체를 바인딩할 수 있습니다.  
  
### 현재 위치 관리  
 <xref:System.Windows.Forms.BindingSource> 구성 요소는 <xref:System.Windows.Forms.ICurrencyManagerProvider> 인터페이스를 구현하여 현재 위치 관리를 처리합니다.  <xref:System.Windows.Forms.ICurrencyManagerProvider> 인터페이스를 사용하면 <xref:System.Windows.Forms.BindingSource>의 현재 위치 관리자는 물론 같은 <xref:System.Windows.Forms.BindingSource.DataMember%2A>에 바인딩된 다른 <xref:System.Windows.Forms.BindingSource>의 현재 위치 관리자에도 액세스할 수 있습니다.  
  
 <xref:System.Windows.Forms.BindingSource> 구성 요소는 <xref:System.Windows.Forms.CurrencyManager> 기능을 캡슐화하고 가장 일반적인 <xref:System.Windows.Forms.CurrencyManager> 속성 및 이벤트를 노출합니다.  다음 표에서는 현재 위치 관리와 관련된 몇 가지 멤버에 대해 설명합니다.  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> 속성  
 <xref:System.Windows.Forms.BindingSource>에 연결된 현재 위치 관리자를 가져옵니다.  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A> 메서드  
 지정된 데이터 멤버에 다른 <xref:System.Windows.Forms.BindingSource>가 바인딩되어 있으면 해당 현재 위치 관리자를 가져옵니다.  
  
 <xref:System.Windows.Forms.BindingSource.Current%2A> 속성  
 데이터 소스의 현재 항목을 가져옵니다.  
  
 <xref:System.Windows.Forms.BindingSource.Position%2A> 속성  
 기본 목록에서 현재 위치를 가져오거나 설정합니다.  
  
 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 메서드  
 내부 데이터 소스에 보류 중인 변경 내용을 적용합니다.  
  
 <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> 메서드  
 현재 편집 작업을 취소합니다.  
  
### 데이터 소스 목록  
 <xref:System.Windows.Forms.BindingSource> 구성 요소는 <xref:System.ComponentModel.IBindingListView> 및 <xref:System.ComponentModel.ITypedList> 인터페이스를 구현합니다.  이러한 구현을 통해 <xref:System.Windows.Forms.BindingSource> 구성 요소 자체를 외부 저장소 없이 데이터 소스로 사용할 수 있습니다.  
  
 <xref:System.Windows.Forms.BindingSource> 구성 요소가 데이터 소스에 연결되어 있으면 데이터 소스가 목록으로 노출됩니다.  
  
 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 속성을 형식, 개체, 형식 목록 등의  여러 데이터 소스로 설정할 수 있습니다.  결과 데이터 소스는 목록으로 노출됩니다.  다음 표에서는 몇 가지 일반적인 데이터 소스와 목록 계산 결과를 보여 줍니다.  
  
|DataSource 속성|목록 결과|  
|-------------------|-----------|  
|null 참조\(Visual Basic의 경우 `Nothing`\)|개체의 빈 <xref:System.ComponentModel.IBindingList>입니다.  항목을 추가하면 추가된 항목의 형식으로 목록이 설정됩니다.|  
|<xref:System.Windows.Forms.BindingSource.DataMember%2A>가 설정된 null 참조\(Visual Basic의 경우 `Nothing`\)|지원되지 않으며 <xref:System.ArgumentException>을 발생시킵니다.|  
|목록 이외의 형식 또는 "T" 형식의 개체|"T" 형식의 빈 <xref:System.ComponentModel.IBindingList>|  
|배열 인스턴스|배열 요소가 들어 있는 <xref:System.ComponentModel.IBindingList>|  
|<xref:System.Collections.IEnumerable> 인스턴스|<xref:System.Collections.IEnumerable> 항목이 들어 있는 <xref:System.ComponentModel.IBindingList>|  
|"T" 형식이 들어 있는 목록 인스턴스|"T" 형식이 들어 있는 <xref:System.ComponentModel.IBindingList> 인스턴스|  
  
 또한 <xref:System.Windows.Forms.BindingSource.DataSource%2A>를 <xref:System.ComponentModel.IListSource> 및 <xref:System.ComponentModel.ITypedList>와 같은 그 밖의 목록 형식으로 설정할 수 있으며 <xref:System.Windows.Forms.BindingSource>에서 이를 적절히 처리합니다.  이 경우에는 목록에 들어 있는 형식이 기본 생성자를 가집니다.  
  
### BindingSource를 IBindingList로  
 <xref:System.Windows.Forms.BindingSource> 구성 요소는 내부 데이터를 <xref:System.ComponentModel.IBindingList>로 조작 및 액세스할 수 있는 멤버를 제공합니다.  다음 표에서는 이러한 일부 멤버에 대해 설명합니다.  
  
|멤버|설명|  
|--------|--------|  
|<xref:System.Windows.Forms.BindingSource.List%2A> 속성|<xref:System.Windows.Forms.BindingSource.DataSource%2A> 또는 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 속성의 계산 결과 목록을 가져옵니다.|  
|<xref:System.Windows.Forms.BindingSource.AddNew%2A> 메서드|기본 목록에 새 항목을 추가합니다.  <xref:System.ComponentModel.IBindingList> 인터페이스를 구현하고 항목 추가를 허용\(즉, <xref:System.Windows.Forms.BindingSource.AllowNew%2A> 속성이 `true`로 설정됨\)하는 데이터 소스에 적용됩니다.|  
  
### 사용자 지정 항목 만들기  
 <xref:System.Windows.Forms.BindingSource.AddingNew> 이벤트를 처리하여 고유의 항목 만들기 논리를 제공할 수 있습니다.  새 개체가 <xref:System.Windows.Forms.BindingSource>에 추가되기 전에 <xref:System.Windows.Forms.BindingSource.AddingNew> 이벤트가 발생합니다.  이 이벤트는 <xref:System.Windows.Forms.BindingSource.AddNew%2A> 메서드가 호출된 후 새 항목이 기본 목록에 추가되기 전에 발생합니다.  이 이벤트를 처리하면 <xref:System.Windows.Forms.BindingSource> 클래스에서 파생시키지 않고 사용자 지정 항목 만들기 동작을 제공할 수 있습니다.  자세한 내용은 [방법: Windows Forms BindingSource를 사용하여 항목 추가 사용자 지정](../../../../docs/framework/winforms/controls/how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)을 참조하십시오.  
  
### 트랜잭션 항목 만들기  
 <xref:System.Windows.Forms.BindingSource> 구성 요소는 <xref:System.ComponentModel.ICancelAddNew> 인터페이스를 구현하여 트랜잭션 항목 만들기를 활성화합니다.  <xref:System.Windows.Forms.BindingSource.AddNew%2A> 호출을 통해 새 항목이 잠정적으로 만들어지고 나면 다음과 같은 방법으로 추가 내용을 커밋하거나 롤백할 수 있습니다.  
  
-   <xref:System.ComponentModel.ICancelAddNew.EndNew%2A> 메서드는 보류 중인 추가 내용을 명시적으로 커밋합니다.  
  
-   삽입, 제거, 이동 등의 다른 컬렉션 작업을 수행하면 보류 중인 추가 내용이 암시적으로 커밋됩니다.  
  
-   <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A> 메서드는 이 메서드가 아직 커밋되지 않은 경우 보류 중인 추가 내용을 롤백합니다.  
  
### IEnumerable 지원  
 <xref:System.Windows.Forms.BindingSource> 구성 요소는 <xref:System.Collections.IEnumerable> 데이터 소스에 컨트롤을 바인딩할 수 있는 기능을 활성화합니다.  이 구성 요소를 사용하면 <xref:System.Data.SqlClient.SqlDataReader?displayProperty=fullName>와 같은 데이터 소스에 바인딩할 수 있습니다.  
  
 <xref:System.Collections.IEnumerable> 데이터 소스를 <xref:System.Windows.Forms.BindingSource> 구성 요소에 할당하면 <xref:System.Windows.Forms.BindingSource>는 <xref:System.ComponentModel.IBindingList>를 만들고 <xref:System.Collections.IEnumerable> 데이터 소스의 내용을 목록에 추가합니다.  
  
### 디자인 타임 지원  
 팩터리 클래스에서 만든 개체나 웹 서비스에서 반환된 개체와 같은 일부 개체 형식은 디자인 타임에 만들 수 없습니다.  컨트롤이 바인딩할 수 있는 개체가 메모리에 없어도 디자인 타임에 이러한 형식에 컨트롤을 바인딩해야 하는 경우가 가끔 있습니다.  예를 들어, <xref:System.Windows.Forms.DataGridView> 컨트롤의 열 머리글에 사용자 지정 형식의 공용 속성 이름으로 레이블을 붙여야 하는 경우가 있습니다.  
  
 이 시나리오를 지원하기 위해 <xref:System.Windows.Forms.BindingSource> 구성 요소는 <xref:System.Type>에 바인딩할 수 있도록 지원합니다.  <xref:System.Windows.Forms.BindingSource.DataSource%2A> 속성에 <xref:System.Type>을 할당하면 <xref:System.Windows.Forms.BindingSource> 구성 요소는 <xref:System.Type> 항목의 빈 <xref:System.ComponentModel.BindingList%601>을 만듭니다.  이후에 <xref:System.Windows.Forms.BindingSource> 구성 요소에 컨트롤을 바인딩하면 디자인 타임이나 런타임에 해당 형식의 스키마나 속성이 있다는 알림을 받습니다.  자세한 내용은 [방법: 형식에 Windows Forms 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)을 참조하십시오.  
  
### 정적 ListBindingHelper 메서드  
 <xref:System.Windows.Forms.BindingContext?displayProperty=fullName>, <xref:System.Windows.Forms.CurrencyManager?displayProperty=fullName> 및 <xref:System.Windows.Forms.BindingSource> 형식은 모두 공통 논리를 통해 `DataSource`\/`DataMember` 쌍에서 목록을 생성합니다.  또한 이 공통 논리는 다음과 같은 `static` 메서드를 통해 컨트롤 작성자나 그 밖의 타사에서 사용할 수 있도록 공개적으로 노출됩니다.  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>.  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### IBindingListView 인터페이스로 정렬 및 필터링  
 <xref:System.Windows.Forms.BindingSource> 구성 요소는 <xref:System.ComponentModel.IBindingList> 인터페이스를 확장하는 <xref:System.ComponentModel.IBindingListView> 인터페이스를 구현합니다.  <xref:System.ComponentModel.IBindingList>는 단일 열 정렬을 제공하고 <xref:System.ComponentModel.IBindingListView>는 고급 정렬 및 필터링을 제공합니다.  데이터 소스에서도 이러한 인터페이스 중 하나를 구현할 경우 <xref:System.ComponentModel.IBindingListView>를 사용하면 데이터 소스의 항목을 정렬 및 필터링할 수 있습니다.  <xref:System.Windows.Forms.BindingSource> 구성 요소는 이러한 멤버의 참조 구현을 제공하지 않습니다.  대신 호출이 기본 목록에 전달됩니다.  
  
 다음 표에서는 정렬 및 필터링할 때 사용할 속성에 대해 설명합니다.  
  
|멤버|설명|  
|--------|--------|  
|<xref:System.Windows.Forms.BindingSource.Filter%2A> 속성|데이터 소스가 <xref:System.ComponentModel.IBindingListView>인 경우, 표시할 행을 필터링하는 데 사용되는 식을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.BindingSource.Sort%2A> 속성|데이터 소스가 <xref:System.ComponentModel.IBindingList>인 경우, 정렬에 사용되는 열 이름과 정렬 순서 정보를 가져오거나 설정합니다.<br /><br /> 또는<br /><br /> 데이터 소스가 <xref:System.ComponentModel.IBindingListView>이고 고급 정렬을 지원하는 경우, 정렬에 사용되는 여러 열 이름과 정렬 순서를 가져옵니다.|  
  
### BindingNavigator와 통합  
 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하면 모든 Windows Forms 컨트롤을 데이터 소스에 바인딩할 수 있지만, 특히 <xref:System.Windows.Forms.BindingSource> 구성 요소와 작동하도록 <xref:System.Windows.Forms.BindingNavigator> 컨트롤이 디자인되었습니다.  <xref:System.Windows.Forms.BindingNavigator> 컨트롤은 <xref:System.Windows.Forms.BindingSource> 구성 요소의 현재 항목을 제어할 수 있는 사용자 인터페이스를 제공합니다.  기본적으로 <xref:System.Windows.Forms.BindingNavigator> 컨트롤은 <xref:System.Windows.Forms.BindingSource> 구성 요소의 탐색 메서드에 해당하는 단추를 제공합니다.  자세한 내용은 [방법: Windows Forms BindingNavigator 컨트롤을 사용하여 데이터 탐색](../../../../docs/framework/winforms/controls/how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.BindingNavigator>   
 [BindingSource 구성 요소 개요](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)   
 [BindingNavigator 컨트롤](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)   
 [Windows Forms 데이터 바인딩](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [방법: 형식에 Windows Forms 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)   
 [방법: BindingSource가 있는 Windows Forms 컨트롤에 데이터 소스 업데이트 내용 반영](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)