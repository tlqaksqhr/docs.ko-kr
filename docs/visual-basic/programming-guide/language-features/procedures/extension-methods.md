---
title: "확장 메서드(Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.ExtensionMethods"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "데이터 형식 확장"
  - "확장 메서드[Visual Basic]"
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
caps.latest.revision: 41
caps.handback.revision: 41
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 확장 메서드(Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

확장 메서드를 사용하면 개발자가 파생 형식을 새로 만들지 않고 이미 정의되어 있는 데이터 형식에 사용자 지정 기능을 추가할 수 있습니다.  확장 메서드를 사용하면 기존 형식의 인스턴스 메서드인 것처럼 호출되는 메서드를 작성할 수 있습니다.  
  
## 설명  
 확장 메서드는 `Sub` 프로시저 또는 `Function` 프로시저만 될 수 있습니다.  확장 속성, 필드 또는 이벤트는 정의할 수 없습니다.  모든 확장 메서드는 <xref:System.Runtime.CompilerServices?displayProperty=fullName> 네임스페이스에서 `<Extension()>` 확장 특성으로 표시해야 합니다.  
  
 확장 메서드 정의의 첫 번째 매개 변수는 메서드가 확장하는 데이터 형식을 지정합니다.  메서드가 실행되면 첫 번째 매개 변수는 메서드를 호출하는 데이터 형식의 인스턴스에 바인딩됩니다.  
  
## 예제  
  
### 설명  
 다음 예제에서는 <xref:System.String> 데이터 형식에 대해 `Print` 확장을 정의합니다.  이 메서드는 `Console.WriteLine`을 사용하여 문자열을 표시합니다.  `Print` 메서드의 매개 변수인 `aString`은 메서드가 <xref:System.String> 클래스를 확장하도록 설정합니다.  
  
 [!code-vb[VbVbalrExtensionMethods#1](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/extension-methods_1.vb)]  
  
 확장 메서드 정의가 `<Extension()>` 확장 특성으로 표시되어 있음을 유의하십시오.  메서드가 정의된 모듈을 표시할지 여부는 선택할 수 있지만 각 확장 메서드는 반드시 표시해야 합니다.  확장 특성에 액세스하려면 <xref:System.Runtime.CompilerServices>를 가져와야 합니다.  
  
 확장 메서드는 모듈 안에만 선언할 수 있습니다.  일반적으로 확장 메서드가 정의되는 모듈은 메서드가 실제로 호출되는 모듈과 다릅니다.  따라서 확장 메서드가 포함된 모듈은 필요에 따라 가져오기를 통해 범위로 가져와야 합니다.  `Print`가 포함된 모듈을 범위로 가져온 후에는 `ToUpper`와 같이 인수를 사용하지 않는 일반 인스턴스 메서드인 것처럼 이 메서드를 호출할 수 있습니다.  
  
 [!code-vb[VbVbalrExtensionMethods#2](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/extension-methods_2.vb)]  
  
 다음 예제인 `PrintAndPunctuate`도 <xref:System.String>에 대한 확장이며 이 경우에는 매개 변수 두 개를 사용하여 메서드를 정의합니다.  첫 번째 매개 변수 `aString`은 확장 메서드가 <xref:System.String>을 확장하도록 설정합니다.  두 번째 매개 변수 `punc`는 메서드가 호출될 때 인수로 전달되는 문장 부호 문자열입니다.  이 메서드는 문자열과 문장 부호를 차례로 표시합니다.  
  
 [!code-vb[VbVbalrExtensionMethods#3](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/extension-methods_3.vb)]  
  
 이 메서드는 `punc`의 문자열 인수 `example.PrintAndPunctuate(".")`를 보내 호출됩니다.  
  
 다음 예제에서는 정의 및 호출된 `Print`와 `PrintAndPunctuate`를 보여 줍니다.  확장 특성에 액세스하려면 정의 모듈로 <xref:System.Runtime.CompilerServices>를 가져와야 합니다.  
  
### 코드  
  
```vb#  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
  
    <Extension()>   
    Public Sub Print(ByVal aString As String)  
        Console.WriteLine(aString)  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 다음으로 확장 메서드를 범위로 가져와 호출합니다.  
  
```vb#  
Imports ConsoleApplication2.StringExtensions  
Module Module1  
  
    Sub Main()  
  
        Dim example As String = "Example string"  
        example.Print()  
  
        example = "Hello"  
        example.PrintAndPunctuate(".")  
        example.PrintAndPunctuate("!!!!")  
  
    End Sub  
End Module  
```  
  
### 설명  
 이러한 확장 메서드나 이와 유사한 확장 메서드는 범위 안에만 있으면 실행 가능합니다.  확장 메서드가 포함된 모듈이 범위에 있으면 해당 메서드가 IntelliSense에 표시되어 일반적인 인스턴스 메서드와 마찬가지로 호출될 수 있습니다.  
  
 메서드를 호출하면 첫 번째 매개 변수에 대해서는 인수가 전달되지 않는다는 점에 주의하십시오.  앞에서 설명한 메서드 정의에서 `aString` 매개 변수는 해당 메서드를 호출하는 `String`의 인스턴스인 `example`에 바인딩됩니다.  컴파일러에서는 `example`을 첫 번째 매개 변수에 전달되는 인수로 사용합니다.  
  
 `Nothing`으로 설정된 개체에 대해 확장 메서드가 호출된 경우 확장 메서드가 실행됩니다.  이 작업은 일반 인스턴스 메서드에 적용되지 않습니다.  확장 메서드에서 `Nothing`을 명시적으로 확인할 수 있습니다.  
  
## 확장할 수 있는 형식  
 다음과 같은 형식을 포함하여 Visual Basic 매개 변수 목록에 표시할 수 있는 대부분의 형식에 대해 확장 메서드를 정의할 수 있습니다.  
  
-   클래스\(참조 형식\)  
  
-   구조체\(값 형식\)  
  
-   인터페이스  
  
-   대리자  
  
-   ByRef 및 ByVal 인수  
  
-   제네릭 메서드 매개 변수  
  
-   배열  
  
 첫 번째 매개 변수는 확장 메서드에서 확장할 데이터 형식을 지정하기 때문에 필수적 요소이며 선택적 요소가 아닙니다.  이 이유 때문에 `Optional` 매개 변수와 `ParamArray` 매개 변수는 매개 변수 목록에서 첫 번째 매개 변수가 될 수 없습니다.  
  
 런타임에 바인딩에서는 확장 메서드가 고려되지 않습니다.  다음 예제에서 `anObject.PrintMe()` 문이 <xref:System.MissingMemberException> 예외를 발생시킵니다. 이 예외는 두 번째 `PrintMe` 확장 메서드 정의가 삭제되었을 때 나타나는 예외와 동일합니다.  
  
 [!code-vb[VbVbalrExtensionMethods#9](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/extension-methods_4.vb)]  
  
## 최선의 구현 방법  
 확장 메서드를 사용하면 강력하면서도 편리한 방법으로 기존 형식을 확장할 수 있습니다.  그러나 확장 메서드를 제대로 사용하려면 몇 가지 사항을 고려해야 합니다.  이러한 고려 사항은 주로 클래스 라이브러리 작성에만 적용되지만 확장 메서드를 사용하는 응용 프로그램에도 영향을 줄 수 있습니다.  
  
 일반적으로 자신이 소유하지 않은 형식에 추가하는 확장 메서드는 자신이 제어할 수 있는 형식에 추가하는 확장 메서드보다 취약합니다.  자신이 클래스를 소유하고 있지 않은 경우에는 확장 메서드를 방해할 수 있는 여러 가지 요소가 발생할 수 있습니다.  
  
-   인수와 매개 변수 사이에 축소 변환이 필요하지 않고 호출하는 문의 인수와 호환되는 시그니처를 가진 액세스 가능한 인스턴스 멤버가 있으면 해당 인스턴스 메서드가 다른 모든 확장 메서드보다 우선적으로 사용됩니다.  따라서 나중에라도 클래스에 적절한 인스턴스 메서드가 추가되면 기존에 사용하던 확장 멤버에 액세스하지 못하게 될 수 있습니다.  
  
-   확장 메서드 작성자는 원래 확장 메서드보다 더 높은 우선 순위의 충돌하는 확장 메서드를 다른 프로그래머가 작성하지 못하도록 방지할 수 없습니다.  
  
-   기존 네임스페이스에서 확장 메서드를 정의하면 안정성을 높일 수 있습니다.  이렇게 하면 라이브러리 사용자가 네임스페이스를 포함 또는 제외하거나, 라이브러리의 나머지 네임스페이스와 별도로 일부 네임스페이스를 선택할 수 있습니다.  
  
-   인터페이스나 클래스를 소유하고 있지 않은 경우에는 클래스보다는 인터페이스를 확장하는 것이 더 안전합니다.  인터페이스에 대한 변경 사항은 해당 인터페이스를 구현하는 모든 클래스에 영향을 주기 때문에  작성자가 인터페이스에서 메서드를 추가하거나 변경할 가능성이 적습니다.  그러나 클래스에서 동일한 시그니처를 사용하는 확장 메서드가 있는 두 개의 인터페이스를 구현할 경우 두 확장 메서드가 모두 표시되지 않습니다.  
  
-   가능하면 가장 구체적인 형식을 확장합니다.  형식 계층 구조에서 파생 형식이 많은 형식을 선택할 경우에는 자신이 만든 확장 메서드에 방해가 될 수 있는 인스턴스 메서드나 다른 확장 메서드가 생길 가능성이 높습니다.  
  
## 확장 메서드, 인스턴스 메서드 및 속성  
 범위 내 인스턴스 메서드에 호출 문의 인수와 호환되는 시그니처가 있는 경우 해당 인스턴스 메서드가 다른 모든 확장 메서드보다 우선적으로 사용됩니다.  확장 메서드가 일치할 확률이 높더라도 해당 인스턴스 메서드가 우선적으로 사용됩니다.  다음 예제에서 `ExampleClass`에는 `Integer` 형식의 매개 변수를 하나 사용하는 `ExampleMethod`라는 인스턴스 메서드가 들어 있습니다.  확장 메서드 `ExampleMethod`는 `ExampleClass`를 확장하며 `Long` 형식의 매개 변수를 하나 사용합니다.  
  
 [!code-vb[VbVbalrExtensionMethods#4](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/extension-methods_5.vb)]  
  
 다음 코드에서 첫 번째 `ExampleMethod` 호출은 확장 메서드를 호출하는데 이는 `arg1`이 `Long`이어서 확장 메서드의 `Long` 매개 변수와만 호환되기 때문입니다.  두 번째 `ExampleMethod` 호출에서는 `Integer` 인수 `arg2`를 사용하므로 인스턴스 메서드를 호출합니다.  
  
 [!code-vb[VbVbalrExtensionMethods#5](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/extension-methods_6.vb)]  
  
 이제 두 메서드에 있는 매개 변수의 데이터 형식을 반대로 바꿔 보겠습니다.  
  
 [!code-vb[VbVbalrExtensionMethods#6](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/extension-methods_7.vb)]  
  
 이번에는 `Main` 코드에서 두 번 모두 인스턴스 메서드를 호출합니다.  이는 `arg1`과 `arg2`가 모두 `Long`으로 확대 변환될 수 있으며, 두 경우 모두에서 인스턴스 메서드가 확장 메서드보다 우선적으로 사용되기 때문입니다.  
  
 [!code-vb[VbVbalrExtensionMethods#7](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/extension-methods_8.vb)]  
  
 즉, 확장 메서드는 기존 인스턴스 메서드를 대체할 수 없습니다.  그러나 확장 메서드가 인스턴스 메서드와 이름은 같지만 시그니처가 다른 경우에는 두 메서드 모두 사용할 수 있습니다.  예를 들어 `ExampleClass` 클래스에 인수를 사용하지 않는 `ExampleMethod`라는 메서드가 있는 경우, 다음 예제와 같이 이름이 같지만 시그니처가 다른 확장 메서드를 사용할 수 있습니다.  
  
 [!code-vb[VbVbalrExtensionMethods#8](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/extension-methods_9.vb)]  
  
 이 코드의 출력은 다음과 같습니다.  
  
 `Extension method`  
  
 `Instance method`  
  
 속성의 경우에는 보다 간단합니다. 확장 메서드의 이름이 메서드가 확장하는 클래스의 속성 이름과 같을 경우 확장 메서드가 표시되지 않으므로 사용할 수 없습니다.  
  
## 확장 메서드 우선 순위  
 시그니처가 동일한 두 확장 메서드가 범위에 있고 액세스 가능한 경우에는 우선 순위가 높은 메서드가 호출됩니다.  확장 메서드의 우선 순위는 메서드를 범위로 가져오는 데 사용된 메커니즘에 따라 정해집니다.  다음 목록은 최상위에서 최하위 순으로 우선 순위 계층 구조를 보여 줍니다.  
  
1.  현재 모듈 안에 정의된 확장 메서드  
  
2.  현재 네임스페이스 또는 부모 네임스페이스 중 하나에서 데이터 형식 안에 정의된 확장 메서드\(자식 네임스페이스가 부모 네임스페이스보다 우선 순위가 높음\)  
  
3.  현재 파일에서 형식 가져오기 안에 정의된 확장 메서드  
  
4.  현재 파일에서 네임스페이스 가져오기 안에 정의된 확장 메서드  
  
5.  프로젝트 수준의 형식 가져오기 안에 정의된 확장 메서드  
  
6.  프로젝트 수준의 네임스페이스 가져오기 안에 정의된 확장 메서드  
  
 이 우선 순위로 모호성을 해결할 수 없는 경우에는 정규화된 이름을 사용하여 호출할 메서드를 지정할 수 있습니다.  앞의 예제에 나온 `Print` 메서드가 `StringExtensions`라는 모듈에 정의된 경우 정규화된 이름은 `example.Print()`가 아니라 `StringExtensions.Print(example)`입니다.  
  
## 참고 항목  
 <xref:System.Runtime.CompilerServices>   
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>   
 [확장 메서드](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [Module Statement](../../../../visual-basic/language-reference/statements/module-statement.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Parameter Arrays](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)