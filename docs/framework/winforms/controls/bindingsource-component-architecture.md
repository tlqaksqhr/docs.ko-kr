---
title: "BindingSource 구성 요소 아키텍처"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BindingSource component [Windows Forms], architecture
- Windows Forms, data binding
- BindingSource component [Windows Forms], about BindingSource component
- data binding [Windows Forms], BindingSource component
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25a69f31d8da8638cfc92ff94d8f90dbcb327158
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bindingsource-component-architecture"></a>BindingSource 구성 요소 아키텍처
와 <xref:System.Windows.Forms.BindingSource> 구성 요소를 데이터 원본에 일반적으로 모든 Windows Forms 컨트롤을 바인딩할 수 있습니다.  
  
 <xref:System.Windows.Forms.BindingSource> 구성 요소 컨트롤을 데이터 소스에 바인딩하는 프로세스를 간소화 하 고 기존 데이터 바인딩을 통해 다음과 같은 이점이 있습니다.  
  
-   비즈니스 개체에 대 한 디자인 타임 바인딩을 활성화합니다.  
  
-   캡슐화 <xref:System.Windows.Forms.CurrencyManager> 기능과 노출 <xref:System.Windows.Forms.CurrencyManager> 디자인 타임에는 이벤트입니다.  
  
-   쉽게 지 원하는 목록을 만들 수는 <xref:System.ComponentModel.IBindingList> 목록을 고유 하 게 지원 하지 않는 데이터 원본 변경 알림을 목록 변경 알림을 제공 하 여 인터페이스입니다.  
  
-   에 대 한 확장성 지점을 제공는 <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=nameWithType> 메서드.  
  
-   데이터 소스와 컨트롤 간의 간접 참조 수준을 제공합니다. 이 간접 참조 데이터 원본에서 런타임에 변경 될 수 있습니다 때 유용 합니다.  
  
-   특히 Windows Forms 컨트롤 다른 관련 된 데이터와 상호 운용 되는 <xref:System.Windows.Forms.BindingNavigator> 및 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다.  
  
 이러한 이유로 <xref:System.Windows.Forms.BindingSource> 구성 요소는 데이터 원본에 Windows Forms 컨트롤을 바인딩하는 것이 좋습니다.  
  
## <a name="bindingsource-features"></a>BindingSource 기능  
 <xref:System.Windows.Forms.BindingSource> 구성 요소는 데이터에 컨트롤 바인딩에 대 한 몇 가지 기능을 제공 합니다. 이러한 기능을 거의 없는 코딩을 대부분의 데이터 바인딩 시나리오를 구현할 수 있습니다.  
  
 <xref:System.Windows.Forms.BindingSource> 구성 요소의 다양 한 종류의 데이터 원본에 액세스 하기 위한 일관 된 인터페이스를 제공 하 여이 수행 합니다. 즉, 동일한 절차를 사용 하 여 모든 형식에 바인딩합니다. 예를 들어, 연결 수는 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 속성을는 <xref:System.Data.DataSet> 비즈니스 개체 하 고 두 경우 모두 동일한 집합이 속성, 메서드 및 이벤트를 사용 하 여 데이터 소스 조작를 합니다.  
  
 제공 하는 일관 된 인터페이스는 <xref:System.Windows.Forms.BindingSource> 구성 요소 컨트롤에 데이터를 바인딩하는 프로세스를 크게 간소화 됩니다. 변경 알림을 제공 하는 데이터 소스 형식에 대 한는 <xref:System.Windows.Forms.BindingSource> 구성 요소에는 자동으로 변경 내용을 컨트롤 및 데이터 원본 간의 통신 합니다. 이벤트에는 변경 알림을 제공 하지 않는 데이터 소스 형식에 대 한 변경 알림을 발생 시킬 수 있는 제공 됩니다. 다음 목록에서 지 원하는 기능을 보여 줍니다.는 <xref:System.Windows.Forms.BindingSource> 구성 요소:  
  
