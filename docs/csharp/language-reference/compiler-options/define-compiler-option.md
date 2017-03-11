---
title: "/define (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/define"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-define compiler option [C#]"
  - "/define compiler option [C#]"
  - "-d compiler option [C#]"
  - "define compiler option [C#]"
  - "/d compiler option [C#]"
  - "d compiler option [C#]"
ms.assetid: f17d7b4d-82d0-4133-8563-68cced1cac6e
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# /define (C# Compiler Options)
**\/define** 옵션은 `name`을 프로그램의 모든 소스 코드에서 기호로 정의합니다.  
  
## 구문  
  
```  
/define:name[;name2]  
```  
  
## 인수  
 `name`, `name2`  
 정의하려는 하나 이상의 기호 이름입니다.  
  
## 설명  
 **\/define** 옵션은 프로젝트의 모든 파일에 적용되는 컴파일러 옵션이라는 것을 제외하면 [\#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) 전처리기 지시문을 사용하는 것과 같은 효과를 나타냅니다.  소스 파일의 [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) 지시문에서 정의를 제거할 때까지 소스 파일의 기호는 정의된 상태로 있습니다.  \/define 옵션을 사용하는 경우 특정 파일의 `#undef` 지시문은 프로젝트의 다른 소스 코드 파일에 영향을 주지 않습니다.  
  
 이 옵션으로 만든 기호를 [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), [\#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [\#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) 및 [\#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)와 함께 사용하면 소스 파일을 조건부로 컴파일할 수 있습니다.  
  
 **\/d**는 **\/define**의 약식 표현입니다.  
  
 기호 이름을 구분하는 세미콜론 또는 쉼표를 사용하면 **\/define** 옵션으로 여러 기호를 정의할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
/define:DEBUG;TUESDAY  
```  
  
 C\# 컴파일러는 소스 코드에서 사용할 수 있는 기호나 매크로를 자체 정의하지 않습니다. 모든 기호 정의는 사용자가 정의해야 합니다.  
  
> [!NOTE]
>  C\+\+등의 언어와는 다르게 C\#에서는 `#define`을 사용하여 기호에 값을 지정할 수 없습니다.  예를 들어 `#define`을 사용하여 매크로를 만들거나 상수를 정의할 수 없습니다.  상수를 정의하려면 `enum` 변수를 사용합니다.  C\+\+ 스타일 매크로를 만들려면 제네릭과 같은 대체 방법을 사용합니다.  매크로에서는 오류가 발생하기 쉽기 때문에 C\#에서는 매크로의 사용을 허용하지 않고 더 안전한 대체 방법을 제공합니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **빌드** 탭에서 **조건부 컴파일 기호** 상자에 정의할 기호를 입력합니다.  예를 들어, 다음 코드 예제를 사용하는 경우 입력란에 `xx`만 입력하면 됩니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>를 참조하십시오.  
  
## 예제  
  
```  
// preprocessor_define.cs  
// compile with: /define:xx  
// or uncomment the next line  
// #define xx  
using System;  
public class Test   
{  
    public static void Main()   
    {  
        #if (xx)   
            Console.WriteLine("xx defined");  
        #else  
            Console.WriteLine("xx not defined");  
        #endif  
    }  
}  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)