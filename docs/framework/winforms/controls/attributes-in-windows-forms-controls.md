---
title: "Windows Forms 컨트롤의 특성 | Microsoft Docs"
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
  - "특성[Windows Forms]"
  - "특성[Windows Forms], 클래스"
  - "특성[Windows Forms], 컨트롤 속성"
  - "특성[Windows Forms], 데이터 바인딩 속성"
ms.assetid: 2c5640e9-6c6c-49d7-a5e4-a768f6be7853
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Windows Forms 컨트롤의 특성
.NET Framework에서는 사용자 지정 컨트롤 및 구성 요소의 멤버에 적용할 수 있는 다양한 특성을 제공합니다.  이러한 특성 중 일부는 클래스의 런타임 동작에 영향을 주고 일부는 디자인 타임 동작에 영향을 줍니다.  
  
## 컨트롤 및 구성 요소 속성의 특성  
 다음 표에서는 속성이나 사용자 지정 컨트롤 및 구성 요소의 속성이나 기타 멤버에 적용할 수 있는 특성을 보여 줍니다.  이러한 특성을 사용하는 예제는 [방법: Windows Forms 컨트롤에서 특성 적용](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)을 참조하십시오.  
  
|특성|설명|  
|--------|--------|  
|<xref:System.ComponentModel.AmbientValueAttribute>|속성이 다른 소스에서 값을 가져오도록 속성에 전달할 값을 지정합니다.  이를 *앰비언스*라고 합니다.|  
|<xref:System.ComponentModel.BrowsableAttribute>|속성 또는 이벤트를 **속성** 창에 표시할지 여부를 지정합니다.|  
|<xref:System.ComponentModel.CategoryAttribute>|<xref:System.Windows.Forms.PropertySort> 모드로 설정된 <xref:System.Windows.Forms.PropertyGrid> 컨트롤에 표시되는 속성 또는 이벤트를 그룹화할 범주 이름을 지정합니다.|  
|<xref:System.ComponentModel.DefaultValueAttribute>|속성의 기본값을 지정합니다.|  
|<xref:System.ComponentModel.DescriptionAttribute>|속성 또는 이벤트에 대한 설명을 지정합니다.|  
|<xref:System.ComponentModel.DisplayNameAttribute>|인수가 없는 속성, 이벤트 또는 `public` `void` 메서드에 대한 표시 이름을 지정합니다.|  
|<xref:System.ComponentModel.EditorAttribute>|속성을 변경하는 데 사용할 편집기를 지정합니다.|  
|<xref:System.ComponentModel.EditorBrowsableAttribute>|속성 또는 메서드가 편집기에 표시되도록 지정합니다.|  
|<xref:System.ComponentModel.Design.HelpKeywordAttribute>|클래스나 멤버의 컨텍스트 키워드를 지정합니다.|  
|<xref:System.ComponentModel.LocalizableAttribute>|속성을 지역화할 수 있는지 여부를 지정합니다.|  
|<xref:System.ComponentModel.PasswordPropertyTextAttribute>|개체의 텍스트 표시가 별표와 같은 문자로 가려짐을 나타냅니다.|  
|<xref:System.ComponentModel.ReadOnlyAttribute>|이 특성이 바인딩되는 속성이 디자인 타임에 읽기 전용인지 읽기\/쓰기인지 여부를 지정합니다.|  
|<xref:System.ComponentModel.RefreshPropertiesAttribute>|연결된 속성 값이 변경될 경우 속성 표를 새로 고쳐야함을 나타냅니다.|  
|<xref:System.ComponentModel.TypeConverterAttribute>|이 특성이 바인딩되는 개체에 대한 변환기로 사용할 형식을 지정합니다.|  
  
## 데이터 바인딩 속성의 특성  
 다음 표에서는 사용자 지정 컨트롤 및 구성 요소가 데이터 바인딩과 상호 작용하는 방법을 지정할 때 적용할 수 있는 특성을 보여 줍니다.  
  
|특성|설명|  
|--------|--------|  
|<xref:System.ComponentModel.BindableAttribute>|속성이 바인딩에 일반적으로 사용되는지 여부를 지정합니다.|  
|<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|구성 요소의 데이터 소스와 데이터 멤버 속성을 지정합니다.|  
|<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|구성 요소의 기본 바인딩 속성을 지정합니다.|  
|<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|구성 요소의 데이터 소스와 데이터 멤버 속성을 지정합니다.|  
|<xref:System.ComponentModel.AttributeProviderAttribute>|특성 리디렉션을 활성화합니다.|  
  
## 클래스의 특성  
 다음 표에서는 디자인 타임에 사용자 지정 컨트롤 및 구성 요소의 동작을 지정할 때 적용할 수 있는 특성을 보여 줍니다.  
  
|특성|설명|  
|--------|--------|  
|<xref:System.ComponentModel.DefaultEventAttribute>|구성 요소의 기본 이벤트를 지정합니다.|  
|<xref:System.ComponentModel.DefaultPropertyAttribute>|구성 요소의 기본 속성을 지정합니다.|  
|<xref:System.ComponentModel.DesignerAttribute>|구성 요소에 대한 디자인 타임 서비스를 구현하는 데 사용되는 클래스를 지정합니다.|  
|<xref:System.ComponentModel.DesignerCategoryAttribute>|클래스의 디자이너가 특정 범주에 속하도록 지정합니다.|  
|<xref:System.ComponentModel.ToolboxItemAttribute>|도구 상자 항목의 특성을 나타냅니다.|  
|<xref:System.ComponentModel.ToolboxItemFilterAttribute>|도구 상자 항목에 사용할 필터 문자열과 필터 형식을 지정합니다.|  
  
## 참고 항목  
 <xref:System.Attribute>   
 [방법: Windows Forms 컨트롤에서 특성 적용](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)   
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)   
 [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)