-   간접 참조 합니다.  
  
-   현재 항목 관리 합니다.  
  
-   목록으로 데이터 원본입니다.  
  
-   <xref:System.Windows.Forms.BindingSource>로 <xref:System.ComponentModel.IBindingList>합니다.  
  
-   사용자 지정 항목 만들기  
  
-   트랜잭션 항목 만들기  
  
-   <xref:System.Collections.IEnumerable>이 옵션을 지원 합니다.  
  
-   디자인 타임 지원 합니다.  
  
-   정적 <xref:System.Windows.Forms.ListBindingHelper> 메서드.  
  
-   정렬 및 필터링 된 <xref:System.ComponentModel.IBindingListView> 인터페이스입니다.  
  
-   와 통합 <xref:System.Windows.Forms.BindingNavigator>합니다.  
  
### <a name="indirection"></a>간접 참조  
 <xref:System.Windows.Forms.BindingSource> 구성 요소는 컨트롤 및 데이터 원본 간의 간접 참조 수준을 제공 합니다. 컨트롤을 데이터 원본에 직접 컨트롤에 바인딩하는 대신 바인딩할는 <xref:System.Windows.Forms.BindingSource>, 데이터 원본에 연결 하 고는 <xref:System.Windows.Forms.BindingSource> 구성 요소의 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 속성입니다.  
  
 이 수준의 간접 참조와 데이터 소스 제어 바인딩을 다시 설정 하지 않고 변경할 수 있습니다. 이 다음과 같은 기능을 제공 합니다.  
  
-   연결할 수는 <xref:System.Windows.Forms.BindingSource> 현재 제어 바인딩을 그대로 유지 하면서 다른 데이터 원본.  
  
-   데이터 소스의 항목을 변경할 수 있으며 바인딩된 컨트롤에 알립니다. 자세한 내용은 참조 [하는 방법: BindingSource가 있는 Windows Forms 컨트롤에 데이터 소스 업데이트 반영](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)합니다.  
  
-   바인딩할 수 있습니다는 <xref:System.Type> 메모리 내 개체 대신 합니다. 자세한 내용은 참조 [하는 방법: Windows Forms 컨트롤 형식에 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)합니다. 그런 다음 실행 시 개체에 바인딩할 수 있습니다.  
  
### <a name="currency-management"></a>현재 항목 관리  
 <xref:System.Windows.Forms.BindingSource> 구성 요소가 구현 하는 <xref:System.Windows.Forms.ICurrencyManagerProvider> 위치 관리를 처리 하는 인터페이스입니다. 와 <xref:System.Windows.Forms.ICurrencyManagerProvider> 인터페이스에 액세스할 수도 있습니다 통화 관리자에 게는 <xref:System.Windows.Forms.BindingSource>, 다른 작업에 대 한 현재 위치 관리자 외에도 <xref:System.Windows.Forms.BindingSource> 바인딩된 <xref:System.Windows.Forms.BindingSource.DataMember%2A>합니다.  
  
 <xref:System.Windows.Forms.BindingSource> 구성 요소를 캡슐화 <xref:System.Windows.Forms.CurrencyManager> 기능과 노출 가장 일반적인 <xref:System.Windows.Forms.CurrencyManager> 속성 및 이벤트입니다. 다음 표에서 현재 항목 관리와 관련 된 멤버 중 일부를 설명 합니다.  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> 속성  
 와 연결 된 현재 위치 관리자를 가져옵니다는 <xref:System.Windows.Forms.BindingSource>합니다.  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A> 메서드  
 다른 경우 <xref:System.Windows.Forms.BindingSource> 지정된 된 데이터 멤버에 바인딩된, 해당 현재 위치 관리자를 가져옵니다.  
  
 <xref:System.Windows.Forms.BindingSource.Current%2A> 속성  
 데이터 소스의 현재 항목을 가져옵니다.  
  
 <xref:System.Windows.Forms.BindingSource.Position%2A> 속성  
 내부 목록에서 현재 위치를 가져오거나 설정합니다.  
  
 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 메서드  
 내부 데이터 소스에 보류 중인 변경 내용을 적용합니다.  
  
 <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> 메서드  
 현재 편집 작업을 취소합니다.  
  
