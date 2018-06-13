---
title: 사용자 지정 특성 작성
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- multiple attribute instances
- AttributeTargets enumeration
- attributes [.NET Framework], custom
- AllowMultiple property
- custom attributes
- AttributeUsageAttribute class, custom attributes
- Inherited property
- attribute classes, declaring
ms.assetid: 97216f69-bde8-49fd-ac40-f18c500ef5dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 114d24c1fc523d5501deb4aa17f9541c5a918276
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574649"
---
# <a name="writing-custom-attributes"></a>사용자 지정 특성 작성
사용자 지정 특성을 직접 디자인하는 데 새로운 개념을 모두 알 필요는 없습니다. 개체 지향 프로그래밍에 익숙하고 클래스 디자인 방법을 알고 있는 것으로 충분합니다. 사용자 지정 특성은 본래 <xref:System.Attribute?displayProperty=nameWithType>에서 직접 또는 간접적으로 파생된 일반적인 클래스입니다. 일반적인 클래스와 마찬가지로 사용자 지정 특성에도 데이터를 저장하고 검색하는 메서드가 포함되어 있습니다.  
  
 사용자 지정 특성 클래스를 올바르게 디자인하는 기본 단계는 다음과 같습니다.  
  
-   [AttributeUsageAttribute 적용](#cpconapplyingattributeusageattribute)  
  
-   [특성 클래스 선언](#cpcondeclaringattributeclass)  
  
-   [생성자 선언](#cpcondeclaringconstructors)  
  
-   [속성 선언](#cpcondeclaringproperties)  
  
 이 섹션에서는 각 단계에 대해 설명한 다음 마지막으로 [사용자 지정 특성 예제](#cpconcustomattributeexample)를 보여 줍니다.  
  
<a name="cpconapplyingattributeusageattribute"></a>   
## <a name="applying-the-attributeusageattribute"></a>AttributeUsageAttribute 적용  
 사용자 지정 특성을 선언하는 과정은 **AttributeUsageAttribute**를 사용하여 특성 클래스의 주요 특징 일부를 정의하는 것으로 시작됩니다. 예를 들어 다른 클래스에서 특성을 상속할 수 있는지 여부를 지정하거나 해당 특성이 적용될 수 있는 요소를 지정할 수 있습니다. 다음 코드 조각에서는 **AttributeUsageAttribute**의 사용 방법을 보여 줍니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#5)]
 [!code-csharp[Conceptual.Attributes.Usage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#5)]
 [!code-vb[Conceptual.Attributes.Usage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#5)]  
  
 <xref:System.AttributeUsageAttribute?displayProperty=nameWithType>에는 사용자 지정 특성을 만드는 데 필요한 세 가지 멤버인 [AttributeTargets](#cpconwritingcustomattributesanchor1), [Inherited](#cpconwritingcustomattributesanchor2) 및 [AllowMultiple](#cpconwritingcustomattributesanchor3)이 포함되어 있습니다.  
  
<a name="cpconwritingcustomattributesanchor1"></a>   
### <a name="attributetargets-member"></a>AttributeTargets 멤버  
 앞의 예제에는 특성을 모든 프로그램 요소에 적용하는 **AttributeTargets.All** 이 지정되어 있습니다. 또는 특성이 클래스에만 적용되도록 **AttributeTargets.Class**를 지정하거나 특성이 메서드에만 적용되도록 **AttributeTargets.Method**를 지정할 수 있습니다. 이러한 방법으로 사용자 지정 특성을 사용하여 모든 프로그램 요소의 설명을 표시할 수 있습니다.  
  
 또한 <xref:System.AttributeTargets>의 인스턴스를 여러 개 전달할 수도 있습니다. 다음 코드 조각에서는 사용자 지정 특성이 모든 클래스 또는 메서드에 적용되도록 지정합니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#6)]
 [!code-csharp[Conceptual.Attributes.Usage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#6)]
 [!code-vb[Conceptual.Attributes.Usage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#6)]  
  
<a name="cpconwritingcustomattributesanchor2"></a>   
### <a name="inherited-property"></a>Inherited 속성  
 <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> 속성은 특성이 적용된 클래스에서 파생된 클래스가 해당 특성을 상속할 수 있는지 여부를 나타냅니다. 이 특성에는 **true** (기본값) 또는 **false** 플래그가 지정됩니다. 예를 들어 다음 코드 예제에서 `MyAttribute` 의 <xref:System.AttributeUsageAttribute.Inherited%2A> 값은 기본값인 **true**인 반면 `YourAttribute` 의 <xref:System.AttributeUsageAttribute.Inherited%2A> 값은 **false**입니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Attributes.Usage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#7)]
 [!code-vb[Conceptual.Attributes.Usage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#7)]  
  
 이 두 특성은 기본 클래스인 `MyClass`의 메서드에 적용됩니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#9)]
 [!code-csharp[Conceptual.Attributes.Usage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#9)]
 [!code-vb[Conceptual.Attributes.Usage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#9)]  
  
 마지막으로, `YourClass` 클래스가 기본 클래스인 `MyClass`에서 상속됩니다. `MyMethod` 메서드는 `MyAttribute`를 표시하지만 `YourAttribute`는 표시하지 않습니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#10](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#10)]
 [!code-csharp[Conceptual.Attributes.Usage#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#10)]
 [!code-vb[Conceptual.Attributes.Usage#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#10)]  
  
<a name="cpconwritingcustomattributesanchor3"></a>   
### <a name="allowmultiple-property"></a>AllowMultiple 속성  
 <xref:System.AttributeUsageAttribute.AllowMultiple%2A?displayProperty=nameWithType> 속성은 하나의 요소에 대해 특성의 인스턴스가 여러 개 있을 수 있는지 여부를 나타냅니다. **true**로 설정되어 있으면 여러 개의 인스턴스가 있을 수 있으며, **false** (기본값)로 설정되어 있으면 하나의 인스턴스만 있을 수 있습니다.  
  
 다음 예제에서 `MyAttribute` 의 <xref:System.AttributeUsageAttribute.AllowMultiple%2A> 값은 기본값인 **false**인 반면 `YourAttribute` 의 값은 **true**입니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#11)]
 [!code-csharp[Conceptual.Attributes.Usage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#11)]
 [!code-vb[Conceptual.Attributes.Usage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#11)]  
  
 이 특성의 인스턴스가 여러 개 적용되면 `MyAttribute` 에서는 컴파일러 오류가 생성됩니다. 다음 코드 예제에서는 `YourAttribute` 를 올바르게 사용한 경우와 `MyAttribute`를 잘못 사용한 경우를 보여 줍니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#13](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#13)]
 [!code-csharp[Conceptual.Attributes.Usage#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#13)]
 [!code-vb[Conceptual.Attributes.Usage#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#13)]  
  
 <xref:System.AttributeUsageAttribute.AllowMultiple%2A> 속성과 <xref:System.AttributeUsageAttribute.Inherited%2A> 속성이 모두 **true**로 설정된 경우에는 다른 클래스에서 상속된 클래스가 특성을 상속할 수 있으며 동일한 자식 클래스에 적용된 동일한 특성의 다른 인스턴스를 가질 수 있습니다. <xref:System.AttributeUsageAttribute.AllowMultiple%2A> 이 **false**로 설정된 경우에는 자식 클래스에 있는 동일한 특성의 새 인스턴스가 부모 클래스에 있는 모든 특성 값을 덮어씁니다.  
  
<a name="cpcondeclaringattributeclass"></a>   
## <a name="declaring-the-attribute-class"></a>특성 클래스 선언  
 <xref:System.AttributeUsageAttribute>를 적용한 다음 특성을 상세히 정의할 수 있습니다. 특성 클래스를 선언하는 과정은 다음 코드에서처럼 일반적인 클래스를 선언하는 과정과 비슷합니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#14)]
 [!code-csharp[Conceptual.Attributes.Usage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#14)]
 [!code-vb[Conceptual.Attributes.Usage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#14)]  
  
 이 특성 정의는 다음과 같은 몇 가지 점을 보여 줍니다.  
  
-   특성 클래스는 공용 클래스로 선언되어야 합니다.  
  
-   특성 클래스의 이름은 규칙에 따라 **Attribute**로 끝납니다. 이 규칙을 반드시 적용할 필요는 없지만 가독성을 향상시키기 위해 사용하는 것이 좋습니다. 특성이 적용될 때 Attribute라는 단어를 포함시키지 않을 수도 있습니다.  
  
-   모든 특성 클래스는 **System.Attribute**에서 직접 또는 간접적으로 상속해야 합니다.  
  
-   Microsoft VisualBasic에서는 모든 사용자 지정 특성 클래스에 **AttributeUsageAttribute** 특성이 있습니다.  
  
<a name="cpcondeclaringconstructors"></a>   
## <a name="declaring-constructors"></a>생성자 선언  
 특성은 일반적인 클래스와 동일한 방법으로 생성자를 사용하여 초기화됩니다. 다음 코드 조각에서는 일반적인 특성 생성자를 보여 줍니다. 이 공용 생성자는 매개 변수를 적용하여 해당 매개 변수의 값을 멤버 변수와 같은 값으로 설정합니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#15)]
 [!code-csharp[Conceptual.Attributes.Usage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#15)]
 [!code-vb[Conceptual.Attributes.Usage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#15)]  
  
 생성자를 오버로드하여 값을 다르게 조합하여 사용할 수도 있습니다. 또한 사용자 지정 특성 클래스에 대한 [속성](https://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52)을 정의하면 특성을 초기화 할 때 명명된 매개변수와 위치 매개 변수를 함께 사용할 수 있습니다. 일반적으로 모든 필수 매개 변수는 positional로 정의하고 모든 선택적 매개 변수는 named로 정의합니다. 이때 필수 매개 변수가 없으면 특성을 초기화할 수 없습니다. 다른 모든 매개 변수는 선택적 요소입니다. Visual Basic에서는 특성 클래스의 생성자가 ParamArray 인수를 사용할 수 없습니다.  
  
 다음 코드 예제에서는 앞의 생성자를 사용하는 특성이 선택적 매개 변수와 필수 매개 변수를 사용하여 적용되는 방식을 보여 줍니다. 이 예제에서는 특성에 하나의 필수 부울 값과 하나의 선택적 문자열 속성이 있는 것으로 가정합니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#17)]
 [!code-csharp[Conceptual.Attributes.Usage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#17)]
 [!code-vb[Conceptual.Attributes.Usage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#17)]  
  
<a name="cpcondeclaringproperties"></a>   
## <a name="declaring-properties"></a>속성 선언  
 명명된 매개 변수를 정의하거나 특성에 의해 저장된 값을 쉽게 반환하려면 [속성](https://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52)을 선언합니다. 특성 속성은 반환될 데이터 형식에 대한 설명이 포함된 공용 엔터티로 선언되어야 합니다. 속성 값을 포함할 변수를 정의한 다음 이를 **get** 및 **set** 메서드와 연결합니다. 다음 코드 예제에서는 특성에 간단한 속성을 구현하는 방법을 보여 줍니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#16](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#16)]
 [!code-csharp[Conceptual.Attributes.Usage#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#16)]
 [!code-vb[Conceptual.Attributes.Usage#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#16)]  
  
<a name="cpconcustomattributeexample"></a>   
## <a name="custom-attribute-example"></a>사용자 지정 특성 예제  
 이 섹션에서는 앞에서 설명한 내용을 종합하고, 간단한 특성을 디자인하여 코드 섹션의 작성자에 대한 정보를 나타내는 방법에 대해 설명합니다. 이 예제에서 사용된 특성에는 프로그래머의 이름 및 수준과 코드 검토 여부가 저장됩니다. 이 특성은 저장할 실제 값이 포함된 세 개의 private 변수를 사용합니다. 각 변수는 값을 가져오고 설정하는 public 속성으로 표시됩니다. 마지막으로 두 개의 필수 매개 변수를 사용하여 생성자가 정의됩니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#4)]
 [!code-csharp[Conceptual.Attributes.Usage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#4)]
 [!code-vb[Conceptual.Attributes.Usage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#4)]  
  
 전체 이름인 `DeveloperAttribute`나 약식 이름인 `Developer`를 다음 중 한 가지 방법으로 사용하여 이 특성을 적용할 수 있습니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#12)]
 [!code-csharp[Conceptual.Attributes.Usage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#12)]
 [!code-vb[Conceptual.Attributes.Usage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#12)]  
  
 첫 번째 예제에서는 필수 요소인 명명된 매개 변수만 사용하여 적용된 특성을 보여 주고, 두 번째 예제에서는 필수 매개 변수와 선택적 매개 변수를 모두 사용하여 적용된 특성을 보여 줍니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Attribute?displayProperty=nameWithType>  
 <xref:System.AttributeUsageAttribute>  
 [특성](../../../docs/standard/attributes/index.md)
