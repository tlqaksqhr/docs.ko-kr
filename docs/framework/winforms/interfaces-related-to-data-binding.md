---
title: "데이터 바인딩과 관련된 인터페이스 | Microsoft Docs"
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
  - "데이터[Windows Forms], 데이터 바인딩 인터페이스"
  - "데이터 바인딩, 인터페이스"
  - "IBindingList 인터페이스, Windows Forms 데이터 바인딩"
  - "IBindingListView 인터페이스"
  - "IDataErrorInfo 인터페이스, Windows Forms 데이터 바인딩"
  - "IEditableObject 인터페이스, Windows Forms 데이터 바인딩"
  - "IList 인터페이스, Windows Forms 데이터 바인딩"
  - "INotifyPropertyChanged 인터페이스"
  - "인터페이스, Windows Forms 데이터 바인딩"
ms.assetid: 14e49a2e-3e46-47ca-b491-70d546333277
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# 데이터 바인딩과 관련된 인터페이스
[!INCLUDE[vstecado](../../../includes/vstecado-md.md)]을 사용하면 응용 프로그램과 처리할 데이터의 바인딩 요구를 충족시킬 다양한 데이터 구조를 만들 수 있습니다.  Windows Forms에서 데이터를 제공하거나 사용하는 고유 클래스를 만들어야 할 수도 있습니다.  이들 개체는 기본 데이터 바인딩부터 디자인 타임 지원, 오류 확인, 변경 사항 알림, 심지어 데이터 자체의 변경 내용에 대한 구조화된 롤백 지원에 이르기까지 다양한 수준의 복합 기능을 제공할 수 있습니다.  
  
## 데이터 바인딩 인터페이스의 소비자  
 다음 단원에서는 두 그룹의 인터페이스 개체를 설명합니다.  첫 번째 그룹에서는 데이터 소스 작성자에 의해 데이터 소스에 구현된 인터페이스를 나열합니다.  이러한 인터페이스는 데이터 소스 소비자가 사용하며, 이러한 소비자는 대부분의 경우 Windows Forms 컨트롤이나 구성 요소입니다.  두 번째 그룹에서는 구성 요소 작성자를 위해 설계된 인터페이스를 나열합니다.  구성 요소 작성자는 이러한 인터페이스를 사용하여 Windows Forms 데이터 바인딩 엔진에서 사용할 데이터 바인딩을 지원하는 구성 요소를 만들 수 있습니다.  폼과 관련된 클래스 안에 이러한 인터페이스를 구현하여 데이터 바인딩을 사용할 수 있습니다. 각 경우에서 데이터와의 상호 작용이 가능한 인터페이스를 구현하는 클래스가 제공됩니다.  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] RAD\(Rapid Application Development\) 데이터 디자인 연습 도구에서는 이미 이 기능이 활용되고 있습니다.  
  
### 데이터 소스 작성자가 구현할 수 있는 인터페이스  
 다음 인터페이스는 Windows Forms 컨트롤에 의해 사용됩니다.  
  
-   <xref:System.Collections.IList> 인터페이스  
  
     <xref:System.Collections.IList> 인터페이스를 구현하는 클래스는 <xref:System.Array>, <xref:System.Collections.ArrayList> 또는 <xref:System.Collections.CollectionBase>일 수 있습니다.  이러한 클래스는 <xref:System.Object> 형식의 항목으로 이루어진 인덱스된 목록입니다.  인덱스의 첫 번째 항목에 따라 형식이 결정되기 때문에 이러한 목록에는 같은 형식이 포함되어야 합니다.  <xref:System.Collections.IList>는 런타임에만 바인딩에 사용할 수 있습니다.  
  
    > [!NOTE]
    >  Windows Forms와 바인딩할 비즈니스 개체 목록을 만들려면 <xref:System.ComponentModel.BindingList%601>을 사용하는 것이 좋습니다.  <xref:System.ComponentModel.BindingList%601>은 양방향 Windows Forms 데이터 바인딩에 필요한 기본 인터페이스를 구현하는 확장 가능한 클래스입니다.  
  