### <a name="data-source-as-a-list"></a>데이터 소스 목록  
 <xref:System.Windows.Forms.BindingSource> 구성 요소가 구현 하는 <xref:System.ComponentModel.IBindingListView> 및 <xref:System.ComponentModel.ITypedList> 인터페이스입니다. 이 구현을 사용할 수 있습니다는 <xref:System.Windows.Forms.BindingSource> 구성 요소 자체는 데이터 원본으로 외부 저장소 없이 합니다.  
  
 경우는 <xref:System.Windows.Forms.BindingSource> 데이터 원본에 연결 된 구성 요소, 데이터 원본 목록으로 노출 합니다.  
  
 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 을 여러 데이터 소스 속성을 설정할 수 있습니다. 여기에 형식, 개체 및 형식의 목록을 포함 합니다. 결과 데이터 소스 목록으로 노출 됩니다. 다음 표에서 몇 가지 일반적인 데이터 소스 및 목록 계산 결과 보여 줍니다.  
  
|DataSource 속성|목록 결과|  
|-------------------------|------------------|  
|null 참조(Visual Basic의 경우 `Nothing`)|빈 <xref:System.ComponentModel.IBindingList> 개체입니다. 추가 된 항목의 형식으로 목록을 설정 항목을 추가 합니다.|  
|Null 참조 (`Nothing` Visual basic에서)와 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 설정|지원 되지 않습니다. 발생 <xref:System.ArgumentException>합니다.|  
|목록이 아닌 형식 또는 "T" 유형의 개체|빈 <xref:System.ComponentModel.IBindingList> "T" 형식입니다.|  
|배열 인스턴스|<xref:System.ComponentModel.IBindingList> 배열 요소가 들어 있습니다.|  
|<xref:System.Collections.IEnumerable>인스턴스|<xref:System.ComponentModel.IBindingList> 포함 하는 <xref:System.Collections.IEnumerable> 항목|  
|"T" 유형이 포함 된 인스턴스를 나열 합니다.|<xref:System.ComponentModel.IBindingList> "T" 형식은 포함 하는 인스턴스.|  
  
 또한 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 와 같은 다른 목록 형식으로 설정할 수 있습니다 <xref:System.ComponentModel.IListSource> 및 <xref:System.ComponentModel.ITypedList>, 및 <xref:System.Windows.Forms.BindingSource> 적절히 처리 됩니다. 이 경우 목록에 포함 된 유형을 기본 생성자가 있어야 합니다.  
  
### <a name="bindingsource-as-an-ibindinglist"></a>IBindingList으로 BindingSource  
 <xref:System.Windows.Forms.BindingSource> 으로 기본 데이터 액세스 및 조작을 위한 멤버를 제공 하는 구성 요소는 <xref:System.ComponentModel.IBindingList>합니다. 다음 표에서 이러한 멤버 중 일부를 설명 합니다.  
  
|멤버|설명|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.List%2A> 속성|계산으로 인해 발생 하는 목록을 가져옵니다는 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 또는 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 속성입니다.|  
|<xref:System.Windows.Forms.BindingSource.AddNew%2A> 메서드|내부 목록에 새 항목을 추가합니다. 구현 하는 데이터 소스에 적용 됩니다는 <xref:System.ComponentModel.IBindingList> 인터페이스 및 항목 추가 허용 (즉,는 <xref:System.Windows.Forms.BindingSource.AllowNew%2A> 속성이로 설정 되어 `true`).|  
  
