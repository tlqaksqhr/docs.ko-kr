---
title: "&lt;exception&gt;(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "exception"
  - "<exception>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<exception> C# XML 태그"
  - "exception C# XML 태그"
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# &lt;exception&gt;(C# 프로그래밍 가이드)
## 구문  
  
```  
<exception cref="member">description</exception>  
```  
  
#### 매개 변수  
 cref \= "`member`"  
 현재 컴파일 환경에 있는 예외에 대한 참조.  컴파일러에서는 지정된 예외가 존재하는지를 확인하고 `member`를 출력 XML의 정식 요소 이름으로 변환합니다.  `member`는 큰따옴표\(" "\)로 묶어야 합니다.  
  
 제네릭 형식에 대한 cref 참조를 만드는 방법의 자세한 내용은 [\<see\>](../../../csharp/programming-guide/xmldoc/see.md)를 참조하십시오.  
  
 `description`  
 예외에 대한 설명입니다.  
  
## 설명  
 throw할 수 있는 예외를 \<exception\> 태그에 지정합니다.  이 태그는 메서드, 속성, 이벤트 및 인덱서에 대한 정의에 적용할 수 있습니다.  
  
 [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
 예외 처리에 대한 자세한 내용은 [예외 및 예외 처리](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)를 참조하십시오.  
  
## 예제  
 [!code-cs[csProgGuideDocComments#4](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/exception_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)