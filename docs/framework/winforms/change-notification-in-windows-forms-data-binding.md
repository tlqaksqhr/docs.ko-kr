---
title: "Windows Forms 데이터 바인딩의 변경 알림"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, data binding
- Windows Forms, adding change notification for data binding
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 827e93ad779dfeb2dd398a2fc031fcb99a77a39c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="change-notification-in-windows-forms-data-binding"></a>Windows Forms 데이터 바인딩의 변경 알림
Windows Forms 데이터 바인딩의 가장 중요 한 개념 중 하나인 *변경 알림*합니다. 데이터 소스와 바인딩된 컨트롤 항상 최신 데이터를 갖도록 하려면 데이터 바인딩에 대 한 변경 알림을 추가 해야 합니다. 특히 바인딩된 컨트롤의 데이터 소스에 대 한 변경 내용이 통보 되 있는지 확인 하려는 및 데이터 소스 컨트롤의 바인딩된 속성에 대 한 변경 내용을 알려 줍니다.  
  
 서로 다른 종류의 데이터 바인딩에 따라 변경 알림 있습니다.  
  
-   컨트롤 속성은 개체의 단일 인스턴스에 바인딩하는 단순 바인딩.  
  
-   목록 기반 바인딩, 컨트롤 속성 또는 목록에 있는 항목의 속성에 바인딩된 컨트롤 속성을 포함할 수 있는 개체의 목록에 바인딩됩니다.  
  
 또한 데이터 바인딩을 사용 하려면 Windows Forms 컨트롤을 만들면 적용 해야는 *PropertyName*패턴 컨트롤에 변경 하는 컨트롤의 바인딩된 속성에 대 한 변경 내용이 전파 되도록는 데이터 원본입니다.  
  
## <a name="change-notification-for-simple-binding"></a>간단한 바인딩에 대 한 변경 알림  
 단순 바인딩이 바인딩된 속성의 값이 변경 될 때 비즈니스 개체 변경 알림을 제공 해야 합니다. 노출 하 여이 작업을 수행할 수는 *PropertyName*비즈니스 개체 및 사용 하 여 컨트롤에 비즈니스 개체를 바인딩의 각 속성에 대 한 Changed 이벤트는 <xref:System.Windows.Forms.BindingSource> 또는 선호 되는 비즈니스 개체를 구현 하는 방법 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스와 발생 한 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 속성의 값이 변경 될 때 이벤트입니다. 자세한 내용은 참조 [하는 방법: INotifyPropertyChanged 인터페이스 구현](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)합니다. 구현 하는 개체를 사용 하는 경우는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 않아도 사용 하는 <xref:System.Windows.Forms.BindingSource> 개체를 컨트롤에 바인딩할 하지만 사용 하 여는 <xref:System.Windows.Forms.BindingSource> 것이 좋습니다.  
  
## <a name="change-notification-for-list-based-binding"></a>목록 기반 바인딩에 대 한 변경 알림  
 Windows Forms 속성 변경 (목록 항목 속성 값 변경)를 제공 하는 바인딩된 목록 및 목록 변경에 따라 달라 집니다 (항목이 삭제 되거나 목록에 추가) 정보를 바인딩된 컨트롤입니다. 데이터 바인딩에 사용 되는 목록 이므로 구현 해야 합니다는 <xref:System.ComponentModel.IBindingList>, 두 가지 유형의 변경 알림 제공 합니다. <xref:System.ComponentModel.BindingList%601> 의 일반 구현 <xref:System.ComponentModel.IBindingList> Windows Forms 데이터 바인딩과 함께 사용 하기 위해 디자인 되었습니다. 만들 수 있습니다는 <xref:System.ComponentModel.BindingList%601> 구현 하는 비즈니스 개체 유형을 포함 하는 <xref:System.ComponentModel.INotifyPropertyChanged> 목록에서 자동으로 변환 하 고는 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트를 <xref:System.ComponentModel.IBindingList.ListChanged> 이벤트입니다. 바인딩된 목록이 아닌 경우는 <xref:System.ComponentModel.IBindingList>를 사용 하 여 Windows Forms 컨트롤에 개체 목록이 바인딩해야 합니다는 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다. <xref:System.Windows.Forms.BindingSource> 구성 요소 속성 목록 변환의 기능과 유사 제공할 됩니다는 <xref:System.ComponentModel.BindingList%601>합니다. 자세한 내용은 참조 [하는 방법: BindingSource와 INotifyPropertyChanged 인터페이스를 사용 하 여 변경 알림 발생](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)합니다.  
  
## <a name="change-notification-for-custom-controls"></a>사용자 지정 컨트롤에 대 한 변경 알림  
 마지막으로, 컨트롤에서 표시 해야는 *PropertyName*Changed 이벤트 데이터에 바인딩될 수 있도록 각 속성에 대 한 합니다. 바인딩된 데이터 소스에 컨트롤 속성에 변경 내용이 전파 됩니다. 자세한 내용은 참조 [하는 방법: PropertyNameChanged 패턴 적용](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.ComponentModel.INotifyPropertyChanged>  
 <xref:System.ComponentModel.BindingList%601>  
 [Windows Forms 데이터 바인딩](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Windows Forms에서 지원하는 데이터 소스](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 [데이터 바인딩 및 Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
