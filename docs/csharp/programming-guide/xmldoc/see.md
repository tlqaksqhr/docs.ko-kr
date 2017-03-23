---
title: "&lt;see&gt;(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "<see>"
  - "see"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<see> C# XML 태그"
  - "cref[C#], <see> 태그"
  - "크로스 참조[C#]"
  - "see C# XML 태그"
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# &lt;see&gt;(C# 프로그래밍 가이드)
## 구문  
  
```  
<see cref="member"/>  
```  
  
#### 매개 변수  
 cref \= "`member`"  
 현재 컴파일 환경에서 호출될 수 있는 멤버 또는 필드에 대한 참조입니다.  컴파일러는 지정된 코드 요소가 있고 출력 XML의 요소 이름에 `member`가 전달되는지 검사합니다.*member*를 큰따옴표\(" "\)로 묶습니다.  
  
## 설명  
 \<see\> 태그는 텍스트 내부에서 링크를 지정할 수 있게 합니다.  See Also 섹션에 배치할 텍스트를 지정하려면 [\<seealso\>](../../../csharp/programming-guide/xmldoc/seealso.md) 를 사용합니다.  코드 요소의 문서 페이지에 대한 내부 하이퍼링크를 만들려면 [cref 특성](../../../csharp/programming-guide/xmldoc/cref-attribute.md)을 사용합니다.  
  
 [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
 다음 예제는 요약 섹션 내부의 \<see\> 를 보여줍니다.  
  
 [!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)