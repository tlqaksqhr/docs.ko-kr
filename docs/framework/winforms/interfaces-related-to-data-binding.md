---
title: 데이터 바인딩과 관련된 인터페이스
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], data-binding interfaces
- INotifyPropertyChanged interface
- IBindingListView interface
- IList interface [Windows Forms], Windows Forms data binding
- IBindingList interface [Windows Forms], Windows Forms data binding
- interfaces [Windows Forms], Windows Forms data binding
- IEditableObject interface [Windows Forms], Windows Forms data binding
- data binding [Windows Forms], interfaces
- IDataErrorInfo interface [Windows Forms], Windows Forms data binding
ms.assetid: 14e49a2e-3e46-47ca-b491-70d546333277
ms.openlocfilehash: 6c4470b33977408fa4429d187dafd76241d0d9d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="interfaces-related-to-data-binding"></a>데이터 바인딩과 관련된 인터페이스
[!INCLUDE[vstecado](../../../includes/vstecado-md.md)]을 사용하면 응용 프로그램과 처리할 데이터의 바인딩 요구를 충족시킬 다양한 데이터 구조를 만들 수 있습니다. Windows Forms에서 데이터를 제공하거나 사용하는 고유 클래스를 만들고 싶을 수도 있습니다. 이러한 개체는 기본 데이터 바인딩부터 디자인 타임 지원, 오류 확인, 변경 사항 알림, 심지어 데이터 자체에 적용된 변경 내용의 구조화된 롤백 지원에 이르기까지 다양한 수준의 복합 기능을 제공할 수 있습니다.  
  
## <a name="consumers-of-data-binding-interfaces"></a>데이터 바인딩 인터페이스의 소비자  
 다음 섹션에서는 두 그룹의 인터페이스 개체를 설명합니다. 첫 번째 그룹에서는 데이터 소스 작성자에 의해 데이터 소스에 구현된 인터페이스를 나열합니다. 이러한 인터페이스는 데이터 소스 소비자가 사용하며, 이러한 소비자의 대부분은 Windows Forms 컨트롤 또는 구성 요소입니다. 두 번째 그룹에서는 구성 요소 작성자를 위해 설계된 인터페이스를 나열합니다. 구성 요소 작성자는 Windows Forms 데이터 바인딩 엔진에서 사용할 데이터 바인딩을 지원하는 구성 요소를 만들 때 이러한 인터페이스를 사용합니다. 양식과 연결된 클래스 내에 이러한 인터페이스를 구현하여 데이터 바인딩을 사용할 수 있습니다. 각 경우에 데이터와의 상호 작용이 가능한 인터페이스를 구현하는 클래스가 제공됩니다. 이미 visual Studio 신속한 응용 프로그램 RAD (개발) 데이터 디자인 환경 도구 활용이 기능의 합니다.  
  
### <a name="interfaces-for-implementation-by-data-source-authors"></a>데이터 소스 작성자가 구현할 수 있는 인터페이스  
 다음 인터페이스는 Windows Forms 컨트롤에서 사용할 수 있도록 설계되었습니다.  
  
-   <xref:System.Collections.IList> 인터페이스  
  
     구현 하는 클래스는 <xref:System.Collections.IList> 인터페이스 수는 <xref:System.Array>, <xref:System.Collections.ArrayList>, 또는 <xref:System.Collections.CollectionBase>합니다. 이 인덱싱된 항목 유형 목록을 <xref:System.Object>합니다. 인덱스의 첫 번째 항목에 따라 형식이 결정되기 때문에 이러한 목록에는 같은 형식이 포함되어 있어야 합니다. <xref:System.Collections.IList> 런타임 시 바인딩에 사용 됩니다.  
  
    > [!NOTE]
    >  Windows forms 바인딩에 대 한 비즈니스 개체의 목록을 만들려는 경우 사용을 고려해 야 하는 <xref:System.ComponentModel.BindingList%601>합니다. <xref:System.ComponentModel.BindingList%601> 는 필요한 양방향 Windows Forms 데이터 바인딩에 대 한 기본 인터페이스를 구현 하는 확장할 수 있는 클래스입니다.  
  
