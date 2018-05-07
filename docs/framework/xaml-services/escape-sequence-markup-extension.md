---
title: '{} 이스케이프 시퀀스-태그 확장'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: a90f6928d68eddd29762e6206769dd7f07704e4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-escape-sequence--markup-extension"></a>{} 이스케이프 시퀀스 / 태그 확장
특성 값에 대 한 XAML 이스케이프 시퀀스를 제공합니다. 이스케이프 시퀀스는 리터럴로 해석 될 특성에 이후 값을 허용 합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a>XAML 속성 요소 사용  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|*LiteralValue*|뒤에 오는 이스케이프 시퀀스는 리터럴 문자열입니다. 일반적으로이 문자열 포함 열기 / 닫기 중괄호 ({또는}).|  
  
## <a name="remarks"></a>설명  
 이스케이프 시퀀스 ({})는 중괄호 ({}) XAML에서 리터럴 문자로 사용할 수 있도록 사용 됩니다.  
  
 일반적으로 XAML 판독기를 태그 확장의 진입점을 나타내는 중괄호 ({})을 사용 합니다; 그러나 다음 문자는 닫는 중괄호 (}) 되는지 확인 하려면 먼저 체크 만 때 두 중괄호 ({}) 인접 한도, 이스케이프 시퀀스를 간주 됩니다.  
  
 이스케이프 시퀀스가 발생 하는 XAML 판독기는 문자열로 서 문자열의 나머지 부분을 처리 해야 합니다. 그러나 이스케이프 시퀀스는 형식 변환기가 멤버에 적용 하는 XAML 작성기에 의해 해석 될 때 문자열 형식 변환을 거쳐야 할 수 있습니다.  
  
 이스케이프 시퀀스는 태그 확장 아니며 클래스에 기반 하지 않습니다. 그러나 하는 XAML 판독기 (사용자 지정 XAML 판독기 포함)을 준수 해야 하는 변환입니다.  
  
 이런이 방식으로 이스케이프 시퀀스로 따옴표 (")를 사용할 수 없습니다. 콘텐츠가 아닌 속성에 대 한 속성 값으로는 따옴표를 설정 해야 속성 요소 구문을 사용 및 property 요소 내의 문자열로 큰따옴표를 배치 하거나 XML 문자 엔터티를 사용 합니다. 콘텐츠 속성의 경우: 따옴표 전체가 될 수 있습니다.  
  
 이스케이프 시퀀스 ({})는 대개 XAML 태그 확장 나타나는 위치에 네임 스페이스 한정자를 포함 해야 하는 XML 형식을 지정 하는 경우 필요 합니다. 이 등호 (=) 후 즉시 시작 XAML 특성 값 및 태그 확장에 포함 됩니다. 다음 예제에서는 XAML 특성 값의 시작 부분에 표시 되는 XML 네임 스페이스에 대 한 이스케이프 시퀀스를 보여 줍니다.  
  
 [!code-xaml[XLINQExample#StackPanelResources](../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a>참고 항목  
 [XAML을 위한 형식 변환기 및 태그 확장명](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)  
 [XML 문자 엔터티 및 XAML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)
