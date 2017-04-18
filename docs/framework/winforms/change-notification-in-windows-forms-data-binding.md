---
title: "Windows Forms 데이터 바인딩의 변경 알림 | Microsoft Docs"
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
  - "Windows Forms, 데이터 바인딩에 대한 변경 알림 추가"
  - "Windows Forms, 데이터 바인딩"
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Windows Forms 데이터 바인딩의 변경 알림
Windows Forms 데이터 바인딩의 가장 중요한 개념 중 하나는 *변경 알림*입니다.  데이터 소스 및 바인딩된 컨트롤에 항상 최신 데이터가 유지되도록 하려면 데이터 바인딩에 대한 변경 알림을 추가해야 합니다.  특히, 바인딩된 컨트롤에는 해당 데이터 소스의 변경을 알리고 데이터 소스에는 컨트롤의 바인딩된 속성의 변경을 알려야 합니다.  
  
 변경 알림에는 데이터 바인딩의 유형에 따라 여러 종류가 있습니다.  
  
-   단순 바인딩 \- 컨트롤 속성 하나가 개체의 단일 인스턴스에 바인딩됩니다.  
  
-   목록 기반 바인딩 \- 개체 목록에 바인딩된 컨트롤 속성 또는 목록의 항목 속성에 바인딩된 단일 컨트롤 속성을 포함할 수 있습니다.  
  
 또한 데이터 바인딩에 사용하려는 Windows Forms 컨트롤을 만드는 경우 컨트롤의 바인딩된 속성에 대한 변경 내용이 데이터 소스에 전파될 수 있도록 *PropertyName*Changed 패턴을 이 컨트롤에 적용해야 합니다.  
  
## 단순 바인딩에 대한 변경 알림  
 단순 바인딩의 경우 바인딩된 속성의 값이 변경되면 비즈니스 개체가 변경 알림을 제공해야 합니다.  이를 수행하려면 비즈니스 개체의 각 속성에 대한 *PropertyName*Changed 이벤트를 노출하고 <xref:System.Windows.Forms.BindingSource>를 사용하여 비즈니스 개체를 컨트롤에 바인딩합니다. 비즈니스 개체에서 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현하고 속성 값이 변경되면 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트를 발생시키는 메서드를 이 바인딩에 사용할 수도 있습니다.  자세한 내용은 [방법: INotifyPropertyChanged 인터페이스 구현](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)을 참조하십시오.  <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현하는 개체를 사용할 때는 <xref:System.Windows.Forms.BindingSource>를 사용하여 개체를 컨트롤에 바인딩할 필요가 없지만 가능하면 <xref:System.Windows.Forms.BindingSource>를 사용하는 것이 좋습니다.  
  
## 목록 기반 바인딩에 대한 변경 알림  
 Windows Forms에서는 바인딩된 목록을 통해 속성 변경\(목록 항목의 속성 값 변경\) 및 목록 변경\(목록에서 항목 삭제 또는 추가\) 정보를 바인딩된 컨트롤에 제공합니다.  따라서 데이터 바인딩에 사용되는 목록은 <xref:System.ComponentModel.IBindingList>를 구현하여 두 가지 변경 알림 형식을 모두 제공해야 합니다.  <xref:System.ComponentModel.BindingList%601>은 <xref:System.ComponentModel.IBindingList>의 제네릭 구현이며 Windows Forms 데이터 바인딩에 사용하도록 디자인되었습니다.  <xref:System.ComponentModel.INotifyPropertyChanged>를 구현하는 비즈니스 개체 형식이 포함된 <xref:System.ComponentModel.BindingList%601>을 만들 수 있습니다. 이 경우 목록에서 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트가 <xref:System.ComponentModel.IBindingList.ListChanged> 이벤트로 자동 변환됩니다.  바인딩된 목록이 <xref:System.ComponentModel.IBindingList>가 아닌 경우에는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 개체 목록을 Windows Forms 컨트롤에 바인딩해야 합니다.  <xref:System.Windows.Forms.BindingSource> 구성 요소는 <xref:System.ComponentModel.BindingList%601>의 경우와 비슷하게 속성을 목록으로 변환합니다.  자세한 내용은 [방법: BindingSource와 INotifyPropertyChanged 인터페이스를 사용하여 변경 내용 알림 발생](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)을 참조하십시오.  
  
## 사용자 지정 컨트롤에 대한 변경 알림  
 마지막으로, 데이터에 바인딩되도록 디자인된 각 속성에 대해 *PropertyName*Changed 이벤트를 컨트롤측에서 노출해야 합니다.  이렇게 하면 컨트롤 속성에 대한 변경 내용이 바인딩된 데이터 소스에 전파됩니다.  자세한 내용은 [방법: PropertyNameChanged 패턴 적용](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.ComponentModel.INotifyPropertyChanged>   
 <xref:System.ComponentModel.BindingList%601>   
 [Windows Forms 데이터 바인딩](../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Windows Forms에서 지원하는 데이터 소스](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)   
 [데이터 바인딩 및 Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)