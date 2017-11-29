---
title: "방법: 확장명 메서드 작성(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65cdabf59886e7457a327ee9cde968a6a73f2280
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="83b5a-102">방법: 확장명 메서드 작성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83b5a-102">How to: Write an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="83b5a-103">확장 메서드를 사용 하 여 기존 클래스에 메서드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83b5a-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="83b5a-104">해당 클래스의 인스턴스 된 확장 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83b5a-104">The extension method can be called as if it were an instance of that class.</span></span>  
  
### <a name="to-define-an-extension-method"></a><span data-ttu-id="83b5a-105">확장 메서드를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="83b5a-105">To define an extension method</span></span>  
  
1.  <span data-ttu-id="83b5a-106">Visual Studio에서 기존 또는 새 Visual Basic 응용 프로그램을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="83b5a-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="83b5a-107">확장 메서드를 정의 하려는 파일 맨 위에 있는 다음 import 문을 포함:</span><span class="sxs-lookup"><span data-stu-id="83b5a-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  <span data-ttu-id="83b5a-108">기존 또는 새 응용 프로그램에서 모듈 내에서 확장 특성으로 메서드 정의 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="83b5a-108">Within a module in your new or existing application, begin the method definition with the extension attribute:</span></span>  
  
    ```  
    <Extension()>  
    ```  
  
4.  <span data-ttu-id="83b5a-109">일반적인 방법으로 메서드를 선언는 첫 번째 매개 변수 형식의 확장 하려는 데이터 형식을 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83b5a-109">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a><span data-ttu-id="83b5a-110">예제</span><span class="sxs-lookup"><span data-stu-id="83b5a-110">Example</span></span>  
 <span data-ttu-id="83b5a-111">다음 예제에서는 모듈의 확장 메서드를 선언 `StringExtensions`합니다.</span><span class="sxs-lookup"><span data-stu-id="83b5a-111">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="83b5a-112">두 번째 모듈 `Module1`, 가져옵니다 `StringExtensions` 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="83b5a-112">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="83b5a-113">확장 메서드를 호출할 때 범위 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83b5a-113">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="83b5a-114">확장 메서드 `PrintAndPunctuate` 확장은 <xref:System.String> 문자열 인스턴스를 표시 하는 메서드를 사용 하 여 클래스 다음 매개 변수로 전송 문장 부호 기호 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="83b5a-114">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>  
  
```vb  
' Declarations will typically be in a separate module.  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
```vb  
' Import the module that holds the extension method you want to use,   
' and call it.  
  
Imports ConsoleApplication2.StringExtensions  
  
Module Module1  
  
    Sub Main()  
        Dim example = "Hello"  
        example.PrintAndPunctuate("?")  
        example.PrintAndPunctuate("!!!!")  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="83b5a-115">고 해당 메서드는 두 개의 매개 변수를 사용 하 여 정의 중 하나만 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83b5a-115">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="83b5a-116">첫 번째 매개 변수 `aString`, 메서드 정의에 바인딩된 `example`, 인스턴스의 `String` 메서드를 호출 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="83b5a-116">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="83b5a-117">예제의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83b5a-117">The output of the example is as follows:</span></span>  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a><span data-ttu-id="83b5a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83b5a-118">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>  
 [<span data-ttu-id="83b5a-119">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="83b5a-119">Extension Methods</span></span>](./extension-methods.md)  
 [<span data-ttu-id="83b5a-120">Module 문</span><span class="sxs-lookup"><span data-stu-id="83b5a-120">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [<span data-ttu-id="83b5a-121">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="83b5a-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="83b5a-122">Visual Basic의 범위</span><span class="sxs-lookup"><span data-stu-id="83b5a-122">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
