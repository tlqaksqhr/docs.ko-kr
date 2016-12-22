---
title: "#line(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#line"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#line 지시문[C#]"
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# #line(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`#line`을 사용하면 오류 및 경고에 대해 컴파일러에서 출력하는 줄 번호와 파일 이름\(선택적 요소\)을 수정할 수 있습니다.  다음 예제에서는 줄 번호와 관련된 두 개의 경고를 보고하는 방법을 보여 줍니다.  `#line 200` 지시문은 줄 번호를 200으로 강제하며\(기본값은 \#7임\), 다음 \#line 지시문까지 파일 이름이 "Special"로 보고됩니다.  \#line default 지시문은 줄 번호 매기기를 기본 번호 매기기로 되돌리며, 이 경우 이전 지시문에 의해 번호가 다시 매겨진 줄 수를 계산합니다.  
  
```  
class MainClass  
{  
    static void Main()  
    {  
#line 200 "Special"  
        int i;    // CS0168 on line 200  
        int j;    // CS0168 on line 201  
#line default  
        char c;   // CS0168 on line 9  
        float f;  // CS0168 on line 10  
#line hidden // numbering not affected  
        string s;   
        double d; // CS0168 on line 13  
    }  
}  
```  
  
## 설명  
 `#line` 지시문은 빌드 프로세스의 자동화된 중간 단계에서 사용합니다.  예를 들어, 원본 소스 코드 파일의 줄을 제거했지만 컴파일러에서 파일의 원래 줄 번호를 따라 출력하려는 경우, 줄을 제거한 다음 `#line`을 사용하여 원래 줄 번호를 시뮬레이션할 수 있습니다.  
  
 `#line hidden` 지시문은 이 지시문 다음에 나오는 줄을 디버거에서 숨깁니다. 따라서 개발자가 코드를 단계별로 실행할 경우 `#line hidden`과 다음 `#line` 지시문\(이 지시문이 다른 `#line hidden` 지시문이 아니라고 가정하고\) 사이에 있는 모든 줄을 건너 뜁니다.  뿐만 아니라 이 옵션을 사용해 ASP.NET에서 사용자 정의 코드와 시스템 생성 코드를 구별하도록 할 수 있습니다.  현재는 ASP.NET에서 이 기능을 주로 사용하지만 앞으로는 보다 많은 소스 생성기에서 이 기능을 사용하게 될 것입니다.  
  
 `#line hidden` 지시문은 오류 보고에 나타나는 파일 이름이나 줄 번호에는 영향을 주지 않습니다.  따라서 숨겨진 블록에서 오류가 발생하더라도 컴파일러가 현재 파일 이름과 오류를 발생시킨 줄 번호를 보고합니다.  
  
 `#line filename` 지시문은 컴파일러 출력에 표시할 파일 이름을 지정합니다.  기본적으로 소스 코드 파일의 실제 이름을 사용합니다.  파일 이름은 큰따옴표\(""\)로 묶어야 하며, 앞에 줄 번호가 와야 합니다.  
  
 소스 코드 파일에 여러 개의 `#line` 지시문을 사용할 수 있습니다.  
  
## 예제 1  
 다음 예제는 디버거가 코드의 숨겨진 줄을 무시하는 방법을 보여 줍니다.  이 예제를 실행하면 텍스트 세 줄이 표시됩니다.  그러나 다음 예제에서와 같이 중단점을 설정하고 F10 키를 눌러 코드를 단계별로 실행하면 디버거가 숨겨진 줄을 무시합니다.  뿐만 아니라 숨겨진 줄에 중단점을 설정하더라도 디버거가 해당 줄을 무시합니다.  
  
```  
// preprocessor_linehidden.cs  
using System;  
class MainClass   
{  
    static void Main()   
    {  
        Console.WriteLine("Normal line #1."); // Set break point here.  
#line hidden  
        Console.WriteLine("Hidden line.");  
#line default  
        Console.WriteLine("Normal line #2.");  
    }  
}  
```  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 전처리기 지시문](../../../visual-basic/reference/command-line-compiler/index.md)