-   <xref:System.ComponentModel.IBindingList> 인터페이스  
  
     구현 하는 클래스는 <xref:System.ComponentModel.IBindingList> 인터페이스는 훨씬 더 높은 수준의 데이터 바인딩 기능을 제공 합니다. 이 구현은 목록 자체가 변경된 경우(예: 목록 항목 개수의 증가/감소)뿐 아니라 목록 항목이 변경된 경우(예: 고객 목록의 세 번째 항목에서 주소 필드가 변경됨)에도 기본적인 정렬 기능과 변경 알림을 제공합니다. 변경 알림은 여러 컨트롤을 같은 데이터에 바인딩할 때 한 컨트롤의 데이터 변경을 다른 바인딩된 컨트롤에 전파하려는 경우에 중요합니다.  
  
    > [!NOTE]
    >  에 대 한 변경 알림을 사용 하는 <xref:System.ComponentModel.IBindingList> 를 통해 상호 작용는 <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> 속성은 때 `true`, 발생는 <xref:System.ComponentModel.IBindingList.ListChanged> 변경 변경 목록 또는 목록에서 항목을 나타내는 이벤트를 합니다.  
  
     유형의 변경 하 여 설명의 <xref:System.ComponentModel.ListChangedType> 의 속성은 <xref:System.ComponentModel.ListChangedEventArgs> 매개 변수입니다. 그러므로 데이터 모델이 업데이트될 때마다 같은 데이터 소스에 바인딩된 다른 컨트롤과 같은 모든 종속 뷰도 업데이트됩니다. 그러나 목록을 발생 시킬 수 있도록 변경 될 때 목록에 알리기 위해 목록에 포함 된 개체는가 <xref:System.ComponentModel.IBindingList.ListChanged> 이벤트입니다.  
  
    > [!NOTE]
    >  <xref:System.ComponentModel.BindingList%601> 의 제네릭 구현을 제공는 <xref:System.ComponentModel.IBindingList> 인터페이스입니다.  
  
-   <xref:System.ComponentModel.IBindingListView> 인터페이스  
  
     구현 하는 클래스는 <xref:System.ComponentModel.IBindingListView> 인터페이스의 구현의 모든 기능을 제공 <xref:System.ComponentModel.IBindingList>도 필터링 및 고급 기능을 정렬 합니다. 이 구현은 문자열 기반 필터링 기능과 속성 설명자 방향 쌍을 사용한 여러 열 정렬 기능을 제공합니다.  
  
-   <xref:System.ComponentModel.IEditableObject> 인터페이스  
  
     구현 하는 클래스는 <xref:System.ComponentModel.IEditableObject> 인터페이스 경우 해당 개체에 대 한 변경 내용이 영구적으로 반영을 제어 하는 개체를 사용 합니다. 이 구현에서 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, 및 <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 는 개체에 대 한 변경 내용을 롤백할 수 있도록 하는 메서드. 다음은의 기능에 대해 간략하게 설명 된 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, 및 <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 메서드 및 데이터에 대 한 변경 내용의 롤백하기 위해 함께에서 작동 방식:  
  
    -   <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 메서드는 개체에 대 한 편집의 시작을 알림입니다. 이 인터페이스를 구현 하는 개체를 이후의 모든 업데이트를 저장 해야 하는 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 업데이트를 무시할 수 있습니다 하는 방식으로 메서드를 호출 하는 경우는 <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 메서드를 호출 합니다. Windows Forms 데이터 바인딩에서 호출할 수 있습니다 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 여러 번 single 값의 범위 내에서 편집할 트랜잭션 (예를 들어 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>). 구현 <xref:System.ComponentModel.IEditableObject> 여부를 추적 해야 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 이미 호출 하 고 후속 호출을 무시 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>합니다. 이 메서드는 여러 번 호출할 수 있습니다, 되므로 이후 호출 하는 비파괴적; 즉, 후속 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 호출이 이루어진 또는 저장 된 데이터를 변경 하는 업데이트를 제거할 수 없습니다 첫 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 호출 합니다.  
  
    -   <xref:System.ComponentModel.IEditableObject.EndEdit%2A> 메서드 이후의 모든 변경 내용은 마스터가 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> 개체가 편집 모드에서 현재 내부 개체에 호출 되었습니다.  
  
    -   <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 메서드는 개체에 대 한 모든 변경 사항을 취소 합니다.  
  
     방식에 대 한 자세한 내용은 <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, 및 <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> 메서드 작업를 참조 하십시오. [데이터는 데이터베이스에 다시 저장](/visualstudio/data-tools/save-data-back-to-the-database)합니다.  
  
     데이터 기능에 대 한 이러한 트랜잭션 개념에서 사용 되는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.  
  
-   <xref:System.ComponentModel.ICancelAddNew> 인터페이스  
  
     구현 하는 클래스는 <xref:System.ComponentModel.ICancelAddNew> 일반적으로 인터페이스를 구현 하는 <xref:System.ComponentModel.IBindingList> 인터페이스 및 데이터 소스에 대 한 추가 롤백할 수 있습니다는 <xref:System.ComponentModel.IBindingList.AddNew%2A> 메서드. 데이터 원본 구현 하는 <xref:System.ComponentModel.IBindingList> 인터페이스를 또한 있어야을 구현할 수는 <xref:System.ComponentModel.ICancelAddNew> 인터페이스입니다.  
  
