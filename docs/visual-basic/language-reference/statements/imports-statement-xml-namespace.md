---
title: Imports 문(XML 네임스페이스)
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: ba7475416d8a4e2eb3c892d457c03eeb695045eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="imports-statement-xml-namespace"></a>Imports 문(XML 네임스페이스)
XML 리터럴과 XML 축 속성에서 사용 하기 위해 XML 네임 스페이스 접두사를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a>요소  
 `xmlNamespacePrefix`  
 선택 사항입니다. XML 특성과 해당 요소를 참조할 수는 문자열 `xmlNamespaceName`합니다. 하지 않으면 `xmlNamespacePrefix` 은 가져온된 XML 네임 스페이스는 기본 XML 네임 스페이스는 제공 합니다. 유효한 XML 식별자 여야 합니다. 자세한 내용은 참조 [이름을의 선언 된 XML 요소 및 특성](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다.  
  
 `xmlNamespaceName`  
 필수. 가져온 XML 네임 스페이스를 식별 하는 문자열입니다.  
  
## <a name="remarks"></a>설명  
 사용할 수는 `Imports` XML 리터럴과 XML 축 속성 또는에 전달 된 매개 변수로 사용할 수 있는 전역 XML 네임 스페이스를 정의 하는 문에 `GetXmlNamespace` 연산자. (사용 하는 방법에 대 한 정보에 대 한는 `Imports` 코드에서 형식 이름이 사용 되는 위치에 사용할 수 있는 별칭을 가져오려는 문을 참조 [Imports 문 (.NET Namespace 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) 사용 하 여 XML 네임 스페이스를 선언 하기 위한 구문에서 `Imports` 문을 XML에서 사용 하는 구문과 동일 합니다. 따라서 네임 스페이스 선언을 XML 파일에서 복사한에서 사용 하 여 프로그램 `Imports` 문.  
  
 XML 네임 스페이스 접두사는 동일한 네임 스페이스에서 생성 되는 XML 요소를 반복적으로 만들려는 경우 유용 합니다. 으로 선언 된 XML 네임 스페이스 접두사는 `Imports` 문은 모든 코드 파일에서 사용할 수 있다는 점에서 전역적입니다. XML 요소 리터럴 및 XML 축 속성에 액세스할 때 만들 때 사용할 수 있습니다. 자세한 내용은 참조 [XML 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) 및 [XML 축 속성](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)합니다.  
  
 네임 스페이스 접두사가 없는 전역 XML 네임 스페이스를 정의 하는 경우 (예를 들어 `Imports <xmlns="http://SomeNameSpace>"`), 해당 네임 스페이스에는 기본 XML 네임 스페이스 것으로 간주 됩니다. 기본 XML 네임 스페이스는 XML 요소 리터럴 또는 네임 스페이스를 명시적으로 지정 하지 않은 XML 특성 축 속성에 대해 사용 됩니다. 기본 네임 스페이스는 지정된 된 네임 스페이스는 빈 네임 스페이스 하는 경우에 사용 됩니다 (즉, `xmlns=""`). 기본 XML 네임 스페이스는 네임 스페이스가 없는 XML 특성 축 속성 또는 XML 리터럴의 XML 특성에 적용 되지 않습니다.  
  
 XML 네임 스페이스는 리터럴, XML에 정의 된 이라고 하는 *XML 네임 스페이스를 로컬*, XML 네임 스페이스에 정의 된 보다 우선는 `Imports` 전역 2로 문을 합니다. 에 정의 된 XML 네임 스페이스는 `Imports` 문이 Visual Basic 프로젝트에 대 한 가져온 XML 네임 스페이스 보다 우선 합니다. XML 리터럴의 XML 네임 스페이스를 정의 하는 경우 해당 로컬 네임 스페이스는 포함 된 식에 적용 되지 않습니다.  
  
 전역 XML 네임 스페이스는.NET Framework 네임 스페이스와 동일한 범위 지정 및 정의 규칙을 따릅니다. 결과적으로, 포함할 수 있습니다는 `Imports` 전역 XML 네임 스페이스를 정의 하는 문을 아무 곳 이나.NET Framework 네임 스페이스를 가져올 수 있습니다. 코드 파일 및 프로젝트 수준의 가져온된 네임 스페이스를 모두 포함 합니다. 프로젝트 수준 가져온된 네임 스페이스에 대 한 정보를 참조 하십시오. [참조 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)합니다.  
  
 각 소스 파일에는 개수에 관계 없이 포함 될 수 있습니다 `Imports` 문. 이러한 옵션 선언 같은 따라야는 `Option Strict` 문 및 이러한 앞에 야 프로그래밍 요소 선언 같은 `Module` 또는 `Class` 문.  
  
## <a name="example"></a>예제  
 다음 예제에서는 기본 XML 네임 스페이스와 XML 네임 스페이스 접두사와 함께 식별 된 `ns`합니다. 그런 다음 두 네임 스페이스를 사용 하는 XML 리터럴을 만듭니다.  
  
 [!code-vb[VbXMLSamples#45](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
```xml  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## <a name="example"></a>예제  
 다음 예에서는 XML 네임 스페이스 접두사를 가져옵니다 `ns`합니다. 그런 다음 네임 스페이스 접두사를 사용 하 고 요소의 최종 폼을 표시 하는 XML 리터럴을 만듭니다.  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 컴파일러가 변환 함을 XML 네임 스페이스 접두사를 전역 접두사에서 로컬 접두사 정의 확인 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 XML 네임 스페이스 접두사를 가져옵니다 `ns`합니다. 네임스페이스의 접두사를 사용하여 XML 리터럴을 만들고 정규화된 이름 `ns:name`을 가진 첫 번째 자식 노드에 액세스합니다.  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>참고 항목  
 [XML 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML 축 속성](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [선언된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [GetXmlNamespace 연산자](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
