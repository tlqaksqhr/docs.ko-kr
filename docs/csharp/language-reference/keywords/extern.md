---
title: "extern(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "extern_CSharpKeyword"
  - "extern"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "DllImport 특성"
  - "extern 키워드[C#]"
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# extern(C# 참조)
`extern` 한정자는 외부에서 구현되는 메서드를 선언하는 데 사용됩니다.  `extern` 한정자는 일반적으로 Interop 서비스를 사용하여 비관리 코드를 호출할 때 `DllImport` 특성과 함께 사용됩니다.  이 경우 다음 예제에서와 같이 메서드를 `static`으로 선언해야 합니다.  
  
```  
[DllImport("avifil32.dll")]  
private static extern void AVIFileInit();  
```  
  
 `extern` 키워드는 외부 어셈블리 별칭도 정의하여 단일 어셈블리 내에서 동일한 구성 요소의 다른 버전을 참조할 수 있도록 합니다.  자세한 내용은 [extern alias](../../../csharp/language-reference/keywords/extern-alias.md)을 참조하십시오.  
  
 [abstract](../../../csharp/language-reference/keywords/abstract.md)와 `extern` 한정자를 함께 사용하여 같은 멤버를 제한할 수는 없습니다.  `extern` 한정자는 메서드가 C\# 코드 외부에서 구현됨을 나타내고 `abstract` 한정자는 해당 클래스에서 메서드가 구현되지 않음을 나타냅니다.  
  
 extern 키워드는 C\+\+보다 C\#에서 사용이 제한적입니다.  C\# 키워드를 C\+\+ 키워드와 비교하려면 extern을 사용하여 C\+\+ 언어 참조에 링크 지정을 참조하십시오.  
  
## 예제  
 **예제 1.** 다음 예제에서는 프로그램이 사용자로부터 문자열을 수신하여 메시지 상자에 표시합니다.  이 프로그램은 User32.dll 라이브러리에서 가져온 `MessageBox` 메서드를 사용합니다.  
  
 [!code-cs[csrefKeywordsModifiers#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/extern_1.cs)]  
  
## 예제  
 **예제 2.** 이 예제는 C 라이브러리\(네이티브 DLL\)로 호출되는 C\# 프로그램을 보여줍니다.  
  
 1.  다음 C 파일을 만들고 이름을 `cmdll.c`로 지정합니다.  
  
```  
// cmdll.c  
// Compile with: /LD  
int __declspec(dllexport) SampleMethod(int i)  
{  
   return i*10;  
}  
```  
  
## 예제  
 2.  Visual Studio 설치 디렉터리에서 Visual Studio x64\(또는 x32\) 네이티브 도구 명령 프롬프트 창을 열고 명령 프롬프트에서 `cmdll.c`를 입력하여 **cl \/LD cmdll.c** 파일을 컴파일합니다.  
  
 3.  같은 디렉터리에서 다음 C\# 파일을 만들고 이름을 `cm.cs`로 지정합니다.  
  
```  
// cm.cs  
using System;  
using System.Runtime.InteropServices;  
public class MainClass   
{  
   [DllImport("Cmdll.dll")]  
   public static extern int SampleMethod(int x);  
  
   static void Main()   
   {  
      Console.WriteLine("SampleMethod() returns {0}.", SampleMethod(5));  
   }  
}  
```  
  
## 예제  
 3.  Visual Studio 설치 디렉터리에서 Visual Studio x64\(또는 x32\) 네이티브 도구 명령 프롬프트 창을 열고 명령 프롬프트에서 다음을 입력하여 `cm.cs` 파일을 컴파일합니다.  
  
> **csc cm.cs**\(x64 명령 프롬프트용\)   
>  —또는—  
> **csc \/platform:x86 cm.cs**\(x32 명령 프롬프트용\)  
  
 이렇게 하면 실행 파일 `cm.exe`가 만들어집니다.  
  
 4.  `cm.exe`를 실행합니다.  `SampleMethod` 메서드가 값 5를 DLL 파일로 전달하면 10으로 곱해진 값이 반환됩니다. 프로그램 출력은 다음과 같습니다.  
  
```  
SampleMethod() returns 50.  
```  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>   
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)