-   <xref:System.ComponentModel.IDataErrorInfo> 인터페이스  
  
     구현 하는 클래스는 <xref:System.ComponentModel.IDataErrorInfo> 인터페이스 바인딩된 컨트롤을 사용자 지정 오류 정보를 제공 하는 개체를 사용 합니다.  
  
    -   <xref:System.ComponentModel.IDataErrorInfo.Error%2A> 일반 오류 메시지 텍스트를 반환 하는 속성 (예를 들어 "오류가 발생 했습니다").  
  
    -   <xref:System.ComponentModel.IDataErrorInfo.Item%2A> 열에서 특정 오류 메시지와 함께 문자열을 반환 하는 속성 (예를 들어 "의 값은 `State` 열이 유효 하지").  
  
-   <xref:System.Collections.IEnumerable> 인터페이스  
  
     구현 하는 클래스는 <xref:System.Collections.IEnumerable> 에서 인터페이스는 일반적으로 사용 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]합니다. 이 인터페이스에 대 한 Windows Forms 지원은만 통해 사용할 수는 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.BindingSource> 구성 요소를 모두 복사 <xref:System.Collections.IEnumerable> 바인딩 용 별도 목록에 항목입니다.  
  
-   <xref:System.ComponentModel.ITypedList> 인터페이스  
  
     구현 하는 컬렉션 클래스는 <xref:System.ComponentModel.ITypedList> 인터페이스는 순서와 바인딩된 컨트롤에 노출 하는 속성 집합을 제어 하는 기능을 제공 합니다.  
  
    > [!NOTE]
    >  구현 하는 경우는 <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> 메서드, 및 <xref:System.ComponentModel.PropertyDescriptor> 배열이 null, 배열의 마지막 항목에는 항목 목록을 다른 목록 속성을 설명 하는 속성 설명자 됩니다.  
  
-   <xref:System.ComponentModel.ICustomTypeDescriptor> 인터페이스  
  
     구현 하는 클래스는 <xref:System.ComponentModel.ICustomTypeDescriptor> 인터페이스 자체에 대 한 동적 정보를 제공 합니다. 이 인터페이스는 비슷합니다 <xref:System.ComponentModel.ITypedList> 그러나 목록 대신 개체에 사용 됩니다. 이 인터페이스는 사용 하 여 <xref:System.Data.DataRowView> 에 기본 행의 스키마를 설정 합니다. 간단한 구현을 <xref:System.ComponentModel.ICustomTypeDescriptor> 에서 제공 되는 <xref:System.ComponentModel.CustomTypeDescriptor> 클래스입니다.  
  
    > [!NOTE]
    >  디자인 타임에는 바인딩을 지원 하기 위해 구현 하는 형식 <xref:System.ComponentModel.ICustomTypeDescriptor>, 유형을 구현 해야 <xref:System.ComponentModel.IComponent> 양식에 인스턴스로 존재 합니다.  
  
-   <xref:System.ComponentModel.IListSource> 인터페이스  
  
     구현 하는 클래스는 <xref:System.ComponentModel.IListSource> 목록이 아닌 개체에 대 한 바인딩 목록 기반 인터페이스를 수 있습니다. <xref:System.ComponentModel.IListSource.GetList%2A> 방식의 <xref:System.ComponentModel.IListSource> 바인딩 가능한 목록에서 상속 되지 않는 개체에서 반환 하는 데 사용 되 <xref:System.Collections.IList>합니다. <xref:System.ComponentModel.IListSource> 사용 되는 <xref:System.Data.DataSet> 클래스입니다.  
  
-   <xref:System.ComponentModel.IRaiseItemChangedEvents> 인터페이스  
  
     구현 하는 클래스는 <xref:System.ComponentModel.IRaiseItemChangedEvents> 인터페이스는 구현 하는 바인딩 가능한 목록에서 <xref:System.ComponentModel.IBindingList> 인터페이스입니다. 형식 발생 하는 경우를 나타내기 위해이 인터페이스는 사용 <xref:System.ComponentModel.IBindingList.ListChanged> 형식의 이벤트 <xref:System.ComponentModel.ListChangedType.ItemChanged> 를 통해 해당 <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A> 속성입니다.  
  
    > [!NOTE]
    >  구현 해야는 <xref:System.ComponentModel.IRaiseItemChangedEvents> 데이터 원본 앞에서 설명한 이벤트 변환 나열 하는 속성을 제공 하 고 상호 작용 하는 경우는 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다. 그렇지 않은 경우는 <xref:System.Windows.Forms.BindingSource> 성능이 저하 이벤트 변환 나열 하는 속성도 수행 됩니다.  
  
