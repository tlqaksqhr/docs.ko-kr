---
title: "문서 주석에 대한 권장 태그(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "XML[C#], 태그"
  - "XML 문서[C#], 태그"
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# 문서 주석에 대한 권장 태그(C# 프로그래밍 가이드)
C\# 컴파일러는 코드에서 문서 주석을 처리하고 **\/doc** 명령줄 옵션에 이름이 지정된 파일에서 문서 주석의 서식을 XML로 지정합니다.  컴파일러에서 생성 된 파일을 기반으로 최종 문서를 만들려면 사용자 지정 도구를 만들거나 같은 도구를 사용 하 여 [Sandcastle](http://shfb.codeplex.com/).  
  
 태그는 형식, 형식 멤버 등과 같은 코드 구문에서 처리됩니다.  
  
> [!NOTE]
>  문서 주석은 네임스페이스에 적용할 수 없습니다.  
  
 컴파일러는 유효한 XML 태그를 모두 처리합니다.  아래 태그에는 사용자 문서에서 일반적으로 사용하는 기능이 포함되어 있습니다.  
  
## 태그  
  
||||  
|-|-|-|  
|[\<c\>](../../../csharp/programming-guide/xmldoc/code-inline.md)|[\<para\>](../../../csharp/programming-guide/xmldoc/para.md)|[\<see\>](../../../csharp/programming-guide/xmldoc/see.md)\*|  
|[\<code\>](../../../csharp/programming-guide/xmldoc/code.md)|[\<param\>](../../../csharp/programming-guide/xmldoc/param.md)\*|[\<seealso\>](../../../csharp/programming-guide/xmldoc/seealso.md)\*|  
|[\<example\>](../../../csharp/programming-guide/xmldoc/example.md)|[\<paramref\>](../../../csharp/programming-guide/xmldoc/paramref.md)|[\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md)|  
|[\<exception\>](../../../csharp/programming-guide/xmldoc/exception.md)\*|[\<permission\>](../../../csharp/programming-guide/xmldoc/permission.md)\*|[\<typeparam\>](../../../csharp/programming-guide/xmldoc/typeparam.md)\*|  
|[\<include\>](../../../csharp/programming-guide/xmldoc/include.md)\*|[\<remarks\>](../../../csharp/programming-guide/xmldoc/remarks.md)|[\<typeparamref\>](../../../csharp/programming-guide/xmldoc/typeparamref.md)|  
|[\<list\>](../../../csharp/programming-guide/xmldoc/list.md)|[\<returns\>](../../../csharp/programming-guide/xmldoc/returns.md)|[\<value\>](../../../csharp/programming-guide/xmldoc/value.md)|  
  
 \* 표시는 컴파일러가 구문을 확인함을 나타냅니다.  
  
 문서 주석의 텍스트에 꺾쇠 괄호를 표시하려면 다음 예제에 표시된 대로 `<`와 `>`을 사용합니다.  
  
```xml  
/// <summary cref="C < T >">  
/// </summary>  
```  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [\/doc \(Process Documentation Comments\)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [XML 문서 주석](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)