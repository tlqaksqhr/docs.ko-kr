---
title: "Windows Forms 데이터 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 60a9f66fec64ceda71dd5b70211b897c84113429
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="windows-forms-data-binding"></a>Windows Forms 데이터 바인딩
Windows Forms의 데이터 바인딩은 폼의 컨트롤에서 데이터 소스의 정보를 표시하고 변경하는 방법을 제공합니다. 기존의 데이터 소스뿐 아니라 데이터를 포함하는 거의 모든 구조에 바인딩할 수 있습니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [데이터 바인딩 및 Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 Windows Forms의 데이터 바인딩에 대한 개요를 제공합니다.  
  
 [Windows Forms에서 지원하는 데이터 소스](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 Windows Forms에서 사용할 수 있는 데이터 소스를 설명합니다.  
  
 [데이터 바인딩과 관련된 인터페이스](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 Windows Forms 데이터 바인딩과 함께 사용되는 여러 인터페이스를 설명합니다.  
  
 [방법: Windows Forms에서 데이터 탐색](../../../docs/framework/winforms/how-to-navigate-data-in-windows-forms.md)  
 데이터 소스의 항목을 탐색하는 방법을 보여 줍니다.  
  
 [Windows Forms 데이터 바인딩의 변경 알림](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 Windows Forms 데이터 바인딩에 대한 다양한 유형의 변경 알림을 설명합니다.  
  
 [방법: INotifyPropertyChanged 인터페이스 구현](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현하는 방법을 보여 줍니다. 인터페이스는 비즈니스 개체의 속성 변경 내용을 바인딩된 컨트롤에 전달합니다.  
  
 [방법: PropertyNameChanged 패턴 적용](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 적용 하는 방법을 보여 줍니다.는 *PropertyName*패턴을 Windows Forms 사용자 정의 컨트롤의 속성입니다.  
  
 [방법: ITypedList 인터페이스 구현](../../../docs/framework/winforms/how-to-implement-the-itypedlist-interface.md)  
 <xref:System.ComponentModel.ITypedList> 인터페이스를 구현하여 바인딩 가능한 목록에 대한 스키마 검색을 사용하는 방법을 보여 줍니다.  
  
 [방법: IListSource 인터페이스 구현](../../../docs/framework/winforms/how-to-implement-the-ilistsource-interface.md)  
 <xref:System.ComponentModel.IListSource> 인터페이스를 구현하여 <xref:System.Collections.IList>를 구현하지 않지만 다른 위치에서 목록을 제공하는 바인딩 가능한 클래스를 만드는 방법을 보여 줍니다.  
  
 [방법: 동일한 데이터 소스에 바인딩된 여러 컨트롤의 동기화 상태가 유지되도록 설정](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)  
 <xref:System.Windows.Forms.BindingSource.BindingComplete> 이벤트를 처리하여 데이터 소스에 바인딩된 모든 컨트롤의 동기화 상태가 유지되도록 하는 방법을 보여 줍니다.  
  
 [방법: 자식 테이블에서 선택된 행이 올바른 위치에 유지되도록 설정](../../../docs/framework/winforms/ensure-the-selected-row-in-a-child-table-correct.md)  
 부모 테이블의 필드가 변경될 때 자식 테이블의 선택된 행이 변경되지 않도록 하는 방법을 보여 줍니다.  
  
 또한 참조 [인터페이스와 관련 된 데이터 바인딩](http://msdn.microsoft.com/library/41e17s4b\(v=vs.110\)), [하는 방법: Windows Forms에서 데이터 이동](http://msdn.microsoft.com/library/b63ha24w\(v=vs.110\)), [하는 방법: Windows Form에 단순 바인딩된 컨트롤 만들기](http://msdn.microsoft.com/library/sw223a62\(v=vs.110\))합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 바인딩 가능한 구성 요소와 데이터 소스 간의 바인딩을 나타내는 클래스를 설명합니다.  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 컨트롤에 바인딩하기 위해 데이터 소스를 캡슐화하는 클래스를 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [BindingSource 구성 요소](../../../docs/framework/winforms/controls/bindingsource-component.md)  
 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하는 방법을 보여 주는 항목 목록을 포함합니다.  
  
 [DataGridView 컨트롤](../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 바인딩 가능한 datagrid 컨트롤을 사용하는 방법을 보여 주는 항목 목록을 제공합니다.  
  
 또한 참조 [Visual Studio의 데이터 액세스](/visualstudio/data-tools/accessing-data-in-visual-studio)합니다.