-   <xref:System.ComponentModel.ISupportInitialize> 인터페이스  
  
     구현 하는 구성 요소는 <xref:System.ComponentModel.ISupportInitialize> 인터페이스 속성을 설정 하 고 상호 종속적인 속성 초기화에 대 한 일괄 처리 최적화 활용 합니다. <xref:System.ComponentModel.ISupportInitialize> 메서드도 포함 합니다.  
  
    -   <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> 해당 개체 초기화가 시작 됨을 알립니다.  
  
    -   <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> 해당 개체 초기화가 완료 신호를 보냅니다.  
  
-   <xref:System.ComponentModel.ISupportInitializeNotification> 인터페이스  
  
     구현 하는 구성 요소는 <xref:System.ComponentModel.ISupportInitializeNotification> 구현도 인터페이스는 <xref:System.ComponentModel.ISupportInitialize> 인터페이스입니다. 이 인터페이스를 사용 하면 다른에 알리기 위해 <xref:System.ComponentModel.ISupportInitialize> 구성 요소 초기화가 완료 되었음을 합니다. <xref:System.ComponentModel.ISupportInitializeNotification> 인터페이스 두 멤버가 포함 되어 있습니다.  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A> 반환 된 `boolean` 구성 요소가 초기화 되었는지 여부를 나타내는 값입니다.  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.Initialized> 발생 경우 <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> 라고 합니다.  
  
-   <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스  
  
     이 인터페이스를 구현하는 클래스는 해당 속성 값이 변경될 때 이벤트를 발생시키는 형식입니다. 이 인터페이스는 각 컨트롤 속성에서 변경 이벤트를 갖는 패턴을 바꾸는 데 사용됩니다. 사용 될 때는 <xref:System.ComponentModel.BindingList%601>, 비즈니스 개체를 구현 해야는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스와의 BindingList\`1은 변환 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트를 <xref:System.ComponentModel.BindingList%601.ListChanged> 형식의 이벤트 <xref:System.ComponentModel.ListChangedType.ItemChanged>합니다.  
  
    > [!NOTE]
    >  변경에 대 한 알림이 바인딩된 클라이언트와 데이터 간의 바인딩을 발생 하려면 원본 바인딩된 데이터 소스 유형을 구현 하도록 하거나는 <xref:System.ComponentModel.INotifyPropertyChanged> 제공할 수 있습니다 (기본 설정) 하는 인터페이스 또는 있습니다 *propertyName* `Changed` 바인딩 형식에 대 한 이벤트 둘 다 수행 하지 않아야 합니다.  
  
### <a name="interfaces-for-implementation-by-component-authors"></a>구성 요소 작성자가 구현할 수 있는 인터페이스  
 다음 인터페이스는 Windows Forms 데이터 바인딩 엔진에서 사용됩니다.  
  
-   <xref:System.Windows.Forms.IBindableComponent> 인터페이스  
  
     이 인터페이스를 구현하는 클래스는 컨트롤이 아닌 구성 요소이며 데이터 바인딩을 지원합니다. 데이터 바인딩 및 바인딩 컨텍스트를 통해 구성 요소를 반환 하는이 클래스는 <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> 및 <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> 이 인터페이스의 속성입니다.  
  
    > [!NOTE]
    >  구성 요소에서 상속 하는 경우 <xref:System.Windows.Forms.Control>를 구현할 필요가 없습니다는 <xref:System.Windows.Forms.IBindableComponent> 인터페이스입니다.  
  
-   <xref:System.Windows.Forms.ICurrencyManagerProvider> 인터페이스  
  
     구현 하는 클래스는 <xref:System.Windows.Forms.ICurrencyManagerProvider> 인터페이스 자체를 제공 하는 구성 요소는 <xref:System.Windows.Forms.CurrencyManager> 이 특정 구성 요소와 연결 된 바인딩을 관리 합니다. 사용자 지정에 대 한 액세스 <xref:System.Windows.Forms.CurrencyManager> 에서 제공 되는 <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> 속성입니다.  
  
    > [!NOTE]
    >  상속 되는 클래스 <xref:System.Windows.Forms.Control> 바인딩을 통해 자동으로 관리 해당 <xref:System.Windows.Forms.Control.BindingContext%2A> 속성을 구현 해야 하므로 사례는 <xref:System.Windows.Forms.ICurrencyManagerProvider> 모두 아주 드문 경우입니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 바인딩 및 Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [방법: Windows Form에 단순 바인딩된 컨트롤 만들기](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)  
 [Windows Forms 데이터 바인딩](../../../docs/framework/winforms/windows-forms-data-binding.md)