### <a name="custom-item-creation"></a>사용자 지정 항목 만들기  
 처리할 수는 <xref:System.Windows.Forms.BindingSource.AddingNew> 사용자 고유의 항목을 만들 논리를 제공 하는 이벤트입니다. <xref:System.Windows.Forms.BindingSource.AddingNew> 이벤트가 발생 하는 새 개체를 추가 하기 전에 <xref:System.Windows.Forms.BindingSource>합니다. 이 이벤트 후에 발생는 <xref:System.Windows.Forms.BindingSource.AddNew%2A> 메서드를 호출 전에 새 항목이 내부 목록에 추가 됩니다. 이 이벤트를 처리 하 여 사용자 지정 항목 만들기 동작에서 파생 없이 제공할 수 있습니다는 <xref:System.Windows.Forms.BindingSource> 클래스입니다. 자세한 내용은 참조 [하는 방법: Windows Forms BindingSource를 사용 하 여 항목 추가 사용자 지정](../../../../docs/framework/winforms/controls/how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)합니다.  
  
### <a name="transactional-item-creation"></a>트랜잭션 항목 만들기  
 <xref:System.Windows.Forms.BindingSource> 구성 요소가 구현 하는 <xref:System.ComponentModel.ICancelAddNew> 트랜잭션 항목을 만들 수 있는 인터페이스입니다. 새 항목에 대 한 호출을 사용 하 여 일시적으로 만들어진 후 <xref:System.Windows.Forms.BindingSource.AddNew%2A>, 추가 커밋 또는 다음과 같은 방법으로 롤백할 수 있습니다.  
  
-   <xref:System.ComponentModel.ICancelAddNew.EndNew%2A> 메서드를 명시적으로 보류 중인 추가 커밋합니다.  
  
-   삽입, 제거 또는 이동 등의 다른 컬렉션 작업을 수행 하면 보류 중인 추가 암시적으로 커밋합니다.  
  
-   <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A> 메서드는 보류 중인 추가 경우 롤백할 메서드가 아직 커밋되지 않았습니다.  
  
### <a name="ienumerable-support"></a>IEnumerable 지원  
 <xref:System.Windows.Forms.BindingSource> 구성 요소 바인딩 컨트롤을 사용 하면 <xref:System.Collections.IEnumerable> 데이터 원본입니다. 이 구성 요소를 바인딩할 수 있습니다 데이터 소스와 같은 <xref:System.Data.SqlClient.SqlDataReader?displayProperty=nameWithType>합니다.  
  
 경우는 <xref:System.Collections.IEnumerable> 데이터 원본에 할당 된는 <xref:System.Windows.Forms.BindingSource> 구성 요소는 <xref:System.Windows.Forms.BindingSource> 만듭니다는 <xref:System.ComponentModel.IBindingList> 의 내용을 추가 하 고는 <xref:System.Collections.IEnumerable> 목록에 데이터 원본.  
  
### <a name="design-time-support"></a>디자인 타임 지원  
 일부 개체 유형 팩터리 클래스에서 생성 된 개체 또는 웹 서비스에 의해 반환 되는 개체와 같은 디자인 타임에 만들 수 없습니다. 컨트롤이 바인딩할 수 있는 메모리에 개체가 없습니다 하는 경우에 이러한 형식에 디자인 타임에 컨트롤에 바인딩할 해야 경우가 합니다. 예를 들어 해야의 열 머리글에 레이블을 지정 하는 <xref:System.Windows.Forms.DataGridView> 사용자 정의 형식의 공용 속성 이름 사용 하 여 제어 합니다.  
  
 이 시나리오를 지원 하기는 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩을 지원는 <xref:System.Type>합니다. 할당 하면는 <xref:System.Type> 에 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 속성은 <xref:System.Windows.Forms.BindingSource> 구성 요소는 빈 만듭니다 <xref:System.ComponentModel.BindingList%601> 의 <xref:System.Type> 항목입니다. 이후에 바인딩할 모든 컨트롤은 <xref:System.Windows.Forms.BindingSource> 디자인 타임 또는 런타임 시 구성 요소 경고가 속성 또는 해당 형식의 스키마에 게 표시 됩니다. 자세한 내용은 참조 [하는 방법: Windows Forms 컨트롤 형식에 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)합니다.  
  
