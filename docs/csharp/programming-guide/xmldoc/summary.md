---
title: '&lt;summary&gt;(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: 5415603142afaeb5df3f6c2d270a8f895196a207
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ltsummarygt-c-programming-guide"></a>&lt;summary&gt;(C# 프로그래밍 가이드)
## <a name="syntax"></a>구문  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `description`  
 개체에 대한 요약입니다.  
  
## <a name="remarks"></a>설명  
 \<summary > 태그를 사용하여 형식 또는 형식 멤버를 설명해야 합니다. [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md)를 사용하여 형식 설명에 보충 정보를 추가할 수 있습니다. [cref 특성](../../../csharp/programming-guide/xmldoc/cref-attribute.md)을 사용하면 [Sandcastle](https://github.com/EWSoftware/SHFB) 등의 설명서 도구를 통해 코드 요소의 설명서 페이지에 대한 내부 하이퍼링크를 만들 수 있습니다.  
  
 \<summary> 태그의 텍스트는 IntelliSense의 형식에 대한 유일한 정보 소스이며 개체 브라우저 창에도 표시됩니다.  
  
 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다. 컴파일러에서 생성한 파일을 기반으로 최종 문서를 만들려면 사용자 지정 도구를 만들거나 [Sandcastle](https://github.com/EWSoftware/SHFB)과 같은 도구를 사용하면 됩니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_1.cs)]  
  
 앞의 예제에서는 다음 XML 파일을 생성합니다.  
  
```xml  
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
  
## <a name="example"></a>예  
 다음 예제에서는 제네릭 형식에 대한 `cref` 참조를 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[csProgGuideDocComments#11](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_2.cs)]  
  
 앞의 예제에서는 다음 XML 파일을 생성합니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
