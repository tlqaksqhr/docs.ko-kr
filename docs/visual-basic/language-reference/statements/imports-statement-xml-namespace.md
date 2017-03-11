---
title: "Imports Statement (XML Namespace) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ImportsXmlns"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML namespace [Visual Basic], importing"
  - "imports [Visual Basic]"
  - "Imports statement [Visual Basic]"
  - "namespaces [Visual Basic], importing"
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Imports Statement (XML Namespace)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

XML 리터럴 및 XML 축 속성에 사용할 XML 네임스페이스 접두사를 가져옵니다.  
  
## 구문  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## 요소  
 `xmlNamespacePrefix`  
 선택적 요소.  XML 요소 및 특성은 `xmlNamespaceName`을 참조할 수 있는 문자열입니다.  `xmlNamespacePrefix`를 제공하지 않으면 가져온 XML 네임스페이스가 기본 XML 네임스페이스가 됩니다.  올바른 XML 식별자여야 합니다.  자세한 내용은 [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)를 참조하십시오.  
  
 `xmlNamespaceName`  
 필수 요소.  가져올 XML 네임스페이스를 식별하는 문자열입니다.  
  
## 설명  
 `Imports` 문을 사용하여 XML 리터럴 및 XML 축 속성과 함께 사용하거나 `GetXmlNamespace` 연산자로 전달되는 매개 변수로 사용할 수 있는 전역 XML 네임스페이스를 정의할 수 있습니다.  `Imports` 문을 사용하여 사용자 코드에서 형식 이름이 사용되는 곳에 사용될 수 있는 별칭을 가져오는 것에 대한 자세한 내용은 [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하십시오. `Imports` 문을 사용하여 XML 네임스페이스를 선언하는 구문은 XML에서 사용되는 구문과 동일합니다.  따라서 XML 파일의 네임스페이스 선언을 복사하여 `Imports` 문에 사용할 수 있습니다.  
  
 XML 네임스페이스 접두사는 같은 네임스페이스의 XML 요소를 반복적으로 만들고자 할 때 유용합니다.  `Imports` 문을 사용하여 선언된 XML 네임스페이스 접두사는 파일의 모든 코드에서 사용할 수 있다는 점에서 전역적입니다.  XML 요소 리터럴을 만들 때와 XML 축 속성에 액세스할 때 이를 사용할 수 있습니다.  자세한 내용은 [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) 및 [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)을 참조하십시오.  
  
 `Imports <xmlns="http://SomeNameSpace>"`와 같이 네임스페이스 접두사 없이 전역 XML 네임스페이스를 정의하는 경우 해당 네임스페이스는 기본 XML 네임스페이스로 간주됩니다.  기본 XML 네임스페이스는 명시적으로 네임스페이스를 지정하지 않은 모든 XML 요소 리터럴 또는 XML 특성 축 속성에 사용됩니다.  지정된 네임스페이스가 빈 네임스페이스 즉, `xmlns=""`인 경우에도 기본 네임스페이스가 사용됩니다.  기본 XML 네임스페이스는 XML 리터럴의 XML 특성 또는 네임스페이스가 없는 XML 특성 축 속성에는 적용되지 않습니다.  
  
 *로컬 XML 네임스페이스*라고 하는 XML 리터럴에 정의된 XML 네임스페이스는 `Imports` 문을 사용하여 전역으로 정의된 XML 네임스페이스보다 우선합니다.  `Imports` 문을 사용하여 정의된 XML 네임스페이스는 Visual Basic 프로젝트용으로 가져온 XML 네임스페이스보다 우선합니다.  XML 리터럴이 XML 네임스페이스를 정의하면 이 로컬 네임스페이스는 포함된 식에는 적용되지 않습니다.  
  
 전역 XML 네임스페이스는 .NET Framework 네임스페이스와 동일한 범위 및 정의 규칙을 따릅니다.  그 결과 .NET Framework 네임스페이스를 가져올 수 있는 곳이라면 어디에서든 `Imports` 문을 포함시켜 전역 XML 네임스페이스를 정의할 수 있습니다.  여기에는 코드 파일과 프로젝트 수준의 가져온 네임스페이스가 모두 포함됩니다.  프로젝트 수준의 가져온 네임스페이스에 대한 자세한 내용은 [참조 페이지, 프로젝트 디자이너\(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)를 참조하십시오.  
  
 각 소스 파일에 여러 개의 `Imports` 문을 포함할 수 있습니다.  이 문을 사용하려면 `Option Strict` 문과 같은 옵션 선언 규칙을 따라야 하며 `Module` 또는 `Class` 문과 같은 프로그래밍 요소 선언 앞에 와야 합니다.  
  
## 예제  
 다음 예제에서는 기본 XML 네임스페이스와 `ns` 접두사로 식별되는 XML 네임스페이스를 가져옵니다.  그런 다음 두 가지 네임스페이스를 모두 사용하는 XML 리터럴을 만듭니다.  
  
 [!code-vb[VbXMLSamples#45](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/imports-statement-xml-na_1.vb)]  
  
 이 코드가 표시하는 텍스트는 다음과 같습니다.  
  
```  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## 예제  
 다음 예제에서는 XML 네임스페이스 접두사인 `ns`를 가져옵니다.  그런 다음 네임스페이스 접두사를 사용하는 XML 리터럴을 만들고 요소의 최종 폼을 표시합니다.  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/imports-statement-xml-na_2.vb)]  
  
 이 코드가 표시하는 텍스트는 다음과 같습니다.  
  
```  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 컴파일러가 XML 네임스페이스 접두사를 전역 접두사에서 로컬 접두사 정의로 변환해 놓았음을 주의하십시오.  
  
## 예제  
 다음 예제에서는 XML 네임스페이스 접두사인 `ns`를 가져옵니다.  그런 다음 네임스페이스의 접두사를 사용하여 XML 리터럴을 만들고 정규화된 이름인 `ns:name`을 사용하여 첫 번째 자식 노드에 액세스합니다.  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/imports-statement-xml-na_3.vb)]  
  
 이 코드가 표시하는 텍스트는 다음과 같습니다.  
  
 `Patrick Hines`  
  
## 참고 항목  
 [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)   
 [GetXmlNamespace Operator](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)