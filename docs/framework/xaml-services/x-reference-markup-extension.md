---
title: "x:Reference 태그 확장명"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03b63cb40e57223d5c66c03fb60780689cd6c925
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="xreference-markup-extension"></a>x:Reference 태그 확장명
XAML 태그에 선언 된 인스턴스를 참조 합니다. 요소의 참조 `x:Name`합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xaml  
<object property="{x:Reference instancexName}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>XAML 개체 요소 사용  
  
```xaml  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`instancexName`|`x:Name` 값 (또는 값의는 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-식별 된 속성) 참조 된 인스턴스.|  
  
## <a name="remarks"></a>설명  
 `x:Reference`WPF와 같은 특정 프레임 워크에서 구현 된 요소 참조 개념에 대 한 XAML 언어 수준 지원을 제공 합니다.  
  
## <a name="xreference-and-wpf"></a>X:reference 및 WPF  
 WPF 및 XAML 2006에서는 요소 참조의 프레임 워크 수준 기능에 의해 해결 <xref:System.Windows.Data.Binding.ElementName%2A> 바인딩. 대부분의 WPF 응용 프로그램과 시나리오에 대 한 <xref:System.Windows.Data.Binding.ElementName%2A> 바인딩을 사용 해야 합니다. 이 일반 지침에 대 한 예외 데이터 컨텍스트 또는 데이터 바인딩 불가능할 수 있는 기타 영역 지정 고려 사항 하 고 태그 컴파일에 포함 되지 않은 경우 포함할 수 있습니다.  
  
 `x:Reference`XAML 2009에서 정의 된 구문입니다. WPF에서 XAML 2009 기능을 사용할 수 있지만 WPF 태그 컴파일된 XAML에만 사용할 수 있습니다. 태그 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 언어 키워드 및 기능을 지원하지 않습니다.
