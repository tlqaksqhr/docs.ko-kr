---
title: "확장 메서드 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ExtensionMethods
dev_langs:
- VB
helpviewer_keywords:
- extending data types
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
caps.latest.revision: 41
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 381fa0db2d92590d23ebd71a7823a8465e94a6e6
ms.lasthandoff: 03/13/2017

---
# <a name="extension-methods-visual-basic"></a>확장명 메서드(Visual Basic)
확장 메서드는 파생된 형식을 새로 만들지 않고 이미 정의 되어 있는 데이터 형식에 사용자 지정 기능을 추가 하는 개발자를 사용 합니다. 확장 메서드 있게 마치 기존 형식의 인스턴스 메서드인 것 처럼 호출할 수 있는 메서드를 작성 합니다.  
  
## <a name="remarks"></a>주의  
 확장 메서드 수만 `Sub` 프로시저 또는 `Function` 프로시저입니다. 확장 속성, 필드 또는 이벤트를 정의할 수 없습니다. 모든 확장 메서드는 확장 특성으로 표시 해야 `<Extension()>` 에서 <xref:System.Runtime.CompilerServices?displayProperty=fullName>네임 스페이스.</xref:System.Runtime.CompilerServices?displayProperty=fullName>  
  
 확장 메서드 정의의 첫 번째 매개 변수는 메서드가 확장 하는 데이터 형식을 지정 합니다. 메서드가 실행 될 때 첫 번째 매개 변수 인스턴스의 메서드를 호출 하는 데이터 형식에 바인딩됩니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 정의 `Print` 확장을는 <xref:System.String>데이터 형식.</xref:System.String> 메서드를 사용 하 여 `Console.WriteLine` 는 문자열을 표시 합니다. 매개 변수는 `Print` 메서드를 `aString`, 메서드는 <xref:System.String>클래스</xref:System.String> 확장 설정  
  
 [!code-vb[VbVbalrExtensionMethods #&1;](./codesnippet/VisualBasic/extension-methods_1.vb)]  
  
 확장 메서드 정의 확장 특성으로 표시 됩니다 `<Extension()>`합니다. 메서드가 정의 된 모듈을 표시 하는 것은 선택적 이지만 각 확장 메서드가 표시 되어야 합니다. <xref:System.Runtime.CompilerServices>확장 특성에 액세스 하기 위해 가져와야 합니다.</xref:System.Runtime.CompilerServices>  
  
 확장 메서드는 모듈 내 에서만 선언할 수 있습니다. 일반적으로 확장 메서드가 정의 된 모듈 호출 되는 것과 동일한 모듈이 아닙니다. 대신, 확장 메서드를 포함 하는 모듈을 가져온 범위 가져오는 되어야 하는 경우. 포함 된 모듈 후 `Print` 는 범위에는 메서드 마치 인수를 받지 않는 같은 일반 인스턴스 메서드인 것 처럼 `ToUpper`:  
  
 [!code-vb[VbVbalrExtensionMethods #&2;](./codesnippet/VisualBasic/extension-methods_2.vb)]  
  
 다음 예제에서는 `PrintAndPunctuate`에 대 한 확장 이기도 <xref:System.String>,이 이번에 두 개의 매개 변수를 사용 하 여 정의 합니다.</xref:System.String> 첫 번째 매개 변수 `aString`, 확장 메서드는 <xref:System.String>.</xref:System.String> 확장 설정 두 번째 매개 변수 `punc`, 문장 부호는 메서드를 호출할 때 인수로 전달 되는 문자열 이어야 하기 위함입니다. 메서드 뒤에 문장 부호는 문자열을 표시 합니다.  
  
 [!code-vb[VbVbalrExtensionMethods #&3;](./codesnippet/VisualBasic/extension-methods_3.vb)]  
  
 메서드는 문자열 인수에 대 한 전송 하 여 `punc`:`example.PrintAndPunctuate(".")`  
  
 다음 예제에서는 `Print` 및 `PrintAndPunctuate` 정의 및 호출 합니다. <xref:System.Runtime.CompilerServices>확장 특성에 액세스할 수 있도록 하기 위해 정의 모듈에서 가져오게 됩니다.</xref:System.Runtime.CompilerServices>  
  
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
  
 다음으로, 확장 메서드를 범위로 가져올 및 호출 됩니다.  
  
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
 실행할 수 있으려면 요구 또는 이와 유사한 확장 메서드 범위에서 될 것입니다. 확장 메서드를 포함 하는 모듈 범위에 있으면 IntelliSense에 표시 되어 하 고 일반적인 인스턴스 메서드인 것 처럼 호출할 수 있습니다.  
  
 메서드를 호출할 때 인수가 전달 되지 첫 번째 매개 변수를 확인 합니다. 매개 변수 `aString` 이전 메서드 정의에 바인딩된 `example`, 인스턴스의 `String` 호출 하 합니다. 컴파일러는 사용 하 여 `example` 첫 번째 매개 변수로 전달 되는 인수로 합니다.  
  
 로 설정 된 개체에 대 한 확장 메서드를 호출 하는 경우 `Nothing`, 확장 메서드를 실행 합니다. 표준 인스턴스 메서드인에는 적용 되지 않습니다. 명시적으로 확인할 수 있습니다 `Nothing` 확장 메서드에서.  
  
## <a name="types-that-can-be-extended"></a>확장할 수 있는 형식  
 다음을 포함 하는 Visual Basic 매개 변수 목록에 표시할 수 있는 대부분의 형식에는 확장 메서드를 정의할 수 있습니다.  
  
-   클래스 (참조 형식)  
  
-   구조체 (값 형식)  
  
-   인터페이스  
  
-   대리자  
  
-   ByRef 및 ByVal 인수  
  
-   제네릭 메서드 매개 변수  
  
-   배열  
  
 첫 번째 매개 변수는 확장 메서드를 확장 하는 데이터 형식으로 지정 하므로 필요 하며 선택적 수 없습니다. 이런 이유로 `Optional` 매개 변수 및 `ParamArray` 매개 변수는 매개 변수 목록에서 첫 번째 매개 변수 수 없습니다.  
  
 런타임에 바인딩에서는 확장 메서드를 사용 하는 것이 아닙니다. 다음 예에서 문은 `anObject.PrintMe()` 를 발생 시킵니다는 <xref:System.MissingMemberException>예외, 동일한 예외 경우 두 번째 `PrintMe` 확장 메서드 정의 삭제 되었습니다.</xref:System.MissingMemberException>  
  
 [!code-vb[VbVbalrExtensionMethods #&9;](./codesnippet/VisualBasic/extension-methods_4.vb)]  
  
## <a name="best-practices"></a>모범 사례  
 확장 메서드는 기존 형식을 확장 하는 편리 하 고 강력한 방법을 제공 합니다. 그러나이 성공적으로 사용 하려면 있습니다 몇 가지 사항을 고려해 야 합니다. 이러한 고려 사항은 주로 클래스 라이브러리 작성에 적용 되지만 확장 메서드를 사용 하는 모든 응용 프로그램에 영향을 줄 수 있습니다.  
  
 가장 일반적으로 소유 하지 않은 형식에 추가 하는 확장 메서드는 사용자가 제어 하는 형식에 추가 하는 확장 메서드보다 더 취약 합니다. 여러 가지 확장 메서드를 방해할 수 있는 소유 하지 않은 클래스에 발생할 수 있습니다.  
  
-   액세스할 수 있는 인스턴스 멤버와 매개 변수에 필요한 인수에서 축소 변환을 문 호출의 인수와 호환 되는 시그니처가 있는 있으면 모든 확장 메서드 대신 인스턴스 메서드가 사용 됩니다. 따라서 적절 한 인스턴스 메서드는 언젠가 클래스에 추가 되 면에 의존 하는 기존 확장 멤버 수 없게 됩니다.  
  
-   확장 메서드의 작성자는 원래 확장 우선 순위를 있을 수 있는 충돌 하는 확장 메서드 작성에서 다른 프로그래머가 방지할 수 없습니다.  
  
-   네임 스페이스에 확장 메서드를 삽입 하 여 견고성을 향상 시킬 수 있습니다. 라이브러리 소비자가 다음 네임 스페이스를 포함 또는 제외, 되거나 라이브러리의 나머지 부분에서 별도로 네임 스페이스 중에서 선택 합니다.  
  
-   인터페이스를 확장 인터페이스 또는 클래스를 소유 하지 않은 경우에 특히 클래스를 확장 하는 것 보다 더 안전할 수도 있습니다. 인터페이스의 변경을 구현 하는 모든 클래스를 영향을 줍니다. 따라서 작성자는 추가 하거나 인터페이스에서 메서드를 변경 하려면 가능성이 줄어들 수 있습니다. 그러나 클래스는 서명이 같은 확장 메서드가 있는 두 가지 인터페이스를 구현 하는 경우 확장 메서드 모두 표시 됩니다.  
  
-   할 수 있습니다 가장 구체적인 형식을 확장 합니다. 형식 계층 구조, 여러 가지 다른 형식을 파생 되는 형식을 선택 하면는 인스턴스 메서드 또는 사용자 방해할 수 있는 다른 확장 메서드가 도입 가능성이 있습니다.  
  
## <a name="extension-methods-instance-methods-and-properties"></a>확장 메서드, 인스턴스 메서드 및 속성  
 범위 내의 인스턴스 메서드인에 문 호출의 인수와 호환 되는 서명이 있는 경우 모든 확장 메서드 대신 인스턴스 메서드를 사용 하 여 선택 됩니다. 인스턴스 메서드가 확장 메서드는 더 잘 일치 하는 경우에 우선을 순위가 있습니다. 다음 예에서 `ExampleClass` 라는 인스턴스 메서드를 포함 `ExampleMethod` 매개 변수가 하나 형식의 `Integer`합니다. 확장 메서드 `ExampleMethod` 확장 `ExampleClass`, 형식의 매개 변수가 하나 있고 `Long`합니다.  
  
 [!code-vb[VbVbalrExtensionMethods #&4;](./codesnippet/VisualBasic/extension-methods_5.vb)]  
  
 첫 번째 호출 `ExampleMethod` 때문에 다음 코드에는 확장 메서드를 호출 `arg1` 는 `Long` 과 호환 되며는 `Long` 확장 메서드의 매개 변수입니다. 두 번째 호출은 `ExampleMethod` 에 `Integer` 인수 `arg2`, 인스턴스 메서드를 호출 합니다.  
  
 [!code-vb[VbVbalrExtensionMethods #&5;](./codesnippet/VisualBasic/extension-methods_6.vb)]  
  
 이제 역방향 두 메서드에 있는 매개 변수의 데이터 형식:  
  
 [!code-vb[VbVbalrExtensionMethods #&6;](./codesnippet/VisualBasic/extension-methods_7.vb)]  
  
 이번에 코드에서 `Main` 인스턴스 메서드를 두 번 호출 합니다. 즉, 둘 다 `arg1` 및 `arg2` 확대 변환에 `Long`, 인스턴스 메서드가 확장 메서드 두 경우 모두 보다 우선 합니다.  
  
 [!code-vb[VbVbalrExtensionMethods #&7;](./codesnippet/VisualBasic/extension-methods_8.vb)]  
  
 따라서 확장 메서드는 기존 인스턴스 메서드를 바꿀 수 없습니다. 그러나 확장 메서드 이름이 같은 인스턴스 메서드로 하지만 서명을 충돌 하지 않는 경우 두 가지 방법은 모두 액세스할 수 있습니다. 예를 들어 하는 경우 클래스 `ExampleClass` 라는 메서드가 있는 `ExampleMethod` 인수 없음, 이름이 같은 확장 메서드를 사용 하지만 다음 코드와 같이 다른 서명을 허용 됩니다.  
  
 [!code-vb[VbVbalrExtensionMethods #&8;](./codesnippet/VisualBasic/extension-methods_9.vb)]  
  
 이 코드의 출력은 다음과 같습니다.  
  
 `Extension method`  
  
 `Instance method`  
  
 상황은 속성으로 간단: 확장 클래스의 속성으로는 확장 메서드를 사용 하는 같은 이름의 경우 확장 메서드 표시 되지 않으며 액세스할 수 없습니다.  
  
## <a name="extension-method-precedence"></a>확장 메서드 우선 순위  
 시그니처가 같은 두 가지 확장 메서드 범위에서 하 고 액세스할 수 있는 경우 우선 순위가 높은 것이 호출 됩니다. 확장 메서드의 우선 순위는 메서드를 범위로 가져올 하는 데 사용 하는 메커니즘을 기반으로 합니다. 다음 목록에서는 우선 순위 계층에서 순위가 높은 것을 보여 줍니다.  
  
1.  현재 모듈 내에 정의 된 메서드를 확장 합니다.  
  
2.  확장 메서드 정의 된 데이터 내부의 형식은 현재 네임 스페이스 또는 부모 중 하나에 자식 네임 스페이스가 부모 네임 스페이스 보다 우선 순위가 높습니다.  
  
3.  확장 메서드는 현재 파일의 형식 가져오기 안에 정의 합니다.  
  
4.  확장 메서드는 현재 파일의 네임 스페이스 가져오기 내에서 정의 합니다.  
  
5.  프로젝트 수준의 형식 가져오기 안에 정의 된 확장 메서드.  
  
6.  프로젝트 수준의 네임 스페이스 가져오기 안에 정의 된 확장 메서드.  
  
 우선 순위는 모호성을 해결 되지 않으면, 호출 하는 방법을 지정 하는 정규화 된 이름을 사용할 수 있습니다. 하는 경우는 `Print` 앞의 예제에는 메서드가 라는 모듈에 정의 되어 `StringExtensions`, 정규화 된 이름이 `StringExtensions.Print(example)` 대신 `example.Print()`합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.CompilerServices></xref:System.Runtime.CompilerServices>   
 <xref:System.Runtime.CompilerServices.ExtensionAttribute></xref:System.Runtime.CompilerServices.ExtensionAttribute>   
 [확장 메서드](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [Module 문](../../../../visual-basic/language-reference/statements/module-statement.md)   
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)   
 [선택적 매개 변수](./optional-parameters.md)   
 [매개 변수 배열](./parameter-arrays.md)   
 [특성 개요](../../../../visual-basic/programming-guide/concepts/attributes/index.md)   
 [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