-   <xref:System.ComponentModel.IBindingList> 인터페이스  
  
     <xref:System.ComponentModel.IBindingList> 인터페이스를 구현하는 클래스는 훨씬 더 높은 수준의 데이터 바인딩 기능을 제공합니다.  이 구현은 목록 자체가 변경된 경우\(예: 목록 항목 개수의 증가\/감소\)뿐 아니라 목록 항목이 변경된 경우\(예: 고객 목록의 세 번째 항목에서 주소 필드가 변경됨\)에도 기본적인 정렬 기능과 변경 알림을 제공합니다.  변경 알림은 여러 컨트롤을 같은 데이터에 바인딩할 때 한 컨트롤의 데이터 변경을 다른 바인딩된 컨트롤에 전파하려는 경우에 중요합니다.  
  
    > [!NOTE]
    >  변경 알림은 <xref:System.ComponentModel.IBindingList> 인터페이스에서 <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> 속성을 통해 사용할 수 있으며, 이 속성을 `true`로 설정하면 목록이 변경되었거나 목록의 항목이 변경되었음을 나타내는 <xref:System.ComponentModel.IBindingList.ListChanged> 이벤트가 발생합니다.  
  
     변경 형식은 <xref:System.ComponentModel.ListChangedEventArgs> 매개 변수의 <xref:System.ComponentModel.ListChangedType> 속성에 의해 설명됩니다.  그러므로 데이터 모델이 업데이트될 때마다 같은 데이터 소스에 바인딩된 다른 컨트롤과 같은 모든 종속 뷰도 업데이트됩니다.  그러나 목록 안에 포함된 개체가 변경될 경우에는 목록에 이를 알려 목록에서 <xref:System.ComponentModel.IBindingList.ListChanged> 이벤트를 발생시킬 수 있도록 해야 합니다.  
  
    > [!NOTE]
    >  <xref:System.ComponentModel.BindingList%601>은 <xref:System.ComponentModel.IBindingList> 인터페이스의 제네릭 구현을 제공합니다.  
  
-   <xref:System.ComponentModel.IBindingListView> 인터페이스  
  
     <xref:System.ComponentModel.IBindingListView> 인터페이스를 구현하는 클래스는 필터링 및 고급 정렬 기능 외에도 <xref:System.ComponentModel.IBindingList> 구현의 모든 기능을 제공합니다.  이 구현에서는 문자열 기반 필터링 기능과 속성 설명자 방향 쌍을 사용한 여러 열 정렬 기능을 제공합니다.  
  
-   <xref:System.ComponentModel.IEditableObject> 인터페이스  
  
     <xref:System.ComponentModel.IEditableObject> 인터페이스를 구현하는 클래스를 사용하면 해당 개체에 대한 변경 내용을 영구화할 시기를 제어할 수 있습니다.  이 구현에서는 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A> 및 <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 메서드를 제공합니다. 이러한 메서드를 통해 개체의 변경 내용을 롤백할 수 있습니다.  다음은 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A> 및 <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 메서드의 기능과 데이터의 변경 내용을 롤백하기 위해 이러한 메서드가 함께 실행되는 방식에 대한 간략한 설명입니다.  
  
    -   <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 메서드는 개체에 대한 편집이 시작되었음을 나타냅니다.  이 인터페이스를 구현하는 개체는 <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 메서드가 호출될 경우 업데이트 내용을 취소할 수 있도록 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 메서드 호출 이후의 모든 업데이트를 저장해야 합니다.  Windows Forms 데이터 바인딩에서는 단일 편집 트랜잭션\(예: <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>\) 범위 안에서 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>를 여러 번 호출할 수 있습니다.  <xref:System.ComponentModel.IEditableObject>의 구현에서는 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>가 이미 호출되었는지 여부를 추적하여 후속 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 호출을 무시해야 합니다.  이 메서드는 여러 번 호출될 수 있기 때문에 이에 대한 후속 호출로 인해 기존 데이터가 삭제되지 않도록 하는 것이 중요합니다. 즉, 후속 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 호출이 첫 번째 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 호출에서 이루어진 업데이트를 삭제하거나 저장된 데이터를 변경해서는 안 됩니다.  
  
    -   <xref:System.ComponentModel.IEditableObject.EndEdit%2A> 메서드는 해당 개체가 현재 편집 모드에 있을 경우, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>가 호출된 이후에 변경된 모든 내용을 내부 개체에 적용합니다.  
  
    -   <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 메서드는 개체의 모든 변경 내용을 취소합니다.  
  
     <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A> 및 <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 메서드의 작동 방식에 대한 자세한 내용은 [데이터 집합에 데이터 저장](../Topic/Save%20data%20back%20to%20the%20database.md)를 참조하십시오.  
  
     데이터 기능에 대한 이러한 트랜잭션 개념은 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 사용됩니다.  
  
-   <xref:System.ComponentModel.ICancelAddNew> 인터페이스  
  
     <xref:System.ComponentModel.ICancelAddNew> 인터페이스를 구현하는 클래스는 대개 <xref:System.ComponentModel.IBindingList> 인터페이스를 구현하며, 이 클래스를 통해 <xref:System.ComponentModel.IBindingList.AddNew%2A> 메서드를 사용하여 데이터 소스에 적용된 추가 내용을 롤백할 수 있습니다.  데이터 소스에서 <xref:System.ComponentModel.IBindingList> 인터페이스를 구현하는 경우에는 <xref:System.ComponentModel.ICancelAddNew> 인터페이스도 구현해야 합니다.  
  