### <a name="static-listbindinghelper-methods"></a>정적 ListBindingHelper 메서드  
 <xref:System.Windows.Forms.BindingContext?displayProperty=nameWithType>, <xref:System.Windows.Forms.CurrencyManager?displayProperty=nameWithType>, 및 <xref:System.Windows.Forms.BindingSource> 형식을 모두 공통 논리에서 목록을 생성 하는 `DataSource` / `DataMember` 쌍입니다. 또한이 공통 논리는 공개적으로 노출 사용 하기 위해 컨트롤 작성자 및 다음에 제 3 자의 `static` 메서드:  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>.  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### <a name="sorting-and-filtering-with-the-ibindinglistview-interface"></a>IBindingListView 인터페이스로 정렬 및 필터링  
 <xref:System.Windows.Forms.BindingSource> 구성 요소가 구현 하는 <xref:System.ComponentModel.IBindingListView> 인터페이스를 확장 하 고 <xref:System.ComponentModel.IBindingList> 인터페이스입니다. <xref:System.ComponentModel.IBindingList> 단일 열 정렬을 제공 및 <xref:System.ComponentModel.IBindingListView> 는 고급 정렬 및 필터링 합니다. 와 <xref:System.ComponentModel.IBindingListView>, 정렬할 수 있습니다 및 데이터 소스 에서도 하는 경우 데이터 소스에서 항목을 필터링 이러한 인터페이스 중 하나를 구현 합니다. <xref:System.Windows.Forms.BindingSource> 구성 요소가 이러한 멤버를 구현 하는 참조를 제공 하지 않습니다. 대신, 호출 내부 목록에 전달 됩니다.  
  
 다음 표에서 정렬 및 필터링에 사용 하는 속성을 설명 합니다.  
  
|멤버|설명|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.Filter%2A> 속성|데이터 소스가 <xref:System.ComponentModel.IBindingListView>인 경우 표시할 행을 필터링하는 데 사용하는 식을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.BindingSource.Sort%2A> 속성|데이터 소스가 <xref:System.ComponentModel.IBindingList>인 경우 정렬에 사용되는 열 이름과 정렬 순서 정보를 가져오거나 설정합니다.<br /><br /> 또는<br /><br /> 데이터 원본이 경우는 <xref:System.ComponentModel.IBindingListView> 정렬, 고급 지원 가져옵니다 정렬 및 정렬 순서에 사용 되는 여러 열 이름|  
  
### <a name="integration-with-bindingnavigator"></a>BindingNavigator와의 통합  
 사용할 수는 <xref:System.Windows.Forms.BindingSource> 데이터 소스에 Windows Forms 컨트롤을 바인딩하는 구성 요소 이지만 <xref:System.Windows.Forms.BindingNavigator> 컨트롤은 작업을 위해 특별히 설계 되었습니다는 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다. <xref:System.Windows.Forms.BindingNavigator> 제어 하기 위한 사용자 인터페이스를 제공 하는 컨트롤의 <xref:System.Windows.Forms.BindingSource> 구성 요소의 현재 항목입니다. 기본적으로는 <xref:System.Windows.Forms.BindingNavigator> 메서드에 해당 하는 탐색에 있는 단추를 제공 하는 컨트롤의 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다. 자세한 내용은 참조 [하는 방법: Windows Forms BindingNavigator 컨트롤을 사용 하 여 데이터 탐색](../../../../docs/framework/winforms/controls/how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingNavigator>  
 [BindingSource 구성 요소 개요](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)  
 [BindingNavigator 컨트롤](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [Windows Forms 데이터 바인딩](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [방법: 형식에 Windows Forms 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 [방법: BindingSource가 있는 Windows Forms 컨트롤에 데이터 소스 업데이트 내용 반영](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)
