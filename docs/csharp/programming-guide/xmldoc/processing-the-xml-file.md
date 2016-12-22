---
title: "XML 파일 처리(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "XML[C#], 처리"
  - "XML 처리[C#]"
ms.assetid: 60c71193-9dac-4cd3-98c5-100bd0edcc42
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# XML 파일 처리(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

컴파일러는 태그가 있는 코드의 각 구문에 ID 문자열을 생성하여 문서를 만듭니다.  코드에 태그를 추가하는 방법에 대해서는 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)를 참조하십시오. ID 문자열은 해당 구문을 고유하게 식별합니다.  XML 파일을 처리하는 프로그램에서는 이 ID 문자열을 사용하여 문서가 적용될 해당 .NET Framework의 메타데이터\/리플렉션 항목을 식별할 수 있습니다.  
  
 XML 파일은 코드를 계층 구조로 표현하지 않고 각 요소에 대해 생성된 ID를 사용하는 단순한 목록입니다.  
  
 컴파일러는 아래와 같은 규칙에 따라 ID 문자열을 생성합니다.  
  
-   문자열에 공백 문자를 사용하지 않습니다.  
  
-   ID 문자열의 첫 부분은 식별할 멤버의 종류를 나타내는 단일 문자이며 그 뒤에 콜론이 옵니다.  아래와 같은 멤버 형식을 사용합니다.  
  
    |문자|설명|  
    |--------|--------|  
    |N|네임스페이스<br /><br /> 네임스페이스에는 문서 주석을 추가할 수 없지만 지원되는 경우 문서 주석에 대한 cref 참조를 만들 수 있습니다.|  
    |T|형식\(클래스, 인터페이스, 구조체, 열거형, 대리자\)|  
    |F|필드\(field\)|  
    |P|속성\(인덱서와 기타 인덱싱된 속성 포함\)|  
    |M|메서드\(생성자, 연산자 등의 특수한 메서드 포함\)|  
    |E|이벤트|  
    |\!|오류 문자열<br /><br /> 나머지 문자열은 오류 정보를 제공합니다.  C\# 컴파일러는 확인할 수 없는 링크에 대한 오류 정보를 생성합니다.|  
  
-   문자열의 둘째 부분은 네임스페이스의 루트에서 시작하는 항목의 정규화된 이름입니다.  항목의 이름, 해당 포함 형식 및 네임스페이스는 마침표로 구분합니다.  항목 이름 자체에 마침표가 있는 경우 해당 마침표는 해시 기호\('\#'\)로 바뀝니다.  항목 이름에 직접 해시 기호를 사용하지 않는 것으로 가정합니다.  예를 들어, String 생성자의 정규화된 이름은 "System.String.\#ctor"가 될 수 있습니다.  
  
-   속성 및 메서드의 경우, 메서드 인수가 있는 경우 인수 목록을 괄호로 묶어야 합니다.  인수가 없으면 괄호는 필요 없습니다.  인수는 쉼표로 구분합니다.  각 인수의 인코딩은 아래와 같이 .NET Framework 시그니처에서 인수를 인코딩하는 방법을 그대로 따릅니다.  
  
    -   기본 형식.  정규 형식\(ELEMENT\_TYPE\_CLASS 또는 ELEMENT\_TYPE\_VALUETYPE\)은 형식의 정규화된 이름으로 표시됩니다.  
  
    -   내장 형식 \(예를 들어, ELEMENT\_TYPE\_I4, ELEMENT\_TYPE\_OBJECT, ELEMENT\_TYPE\_STRING, ELEMENT\_TYPE\_TYPEDBYREF.  및  ELEMENT\_TYPE\_VOID\)는 해당 형식의 정규화된 이름으로 표시됩니다.  예를 들어, System.Int32 또는 System.TypedReference 등으로 표시됩니다.  
  
    -   ELEMENT\_TYPE\_PTR는 수정된 형식 다음에 '\*'을 붙여 표시합니다.  
  
    -   ELEMENT\_TYPE\_BYREF는 수정된 형식 다음에 '@'을 붙여 표시합니다.  
  
    -   ELEMENT\_TYPE\_PINNED는 수정된 형식 다음에 '^'을 붙여 표시합니다.  C\# 컴파일러에서는 이 내용이 적용되지 않습니다.  
  
    -   ELEMENT\_TYPE\_CMOD\_REQ는 수정된 형식 다음에 '&#124;' 및 한정자 클래스의 정규화된 이름을 붙여 표시합니다.  C\# 컴파일러에서는 이 내용이 적용되지 않습니다.  
  
    -   ELEMENT\_TYPE\_CMOD\_REQ는 수정된 형식 다음에 '&#124;' 및 한정자 클래스의 정규화된 이름을 붙여 표시합니다.  
  
    -   ELEMENT\_TYPE\_SZARRAY는 배열 요소 형식 다음에 "\[\]"를 붙여 표시합니다.  
  
    -   ELEMENT\_TYPE\_GENERICARRAY는 배열 요소 형식 다음에 "\[?\]"를 붙여 표시합니다.  C\# 컴파일러에서는 이 내용이 적용되지 않습니다.  
  
    -   ELEMENT\_TYPE\_ARRAY는 \[*lowerbound*:`size`,*lowerbound*:`size`\]의 형식으로 표시합니다. 여기에서, 쉼표의 수는 차수에서 1을 뺀 값이며 알려진 각 차원의 lowerbound와 size는 숫자로 표시됩니다.  lowerbound 또는 size를 지정하지 않으면 생략됩니다.  특정 차원의 lowerbound와 size가 생략되면 ':' 또한 생략됩니다.  예를 들어, lowerbound가 1이고 size가 지정되지 않은 2차원 배열은 \[1:,1:\]입니다.  
  
    -   ELEMENT\_TYPE\_FNPTR는 "\=FUNC:`type`\(*signature*\)"로 나타냅니다. 여기서, `type`은 반환 형식이며 *signature*는 메서드 인수입니다.  인수가 없으면 괄호는 생략합니다.  C\# 컴파일러에서는 이 내용이 적용되지 않습니다.  
  
     아래와 같은 시그니처 구성 요소는 오버로드된 메서드를 구분하는 데 사용되지 않기 때문에 표시되지 않습니다.  
  
    -   호출 규칙  
  
    -   반환 형식  
  
    -   ELEMENT\_TYPE\_SENTINEL  
  
-   변환 연산자\(op\_Implicit 및 op\_Explicit\)의 경우에만 위에서 인코딩한 대로 반환 형식 앞에 '~'를 붙여 메서드 반환 값을 인코딩합니다.  
  
-   제네릭 형식의 경우 형식의 이름 뒤에는 역따옴표\(\`\) 및 제네릭 형식 매개 변수의 수를 나타내는 번호가 추가됩니다.  다음 예제를 참조하십시오.  
  
     `<member name="T:SampleClass`2">`는 `public class SampleClass<T, U>`로 정의된 형식에 대한 태그입니다.  
  
     제네릭 형식을 매개 변수로 사용하는 메서드의 경우 제네릭 형식 매개 변수는 역따옴표\(\`\)가 앞에 추가된 번호로 지정됩니다\(예: \`0, \`1\).  각 번호는 형식의 제네릭 매개 변수에 대한 배열\(0부터 시작\) 표시를 나타냅니다.  
  
## 예제  
 아래 예제는 클래스와 해당 멤버의 ID 문자열이 생성되는 방식을 보여 줍니다.  
  
 [!CODE [csProgGuidePointers#21](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#21)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [\/doc \(Process Documentation Comments\)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [XML 문서 주석](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)