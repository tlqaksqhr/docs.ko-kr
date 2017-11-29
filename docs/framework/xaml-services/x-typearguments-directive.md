---
title: "x:TypeArguments 지시문"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
caps.latest.revision: "18"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: a63a8080c71ad026664e2e14fc1762fcdd4bdb36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xtypearguments-directive"></a>x:TypeArguments 지시문
제네릭 형식의 생성자에 제네릭의 인수를 입력 하는 전달 합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`object`|CLR 제네릭 형식에 의해 지원 되는 XAML 형식의 개체 요소 선언 합니다. 경우 `object` 아니라 기본 XAML 네임 스페이스는 XAML 형식을 참조 `object` XAML 네임 스페이스를 나타내기 위해 접두사가 필요 여기서 `object` 존재 합니다.|  
|`typeString`|하나 이상의 XAML을 선언 하는 문자열 형식 이름을 문자열로, CLR 제네릭 형식에 대 한 형식 인수를 제공 하는 합니다. 자세한 구문 정보에 대 한 설명을 참조 하세요.|  
  
## <a name="remarks"></a>설명  
 대부분의 경우에 정보 항목으로 사용 되는 XAML 형식은 `typeString` 문자열 접두사. 일반적인 유형의 CLR 제네릭 제약 조건 (예를 들어 <xref:System.Int32> 및 <xref:System.String>) CLR 기본 클래스 라이브러리에서 제공 합니다. 이러한 라이브러리 일반적인에 매핑된 프레임 워크 관련 기본 XAML 네임 스페이스 않으며 하므로 접두사 매핑이 XAML 사용을 위해 필요 합니다.  
  
 쉼표 구분 기호를 사용 하 여 XAML 형식 이름을 여러 개 지정할 수 있습니다.  
  
 제네릭 제약 조건 자체가 제네릭 형식을 사용 하는 경우 중첩 된 제약 조건 형식 인수는 괄호 ()에 포함 될 수입니다.  
  
 이 정의의 `x:TypeArguments` 은.NET Framework XAML 서비스에 국한 되며 CLR 지원을 사용 하 여 합니다. 언어 수준 정의에서 찾을 수 있습니다 [ \[MS-XAML\] 섹션 5.3.11](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.  
  
## <a name="usage-examples"></a>사용 예제  
 이러한 예제를 보려면 다음 XAML 네임 스페이스 정의 선언 된 가정 합니다.  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a>목록\<문자열 >  
 `<scg:List x:TypeArguments="sys:String" ...>`새 인스턴스화합니다 <xref:System.Collections.Generic.List%601> 와 <xref:System.String> 인수를 입력 합니다.  
  
### <a name="dictionarystringstring"></a>사전\<문자열, 문자열 >  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`새 인스턴스화합니다 <xref:System.Collections.Generic.Dictionary%602> 두 개의 <xref:System.String> 인수를 입력 합니다.  
  
### <a name="queuekeyvaluepairstringstring"></a>큐 < KeyValuePair\<String, String >>  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`새 인스턴스화합니다 <xref:System.Collections.Generic.Queue%601> 의 제한 사항은 있는 <xref:System.Collections.Generic.KeyValuePair%602> 내부 제약 조건 형식 인수를 사용 <xref:System.String> 및 <xref:System.String>합니다.  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>XAML 2006 및 WPF XAML 제네릭 사용  
 XAML 2006 사용 및 WPF 응용 프로그램에 사용 되는 XAML에 대 한 다음과 같은 제한 사항이 `x:TypeArguments` 및 일반적으로 XAML 제네릭 형식 사용:  
  
-   XAML 파일의 루트 요소에만 제네릭 형식을 참조 하는 일반 XAML 사용을 지원할 수 있습니다.  
  
-   루트 요소는 하나 이상의 형식 인수가 있는 제네릭 형식에 매핑되어야 합니다. 예로 <xref:System.Windows.Navigation.PageFunction%601>합니다. 페이지 함수에는 WPF의 XAML 제네릭 사용 지원에 대 한 주요 시나리오는입니다.  
  
-   제네릭에 대 한 루트 요소 XAML 개체 요소 사용 하 여 partial 클래스 선언 해야 `x:Class`합니다. 빌드 작업 WPF를 정의 하는 경우에 마찬가지입니다.  
  
-   `x:TypeArguments`중첩 된 제네릭 제약을 참조할 수 없습니다.  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 또는 WPF 3.0 또는 3.5 WPF 없는 XAML 2006 종속성  
 .NET Framework XAML 서비스 XAML 2006 또는 XAML 2009에서의 일반 XAML 사용에 대 한 WPF 관련 제한 완화 됩니다. 제네릭 개체 지원 형식 시스템 및 개체 모델을 지원할 수 있는 XAML 태그의 위치에 요소를 인스턴스화할 수 있습니다.  
  
 XAML 2009를 사용 하면 CLR 매핑하는 대신 기본 공용 언어 기본 형식에 대 한 XAML 형식을 가져올 형식을 사용할 수 있습니다 [일반 XAML 언어 기본 형식에 대 한 기본 제공 형식](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) 의 정보 항목으로는 `typeString`합니다. 예를 들어, 다음에 선언할 수 있습니다 (접두사 매핑이 표시 되지 않지만 x는 XAML 언어 XAML 네임 스페이스에 대 한 XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 Wpf에서 및 대상으로 할 때 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]와 함께 XAML 2009 기능을 사용할 수 있습니다 `x:TypeArguments` 느슨한 XAML (태그 컴파일되지 않은 XAML)에 대해서만 합니다. WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다. 태그로 XAML을 컴파일해야 하는 경우에 "XAML 2006 and WPF 일반 XAML 사용" 섹션에서 설명한 제한에서 작동 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [x:Class 지시문](../../../docs/framework/xaml-services/x-class-directive.md)  
 [x:Type 태그 확장](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [공용 XAML 언어 기본 형식에 대한 기본 제공 형식](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)  
 [XAML의 제네릭](../../../docs/framework/xaml-services/generics-in-xaml.md)
