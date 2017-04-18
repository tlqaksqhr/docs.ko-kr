---
title: "x:Array Markup Extension | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "x:Array"
  - "xArray"
helpviewer_keywords: 
  - "x:Array [XAML Services]"
  - "XAML [XAML Services], x:Array markup extension"
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
caps.latest.revision: 20
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 20
---
# x:Array Markup Extension
태그 확장을 통해 XAML에서 개체의 배열에 대한 일반 지원을 제공합니다.  이는 \[MS\-XAML\]에서 `x:ArrayExtension` XAML 형식에 해당합니다.  
  
## XAML 개체 요소 사용  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`typeName`|`x:Array`가 포함할 형식 이름입니다.  `typeName`은 XAML 형식 정의가 포함된 XAML 네임스페이스에 대한 접두사가 될 수 있습니다.|  
|`arrayContents`|내장 `ArrayExtension.Items` 속성에 할당된 항목 내용입니다.  일반적으로 이러한 항목은 열고 닫는 태그가 `x:Array` 내에 포함된 하나 이상의 개체 요소로 지정되어 있습니다.  여기에 지정된 개체는 `typeName`에 지정된 XAML 형식에 할당될 것으로 예상됩니다.|  
  
## 설명  
 `Type`은 모든 `x:Array` 개체 요소의 필수 특성입니다.  `Type` 매개 변수 값은 `x:Type` 태그 확장을 사용할 필요가 없습니다. 스타일의 약식 이름은 문자열로 지정할 수 있는 XAML 형식입니다.  
  
 .NET Framework XAML 서비스 구현에서 만들어진 배열의 입력 XAML 형식과 출력 CLR <xref:System.Type> 사이의 관계는 태그 확장을 위해 제공되는 서비스 컨텍스트에 따라 영향을 받습니다.  XAML 스키마 컨텍스트와 컨텍스트가 제공하는 <xref:System.Windows.Markup.IXamlTypeResolver> 서비스를 기반으로 필요한 <xref:System.Xaml.XamlType>을 찾은 후 출력 <xref:System.Type>은 입력 XAML 형식의 <xref:System.Xaml.XamlType.UnderlyingType%2A>입니다.  
  
 처리할 때 배열 내용이 `ArrayExtension.Items` 내장 속성에 할당됩니다.  <xref:System.Windows.Markup.ArrayExtension> 구현에서는 <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=fullName>에 의해 표현됩니다.  
  
 .NET Framework XAML 서비스 구현에서 이 태그 확장에 대한 처리는 <xref:System.Windows.Markup.ArrayExtension> 클래스를 통해 정의됩니다.  <xref:System.Windows.Markup.ArrayExtension>은 sealed 클래스가 아니며 사용자 지정 배열 형식에 대한 태그 확장 구현의 기본으로 사용될 수 있습니다.  
  
 `x:Array`는 XAML의 일반 언어 확장에 주로 사용됩니다.  그러나 `x:Array`는 XAML 지원 컬렉션을 구조화된 속성 콘텐츠로 사용하는 특정 속성의 XAML 값을 지정하는 데도 유용합니다.  예를 들어, `x:Array` 사용을 가진 <xref:System.Collections.IEnumerable> 속성의 내용을 지정할 수 있습니다.  
  
 `x:Array`은 태그 확장입니다.  태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다.  `x:Array`는 부분적으로 특성 값 처리를 제공하는 대신 `x:Array`는 내부 텍스트 내용의 대체 처리를 제공하기 때문에 해당 규칙의 예외입니다.  이 동작을 통해 기존 콘텐츠 모델을 통해 지원할 수 없는 형식을 배열로 그룹화한 후 이 명명된 배열에 액세스하고 코드 숨김으로 나중에 참조할 수 있습니다. 사용자는 <xref:System.Array> 메서드를 호출하여 개별 배열 항목을 가져올 수 있습니다.  
  
 XAML의 모든 태그 확장은 특성 구문에 중괄호 \({,}`)`를 사용하며 여기서 특성 구문은 XAML 프로세서가 태그 확장이 특성을 처리해야 함을 인식하는 데 사용하는 규칙입니다.  태그 확장에 대한 자세한 내용은 [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)을 참조하십시오.  
  
 XAML 2009에서 `x:Array`는 태그 확장이 아닌 언어 기본 형식으로 정의됩니다.  자세한 내용은 [Built\-in Types for Common XAML Language Primitives](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)를 참조하십시오.  
  
## WPF 사용 정보  
 일반적으로 `x:Array`를 채우는 개체 요소는 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XML 네임스페이스에 포함된 요소가 아니기 때문에 기본이 아닌 XAML 네임스페이스에 접두사 매핑이 필요합니다.  
  
 예를 들어 다음은 문자열 두 개를 포함하고 배열 수준에 `sys` 접두사와 `x`가 정의된 간단한 배열입니다.  
  
 \[xaml\]  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 배열 요소로 사용되는 사용자 지정 형식의 경우 클래스는 XAML에서 개체 요소로 인스턴스화되기 위한 요구 사항도 지원해야 합니다.  자세한 내용은 [WPF에 대한 XAML 및 사용자 지정 클래스](../../../ocs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)를 참조하십시오.  
  
## 참고 항목  
 [태그 확장 및 WPF XAML](../../../ocs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Types Migrated from WPF to System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)