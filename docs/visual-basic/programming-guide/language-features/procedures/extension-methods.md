---
title: 확장 메서드(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
caps.latest.revision: 41
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d3db3bc2b213b78ef2dceebcf56c9d5fbfa3016e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="extension-methods-visual-basic"></a>확장 메서드(Visual Basic)
확장 메서드는 개발자가 새 파생된 형식을 만들지 않고 이미 정의 되어 있는 데이터 형식에 사용자 지정 기능을 추가할 수를 사용 합니다. 확장 메서드는 기존 형식의 인스턴스 메서드인 것 처럼 호출할 수 있는 메서드를 작성할 수 있도록 설정 합니다.  
  
## <a name="remarks"></a>설명  
 확장 메서드 수만 `Sub` 프로시저 또는 `Function` 프로시저입니다. 확장 속성, 필드 또는 이벤트를 정의할 수 없습니다. 모든 확장 메서드가 확장 특성으로 표시 해야 `<Extension()>` 에서 <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> 네임 스페이스입니다.  
  
 확장 메서드 정의의 첫 번째 매개 변수는 메서드가 확장 하는 데이터 형식을 지정 합니다. 메서드를 실행할 때 첫 번째 매개 변수 메서드를 호출 하는 데이터 형식의 인스턴스에 바인딩됩니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 정의 `Print` 확장을는 <xref:System.String> 데이터 형식입니다. 메서드에서 사용 `Console.WriteLine` 문자열로 표시 합니다. 매개 변수는 `Print` 메서드를 `aString`를 설정 하는 메서드를 확장 하 고 <xref:System.String> 클래스.  
  
 [!code-vb[VbVbalrExtensionMethods#1](./codesnippet/VisualBasic/extension-methods_1.vb)]  
  
 확장 메서드 정의 확장 특성으로 표시 된 것을 알 `<Extension()>`합니다. 메서드가 정의 된 모듈을 표시 하는 것은 옵션 이지만 각 확장 메서드를 표시 합니다. <xref:System.Runtime.CompilerServices>확장 특성에 액세스 하기 위해 가져와야 합니다.  
  
 확장 메서드는 모듈 내 에서만 선언할 수 있습니다. 일반적으로 확장 메서드가 정의 된 모듈에서 호출 된 것과 동일한 모듈이 아닙니다. 대신 확장 메서드를 포함 하는 모듈을 가져온 범위 가져오는 되어야 하는 경우. 포함 된 모듈 후 `Print` 는 범위에는 메서드 인수 사용 하지 않는와 같은 일반적인 인스턴스 메서드인 것 처럼 경우 `ToUpper`:  
  
 [!code-vb[VbVbalrExtensionMethods#2](./codesnippet/VisualBasic/extension-methods_2.vb)]  
  
 다음 예제에서는 `PrintAndPunctuate`에 대 한 확장 이기도 <xref:System.String>,이 시간을 두 개의 매개 변수를 사용 하 여 정의 합니다. 첫 번째 매개 변수 `aString`를 설정 하는 확장 메서드를 확장 하 <xref:System.String>합니다. 두 번째 매개 변수 `punc`는 메서드를 호출할 때 인수로 전달 되는 문장 부호는 문자열을 되도록 만들어졌습니다. 메서드는 문자열과 문장 부호를 표시 합니다.  
  
 [!code-vb[VbVbalrExtensionMethods#3](./codesnippet/VisualBasic/extension-methods_3.vb)]  
  
 에 대 한 문자열 인수에 전송 하 여 메서드는 `punc`:`example.PrintAndPunctuate(".")`  
  
 다음 예제와 `Print` 및 `PrintAndPunctuate` 정의 되 고 호출 합니다. <xref:System.Runtime.CompilerServices>확장 특성에 액세스할 수 있도록 하기 위해 정의 모듈의 가져오게 됩니다.  
  
### <a name="code"></a>코드  
  
```vb  
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
  
 그런 다음 확장 메서드를 범위로 가져올 되며 호출 됩니다.  
  
```vb  
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
  
### <a name="comments"></a>설명  
 실행할 수 있게 되기를 요구 또는 이와 유사한 확장 메서드는 범위에 포함 된 것입니다. 확장 메서드를 포함 하는 모듈 범위에 있으면 IntelliSense에 표시 되어 하 고 일반적인 인스턴스 메서드인 것 처럼 호출할 수 있습니다.  
  
 하는 메서드를 호출할 때 인수가 전송 되지 첫 번째 매개 변수에 대 한 확인 합니다. 매개 변수 `aString` 이전 메서드 정의에 바인딩된 `example`, 인스턴스의 `String` 호출 하 합니다. 컴파일러에서 사용 `example` 첫 번째 매개 변수를 전달 하는 인수입니다.  
  
 로 설정 된 개체에 대 한 확장 메서드를 호출 하는 경우 `Nothing`, 확장 메서드를 실행 합니다. 일반적인 인스턴스 메서드에 적용 되지 않습니다. 명시적으로 확인할 수 있습니다 `Nothing` 확장 메서드에서.  
  
## <a name="types-that-can-be-extended"></a>확장할 수 있는 형식  
 다음을 포함 하는 Visual Basic 매개 변수 목록에서 표시할 수 있는 대부분의 종류에는 확장 메서드를 정의할 수 있습니다.  
  
-   클래스 (참조 형식)  
  
-   구조체 (값 형식)  
  
-   인터페이스  
  
-   대리자  
  
-   ByRef 및 ByVal 인수  
  
-   제네릭 메서드 매개 변수  
  
-   배열  
  
 첫 번째 매개 변수는 확장 메서드를 확장 하는 데이터 형식을 지정 하기 때문에 필요 하 고 선택 사항이 될 수 없습니다. 이런 이유로 `Optional` 매개 변수 및 `ParamArray` 매개 변수는 매개 변수 목록에서 첫 번째 매개 변수 수 없습니다.  
  
 런타임에 바인딩에서는 확장 메서드를 사용 하는 것이 아닙니다. 다음 예에서 문은 `anObject.PrintMe()` 발생는 <xref:System.MissingMemberException> 예외, 표시 되는 경우 동일한 예외 두 번째 `PrintMe` 확장 메서드 정의 삭제 되었습니다.  
  
 [!code-vb[VbVbalrExtensionMethods#9](./codesnippet/VisualBasic/extension-methods_4.vb)]  
  
## <a name="best-practices"></a>모범 사례  
 확장 메서드는 기존 형식을 확장할 수는 편리 하 고 강력한 방법을 제공 합니다. 그러나 메서드를 제대로 사용 하려면 있습니다 몇 가지 사항을 고려해 야 합니다. 이러한 고려 사항은 클래스 라이브러리 작성에 주로 적용 하지만 확장 메서드를 사용 하는 모든 응용 프로그램에 영향을 줄 수 있습니다.  
  
 가장 일반적으로 소유 하지 않은 형식에 추가 하는 확장 메서드는 사용자가 제어 하는 형식에 추가 하는 확장 메서드 보다 더 취약. 몇 가지 확장 메서드를 방해할 수 있는 소유 하지 않은 클래스에 발생할 수 있습니다.  
  
-   인수에서 매개 변수에 필요한 축소 변환이와 문 호출의 인수와 호환 되는 시그니처가 있는 액세스 가능한 인스턴스 멤버 있으면 인스턴스 메서드를 사용 하는 모든 확장 메서드를 대신 사용 됩니다. 따라서 특정 시점에는 클래스에 적절 한 인스턴스 메서드를 추가 하는 경우에 의존 하는 기존 확장 멤버 수 없게 됩니다.  
  
-   확장 메서드의 작성자는 원래 확장 우선 순위를 있을 수 있는 충돌 하는 확장 메서드 작성에서 프로그래머를 방지할 수 없습니다.  
  
-   네임 스페이스에 확장 메서드를 삽입 하 여 견고성을 향상 시킬 수 있습니다. 라이브러리의 소비자 수 다음 네임 스페이스를 포함 또는 제외, 또는 라이브러리의 나머지 부분에서 개별적으로 네임 스페이스 중에서 선택 하십시오.  
  
-   인터페이스를 확장 인터페이스 또는 클래스를 소유 하지 않은 경우에 특히 클래스를 확장 하는 것 보다 더 안전 하 게 수도 있습니다. 인터페이스의 변경을 구현 하는 모든 클래스를 영향을 줍니다. 따라서 작성자를 추가 하거나 인터페이스의 메서드를 변경 가능성이 줄어들 수 있습니다. 그러나 클래스는 동일한 서명으로 확장 메서드가 있는 두 개의 인터페이스를 구현 하는 경우 둘 중 한 확장 방법이 표시 됩니다.  
  
-   확장 가장 구체적인 형식 할 수 있습니다. 형식 계층 구조에서 여러 가지 다른 형식을 파생 되는 유형을 선택 하면 많은 경우 가능성이 인스턴스 메서드 또는 사용자 작업과 방해할 수 있는 다른 확장 메서드를 도입 합니다.  
  
## <a name="extension-methods-instance-methods-and-properties"></a>확장 메서드, 인스턴스 메서드 및 속성  
 범위에서 인스턴스 메서드 서명이 문 호출의 인수와 호환 되는, 하는 경우 모든 확장 메서드 대신 인스턴스 메서드 선택 됩니다. 인스턴스 메서드를 사용 하는 확장 메서드는 일치 하는 경우에 순위가 있습니다. 다음 예에서 `ExampleClass` 라는 인스턴스 메서드를 포함 `ExampleMethod` 형식의 매개 변수 `Integer`합니다. 확장 메서드 `ExampleMethod` 확장 `ExampleClass`, 형식의 매개 변수가 하나 있으며 `Long`합니다.  
  
 [!code-vb[VbVbalrExtensionMethods#4](./codesnippet/VisualBasic/extension-methods_5.vb)]  
  
 첫 번째 호출 `ExampleMethod` 하기 때문에 다음 코드에서 확장 메서드를 호출 `arg1` 은 `Long` 와 호환 됩니다는 `Long` 확장 메서드의 매개 변수입니다. 두 번째 호출으로 `ExampleMethod` 에 `Integer` 인수 `arg2`, 인스턴스 메서드를 호출 합니다.  
  
 [!code-vb[VbVbalrExtensionMethods#5](./codesnippet/VisualBasic/extension-methods_6.vb)]  
  
 이제는 두 가지 방법에서 매개 변수의 데이터 형식과 역방향:  
  
 [!code-vb[VbVbalrExtensionMethods#6](./codesnippet/VisualBasic/extension-methods_7.vb)]  
  
 코드. 이때 `Main` 인스턴스 메서드를 두 번 호출 합니다. ¿¡´ 모두 `arg1` 및 `arg2` 확대 변환이 필요 `Long`, 인스턴스 메서드를 사용 하는 두 경우 모두 확장 메서드 보다 우선 합니다.  
  
 [!code-vb[VbVbalrExtensionMethods#7](./codesnippet/VisualBasic/extension-methods_8.vb)]  
  
 따라서 확장 메서드는 기존 인스턴스 메서드를 바꿀 수 없습니다. 그러나 확장 메서드는 인스턴스 메서드와 동일한 이름을 하지만 서명이 충돌 하지 않는 경우 두 방법 모두를 액세스할 수 있습니다. 예를 들어 경우 클래스 `ExampleClass` 라는 메서드가 있는 `ExampleMethod` 없고 인수, 같은 이름의 확장 메서드를 사용 하지만 다음 코드에 나와 있는 것 처럼 다른 서명이 허용 됩니다.  
  
 [!code-vb[VbVbalrExtensionMethods#8](./codesnippet/VisualBasic/extension-methods_9.vb)]  
  
 이 코드에서 출력은 다음과 같습니다.  
  
 `Extension method`  
  
 `Instance method`  
  
 상황은 속성이 있는 간단한: 확장 클래스의 속성으로 확장 메서드를 사용 하는 같은 이름의 경우 확장 메서드가 표시 되지 않으며 액세스할 수 없습니다.  
  
## <a name="extension-method-precedence"></a>확장 메서드 우선 순위  
 시그니처가 같은 두 가지 확장 메서드 범위에 액세스할 수 있는 경우 우선 순위가 높은 것 호출 됩니다. 확장 메서드의 선행 메서드를 범위로 가져오기에 사용 되는 메커니즘을 기반으로 합니다. 다음 목록은 내림차순 우선 순위 계층 구조를 보여 줍니다.  
  
1.  현재 모듈 내에 정의 된 확장 메서드입니다.  
  
2.  확장 메서드 내에 정의 된 데이터 형식을 현재 네임 스페이스 또는 부모 중 하나에 부모 네임 스페이스 보다 우선 순위가 자식 네임 스페이스가 있습니다.  
  
3.  현재 파일에서 형식 가져오기 내에 정의 된 확장 메서드.  
  
4.  현재 파일의 네임 스페이스 가져오기 내에 정의 된 확장 메서드.  
  
5.  프로젝트 수준의 형식 가져오기 안에 정의 된 확장 메서드.  
  
6.  프로젝트 수준의 네임 스페이스 가져오기 내에 정의 된 확장 메서드.  
  
 우선 순위는 모호성을 해결 되지 않으면, 호출 하는 방법을 지정 하는 정규화 된 이름을 사용할 수 있습니다. 경우는 `Print` 앞의 예제에서 메서드가 라는 모듈에 정의 된 `StringExtensions`, 정규화 된 이름이 `StringExtensions.Print(example)` 대신 `example.Print()`합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.CompilerServices>  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>  
 [확장명 메서드](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)  
 [Module 문](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [선택적 매개 변수](./optional-parameters.md)  
 [매개 변수 배열](./parameter-arrays.md)  
 [특성 개요](../../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
