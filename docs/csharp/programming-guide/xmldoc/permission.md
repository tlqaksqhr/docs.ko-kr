---
title: "&lt;permission&gt;(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "permission"
  - "<permission>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<permission> C# XML 태그"
  - "permission C# XML 태그"
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# &lt;permission&gt;(C# 프로그래밍 가이드)
## 구문  
  
```  
<permission cref="member">description</permission>  
```  
  
#### 매개 변수  
 cref \= "`member`"  
 현재 컴파일 환경에서 호출될 수 있는 멤버 또는 필드에 대한 참조입니다.  컴파일러는 지정된 코드 요소가 존재하고 출력 XML에서 `member`를 정식 요소 이름으로 변환할 수 있는지 확인합니다. *member*는 큰따옴표\(" "\)로 묶어야 합니다.  
  
 제네릭 형식에 대한 cref 참조를 만드는 방법에 대한 자세한 내용은 [\<see\>](../../../csharp/programming-guide/xmldoc/see.md)를 참조하십시오.  
  
 `description`  
 멤버 액세스에 대한 설명입니다.  
  
## 설명  
 \<permission\> 태그를 사용하면 멤버 액세스를 문서화할 수 있습니다.  <xref:System.Security.PermissionSet> 클래스를 사용하면 멤버에 대한 액세스를 지정할 수 있습니다.  
  
 [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 [!code-cs[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)