-   <xref:System.ComponentModel.IDataErrorInfo> 인터페이스  
  
     <xref:System.ComponentModel.IDataErrorInfo> 인터페이스를 구현하는 클래스를 사용하면 개체에서 사용자 지정 오류 정보를 바인딩된 컨트롤에 제공할 수 있습니다.  
  
    -   <xref:System.ComponentModel.IDataErrorInfo.Error%2A> 속성은 일반 오류 메시지 텍스트\(예: "오류가 발생했습니다."\)를 반환합니다.  
  
    -   <xref:System.ComponentModel.IDataErrorInfo.Item%2A> 속성은 열로부터 특정 오류 메시지를 가진 문자열\(예: "`State` 열 값이 잘못되었습니다."\)을 반환합니다.  
  
-   <xref:System.Collections.IEnumerable> 인터페이스  
  
     <xref:System.Collections.IEnumerable> 인터페이스를 구현하는 클래스는 일반적으로 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]에서 사용됩니다.  이 인터페이스에 대한 Windows Forms 지원은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 통해서만 사용할 수 있습니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.BindingSource> 구성 요소는 모든 <xref:System.Collections.IEnumerable> 항목을 바인딩할 목적으로 별도의 목록에 복사합니다.  
  
-   <xref:System.ComponentModel.ITypedList> 인터페이스  
  
     <xref:System.ComponentModel.ITypedList> 인터페이스를 구현하는 컬렉션 클래스는 바인딩된 컨트롤에 노출된 속성의 순서와 집합을 제어하는 기능을 제공합니다.  
  
    > [!NOTE]
    >  <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> 메서드를 구현할 때 <xref:System.ComponentModel.PropertyDescriptor> 배열이 null이 아닌 경우 배열의 마지막 항목은 다른 항목 목록인 목록 속성을 설명하는 속성 설명자가 됩니다.  
  
-   <xref:System.ComponentModel.ICustomTypeDescriptor> 인터페이스  
  
     <xref:System.ComponentModel.ICustomTypeDescriptor> 인터페이스를 구현하는 클래스는 클래스 자체에 대한 동적 정보를 제공합니다.  이 인터페이스는 <xref:System.ComponentModel.ITypedList>와 유사하지만 목록 대신 개체에 사용됩니다.  이 인터페이스는 <xref:System.Data.DataRowView>에서 내부 행의 스키마를 설정하는 데 사용됩니다.  <xref:System.ComponentModel.ICustomTypeDescriptor>의 간단한 구현은 <xref:System.ComponentModel.CustomTypeDescriptor> 클래스에서 제공됩니다.  
  
    > [!NOTE]
    >  <xref:System.ComponentModel.ICustomTypeDescriptor>를 구현하는 형식에 대한 디자인 타임 바인딩을 지원하려면 해당 형식이 <xref:System.ComponentModel.IComponent>를 구현하고 폼에 인스턴스로 존재해야 합니다.  
  
-   <xref:System.ComponentModel.IListSource> 인터페이스  
  
     <xref:System.ComponentModel.IListSource> 인터페이스를 구현하는 클래스를 사용하면 목록이 아닌 개체에서 목록 기반 바인딩을 수행할 수 있습니다.  <xref:System.ComponentModel.IListSource>의 <xref:System.ComponentModel.IListSource.GetList%2A> 메서드는 <xref:System.Collections.IList>에서 상속되지 않는 개체로부터 바인딩할 수 있는 목록을 반환하는 데 사용됩니다.  <xref:System.ComponentModel.IListSource>는 <xref:System.Data.DataSet> 클래스에서 사용됩니다.  
  
-   <xref:System.ComponentModel.IRaiseItemChangedEvents> 인터페이스  
  
     <xref:System.ComponentModel.IRaiseItemChangedEvents> 인터페이스를 구현하는 클래스는 <xref:System.ComponentModel.IBindingList> 인터페이스도 구현하는 바인딩 가능한 목록입니다.  이 인터페이스는 형식에서 <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A> 속성을 통해 <xref:System.ComponentModel.ListChangedType> 형식의 <xref:System.ComponentModel.IBindingList.ListChanged> 이벤트를 발생시키는지 여부를 나타내는 데 사용됩니다.  
  
    > [!NOTE]
    >  데이터 소스가 앞에서 설명한 이벤트 변환을 나열하는 속성을 제공하고 <xref:System.Windows.Forms.BindingSource> 구성 요소와 상호 작용하는 경우에는 <xref:System.ComponentModel.IRaiseItemChangedEvents>를 구현해야 합니다.  그렇지 않으면 <xref:System.Windows.Forms.BindingSource>가 이벤트 변환을 나열하는 속성도 수행하여 성능이 저하됩니다.  
  
