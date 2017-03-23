---
title: "string(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "string"
  - "string_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "문자열[C#], 참조"
  - "@ string 리터럴"
  - "string 리터럴[C#]"
  - "string 키워드[C#]"
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# string(C# 참조)
`string` 형식은 0개 이상의 유니코드 문자 시퀀스를 나타냅니다.  `string`은 .NET Framework의 <xref:System.String>에 대한 별칭입니다.  
  
 `string`은 참조 형식이지만 같음 연산자\(`==` 및 `!=`\)는 참조가 아니라 `string` 개체의 값을 비교하도록 정의되어 있으므로  좀 더 쉽게 문자열을 비교할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```c#  
  
      string a = "hello";  
string b = "h";  
// Append to contents of 'b'  
b += "ello";  
Console.WriteLine(a == b);  
Console.WriteLine((object)a == (object)b);  
```  
  
 이 코드는 문자열의 내용이 동일하므로 "True"를 표시한 다음 "False"를 표시하지만 `a`와 `b`는 동일한 문자열 인스턴스를 가리키지 않습니다.  
  
 \+ 연산자는 문자열을 연결합니다.  
  
```c#  
  
string a = "good " + "morning";  
```  
  
 이 코드는 "good morning"이라는 내용이 포함된 문자열 개체를 만듭니다.  
  
 문자열은 *변경할 수 없습니다*. 즉, 구문을 보면 문자열 개체를 만든 후 이 개체의 내용을 변경할 수 있는 것처럼 보이지만 이는 가능하지 않습니다.  예를 들어, 다음 코드를 작성하면 컴파일러에서는 새 문자 시퀀스가 있는 새 문자열 개체를 만들며 새 개체에 b가 할당됩니다.  문자열 "h"는 가비지 수집의 대상입니다.  
  
```c#  
  
      string b = "h";  
b += "ello";  
```  
  
 \[\] 연산자는 `string`의 개별 문자에 읽기 전용으로 액세스하는 데 사용할 수 있습니다.  
  
```c#  
  
      string str = "test";  
char x = str[2];  // x = 's';  
```  
  
 문자열 리터럴은 `string` 형식이며 따옴표 붙은 형식과 @\-따옴표 붙은 형식의 두 가지 형태로 작성할 수 있습니다.  따옴표 붙은 문자열 리터럴은 다음과 같이 큰따옴표\("\)로 묶습니다.  
  
```c#  
"good morning"  // a string literal  
```  
  
 문자열 리터럴에는 다음과 같이 이스케이프 시퀀스를 포함한  모든 문자 리터럴이 포함될 수 있습니다.  다음 예제에서는 백슬래시에 이스케이프 시퀀스 `\\`, 글자 f에 `\u0066`, 줄 바꿈 문자에 `\n`을 사용합니다.  
  
```  
  
      string a = "\\\u0066\n";  
Console.WriteLine(a);  
```  
  
> [!NOTE]
>  이스케이프 코드 `\`u`dddd`는 유니코드 문자 U\+`dddd`를 나타냅니다. 여기서 `dddd`는 네 자리 숫자입니다.  `\Udddddddd`와 같은 8자리 유니코드 이스케이프 코드도 사용할 수 있습니다.  
  
 약어 문자열 리터럴은 @로 시작하며 큰따옴표로 묶습니다.  예를 들면 다음과 같습니다.  
  
```c#  
@"good morning"  // a string literal  
```  
  
 약어 문자열의 이점은 이스케이프 시퀀스를 처리하지 않기 때문에 다음과 같이 정규화된 파일 이름 등을 쉽게 작성할 수 있다는 것입니다.  
  
```c#  
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"  
```  
  
 @\-따옴표 붙은 문자열에 큰따옴표를 포함시키려면 다음과 같이 큰따옴표를 두 번 입력합니다.  
  
```c#  
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.  
```  
  
 또한 @ 기호는 C\# 키워드인 참조된 식별자\([\/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)\)를 사용하는 데 유용합니다.  
  
 C\#의 문자열에 대한 자세한 내용은 [문자열](../../../csharp/programming-guide/strings/index.md)을 참조하십시오.  
  
## 예제  
 [!code-cs[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문자열 사용에 대한 유용한 정보](../Topic/Best%20Practices%20for%20Using%20Strings%20in%20the%20.NET%20Framework.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)   
 [값 형식](../../../csharp/language-reference/keywords/value-types.md)   
 [기본적인 문자열 작업](../Topic/Basic%20String%20Operations%20in%20the%20.NET%20Framework.md)   
 [새 문자열 만들기](../Topic/Creating%20New%20Strings%20in%20the%20.NET%20Framework.md)   
 [숫자 결과 형식 지정 표](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)