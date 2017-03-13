---
title: "&lt;summary&gt;(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "<summary>"
  - "summary"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<summary> C# XML 태그"
  - "summary C# XML 태그"
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# &lt;summary&gt;(C# 프로그래밍 가이드)
## 구문  
  
```  
<summary>description</summary>  
```  
  
#### 매개 변수  
 `description`  
 개체에 대한 요약입니다.  
  
## 설명  
 형식 또는 형식 멤버를 설명하려면 \<summary\> 태그를 사용해야 합니다.  형식에 대한 설명을 보충하는 정보를 추가하려면 [\<remarks\>](../../../csharp/programming-guide/xmldoc/remarks.md)를 사용합니다.  [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061)과 같은 문서 도구를 사용하여 코드 요소의 문서 페이지에 대한 내부 하이퍼링크를 만들 수 있게 하려면 [cref 특성](../../../csharp/programming-guide/xmldoc/cref-attribute.md)을 사용합니다.  
  
 IntelliSense에서 \<summary\> 태그의 텍스트는 형식 정보의 유일한 출처이며, [Object Browser Window](http://msdn.microsoft.com/ko-kr/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda)에서도 표시됩니다.  
  
 [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  컴파일러에서 생성한 파일을 기반으로 최종 문서를 만들려면 사용자 지정 도구를 만들거나 [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061)과 같은 도구를 사용하면 됩니다.  
  
## 예제  
 [!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_1.cs)]  
  
 앞의 예제는 다음과 같은 XML 파일을 만듭니다.  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:DotNetEvents.TestClass">  
            text for class TestClass  
        </member>  
        <member name="M:DotNetEvents.TestClass.DoWork(System.Int32)">  
            <summary>DoWork is a method in the TestClass class.  
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>  
            <seealso cref="M:DotNetEvents.TestClass.Main"/>  
            </summary>  
        </member>  
        <member name="M:DotNetEvents.TestClass.Main">  
            text for Main  
        </member>  
    </members>  
</doc>  
```  
  
## 예제  
 다음 예제에서는 제네릭 형식에 대한 `cref` 참조를 만드는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideDocComments#11](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_2.cs)]  
  
 앞의 예제는 다음과 같은 XML 파일을 만듭니다.  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:ExtensionMethodsDemo1.A">  
            <summary cref="T:ExtensionMethodsDemo1.C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.B">  
            <summary cref="T:C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.C`1">  
            <summary cref="T:ExtensionMethodsDemo1.A">  
            </summary>  
            <typeparam name="T"></typeparam>  
        </member>  
    </members>  
</doc>  
  
```  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)