-   <xref:System.ComponentModel.ISupportInitialize> 인터페이스  
  
     <xref:System.ComponentModel.ISupportInitialize> 인터페이스를 구현하는 구성 요소는 일괄 처리 최적화를 통해 속성을 설정하고 상호 종속적인 속성을 초기화합니다.  <xref:System.ComponentModel.ISupportInitialize>에는 두 개의 메서드가 있습니다.  
  
    -   <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A>는 개체 초기화가 시작됨을 나타냅니다.  
  
    -   <xref:System.ComponentModel.ISupportInitialize.EndInit%2A>는 개체 초기화가 완료됨을 나타냅니다.  
  
-   <xref:System.ComponentModel.ISupportInitializeNotification> 인터페이스  
  
     <xref:System.ComponentModel.ISupportInitializeNotification> 인터페이스를 구현하는 구성 요소는 <xref:System.ComponentModel.ISupportInitialize> 인터페이스도 구현합니다.  이 인터페이스를 사용하면 초기화가 완료되었음을 다른 <xref:System.ComponentModel.ISupportInitialize> 구성 요소에 알릴 수 있습니다.  <xref:System.ComponentModel.ISupportInitializeNotification> 인터페이스에는 두 개의 멤버가 있습니다.  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A>는 구성 요소가 초기화되었는지 여부를 나타내는 `boolean` 값을 반환합니다.  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.Initialized>는 <xref:System.ComponentModel.ISupportInitialize.EndInit%2A>가 호출될 때 발생합니다.  
  
-   <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스  
  
     이 인터페이스를 구현하는 클래스는 해당 속성 값이 변경될 때 이벤트를 발생시키는 형식입니다.  이 인터페이스는 컨트롤의 각 속성에 대한 변경 이벤트를 갖는 패턴을 바꾸는 데 사용합니다.  <xref:System.ComponentModel.BindingList%601>에서 사용할 경우 비즈니스 개체는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현해야 하며, BindingList\`1은 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트를 <xref:System.ComponentModel.ListChangedType> 형식의 <xref:System.ComponentModel.BindingList%601.ListChanged> 이벤트로 변환합니다.  
  
    > [!NOTE]
    >  바인딩된 클라이언트와 데이터 소스 간의 바인딩에서 변경 알림이 발생하도록 하려면 바인딩된 데이터 소스 형식에서 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현하도록 하거나\(기본 설정\) 바인딩된 형식에 *propertyName*`Changed` 이벤트를 제공합니다. 그러나 두 가지를 모두 수행할 수는 없습니다.  
  
### 구성 요소 작성자가 구현할 수 있는 인터페이스  
 다음 인터페이스는 Windows Forms 데이터 바인딩 엔진에서 사용됩니다.  
  
-   <xref:System.Windows.Forms.IBindableComponent> 인터페이스  
  
     이 인터페이스를 구현하는 클래스는 컨트롤이 아닌 구성 요소이며 데이터 바인딩을 지원합니다.  이 클래스는 이 인터페이스의 <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> 및 <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> 속성을 통해 구성 요소의 데이터 바인딩 및 바인딩 컨텍스트를 반환합니다.  
  
    > [!NOTE]
    >  구성 요소가 <xref:System.Windows.Forms.Control>에서 상속되는 경우에는 <xref:System.Windows.Forms.IBindableComponent> 인터페이스를 구현하지 않아도 됩니다.  
  
-   <xref:System.Windows.Forms.ICurrencyManagerProvider> 인터페이스  
  
     <xref:System.Windows.Forms.ICurrencyManagerProvider> 인터페이스를 구현하는 클래스는 이 특정 구성 요소에 연결된 바인딩을 관리할 수 있는 고유한 <xref:System.Windows.Forms.CurrencyManager>를 제공하는 구성 요소입니다.  사용자 지정 <xref:System.Windows.Forms.CurrencyManager>에는 <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> 속성을 통해 액세스할 수 있습니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.Control>에서 상속되는 클래스는 해당 <xref:System.Windows.Forms.Control.BindingContext%2A> 속성을 통해 바인딩을 자동으로 관리하기 때문에 <xref:System.Windows.Forms.ICurrencyManagerProvider>를 구현해야 하는 경우는 거의 없습니다.  
  
## 참고 항목  
 [데이터 바인딩 및 Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [방법: Windows Form에 단순 바인딩된 컨트롤 만들기](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)   
 [Windows Forms 데이터 바인딩](../../../docs/framework/winforms/windows-forms-data-binding.md)