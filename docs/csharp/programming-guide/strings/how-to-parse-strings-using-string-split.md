---
title: "방법: String.Split를 사용하여 문자열 구문 분석(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c0ef96f1cb074c32208457c192d53c69d95a102d
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-parse-strings-using-stringsplit-c-programming-guide"></a>방법: String.Split를 사용하여 문자열 구문 분석(C# 프로그래밍 가이드)
다음 코드 예제에서는 <xref:System.String.Split%2A?displayProperty=fullName> 메서드를 사용하여 문자열을 구문 분석하는 방법을 보여 줍니다. <xref:System.String.Split%2A> 는 대상 문자열의 흥미로운 하위 문자열을 구분하는 문자를 나타내는 문자 배열을 입력으로 사용합니다.  함수는 하위 문자열 배열을 반환합니다.  
  
 이 예제에서는 공백, 쉼표, 마침표, 콜론 및 탭을 사용하며, 모두 이러한 구분 문자를 포함하는 배열로 <xref:System.String.Split%2A>에 전달됩니다.  대상 문자열 문장의 각 단어는 결과 문자열 배열과 별도로 표시됩니다.  
  
## <a name="example"></a>예제  
 [!code-cs[csProgGuideStrings#16](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-parse-strings-using-string-split_1.cs)]  
  
## <a name="example"></a>예제  
 기본적으로 String.Split는 두 구분 문자가 대상 문자열에 연속적으로 표시되는 경우 빈 문자열을 반환합니다.  선택적 StringSplitOptions.RemoveEmptyEntries 매개 변수를 전달하여 출력에서 빈 문자열을 모두 제외할 수 있습니다.  
  
 String.Split는 문자열 배열(단일 문자 대신 대상 문자열을 구문 분석하기 위한 구분 기호 역할을 하는 문자 시퀀스)을 사용할 수 있습니다.  
  
```csharp  
class TestStringSplit  
{  
    static void Main()  
    {  
        char[] separatingChars = { "<<", "..." };  
  
        string text = "one<<two......three<four";  
        System.Console.WriteLine("Original text: '{0}'", text);  
  
        string[] words = text.Split(separatingChars, System.StringSplitOptions.RemoveEmptyEntries );  
        System.Console.WriteLine("{0} substrings in text:", words.Length);  
  
        foreach (string s in words)  
        {  
            System.Console.WriteLine(s);  
        }  
  
        // Keep the console window open in debug mode.  
        System.Console.WriteLine("Press any key to exit.");  
        System.Console.ReadKey();  
    }  
}  
/* Output:  
    Original text: 'one<<two......three<four'  
    3 words in text:  
    one  
    two  
    three<four  
*/  
```  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문자열](../../../csharp/programming-guide/strings/index.md)   
 [.NET Framework 정규식](https://msdn.microsoft.com/library/hs600312)

