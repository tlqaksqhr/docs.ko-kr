---
title: "&lt;seealso&gt;(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cref"
  - "<seealso>"
  - "seealso"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<seealso> C# XML 태그"
  - "cref[C#]"
  - "cref[C#], 참고 항목"
  - "크로스 참조[C#], 태그"
  - "seealso C# XML 태그"
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# &lt;seealso&gt;(C# 프로그래밍 가이드)
## 구문  
  
```  
<seealso cref="member"/>  
```  
  
#### 매개 변수  
 cref \= "`member`"  
 현재 컴파일 환경에서 호출될 수 있는 멤버 또는 필드에 대한 참조입니다.  컴파일러는 지정된 코드 요소가 존재하고 출력 XML에서 `member`를 요소 이름에 전달하는지 확인합니다. `member`는 큰따옴표\(" "\)로 묶어야 합니다.  
  
 제네릭 형식에 대한 cref 참조를 만드는 방법에 대한 자세한 내용은 [\<see\>](../../../csharp/programming-guide/xmldoc/see.md)를 참조하십시오.  
  
## 설명  
 \<seealso\> 태그를 사용하면 참고 항목 부분에 나타나는 텍스트를 지정할 수 있습니다.  텍스트 내부에서 링크를 지정하려면 [\<see\>](../../../csharp/programming-guide/xmldoc/see.md)를 사용합니다.  
  
 [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 \<seealso\> 사용 예제는 [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md)를 참조하십시오.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)