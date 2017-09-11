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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0705929da72bcb3001228a90bbb9d5ba7c248bf7
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="extension-methods-visual-basic"></a><span data-ttu-id="eb02c-102">확장명 메서드(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb02c-102">Extension Methods (Visual Basic)</span></span>
<span data-ttu-id="eb02c-103">확장 메서드는 파생된 형식을 새로 만들지 않고 이미 정의 되어 있는 데이터 형식에 사용자 지정 기능을 추가 하는 개발자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-103">Extension methods enable developers to add custom functionality to data types that are already defined without creating a new derived type.</span></span> <span data-ttu-id="eb02c-104">확장 메서드 있게 마치 기존 형식의 인스턴스 메서드인 것 처럼 호출할 수 있는 메서드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-104">Extension methods make it possible to write a method that can be called as if it were an instance method of the existing type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb02c-105">주의</span><span class="sxs-lookup"><span data-stu-id="eb02c-105">Remarks</span></span>  
 <span data-ttu-id="eb02c-106">확장 메서드 수만 `Sub` 프로시저 또는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-106">An extension method can be only a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="eb02c-107">확장 속성, 필드 또는 이벤트를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-107">You cannot define an extension property, field, or event.</span></span> <span data-ttu-id="eb02c-108">모든 확장 메서드는 확장 특성으로 표시 해야 `<Extension()>` 에서 <xref:System.Runtime.CompilerServices?displayProperty=fullName>네임 스페이스.</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="eb02c-108">All extension methods must be marked with the extension attribute `<Extension()>` from the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace.</span></span>  
  
 <span data-ttu-id="eb02c-109">확장 메서드 정의의 첫 번째 매개 변수는 메서드가 확장 하는 데이터 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-109">The first parameter in an extension method definition specifies which data type the method extends.</span></span> <span data-ttu-id="eb02c-110">메서드가 실행 될 때 첫 번째 매개 변수 인스턴스의 메서드를 호출 하는 데이터 형식에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-110">When the method is run, the first parameter is bound to the instance of the data type that invokes the method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb02c-111">예제</span><span class="sxs-lookup"><span data-stu-id="eb02c-111">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="eb02c-112">설명</span><span class="sxs-lookup"><span data-stu-id="eb02c-112">Description</span></span>  
 <span data-ttu-id="eb02c-113">다음 예제에서는 정의 `Print` 확장을는 <xref:System.String>데이터 형식.</xref:System.String></span><span class="sxs-lookup"><span data-stu-id="eb02c-113">The following example defines a `Print` extension to the <xref:System.String> data type.</span></span> <span data-ttu-id="eb02c-114">메서드를 사용 하 여 `Console.WriteLine` 는 문자열을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-114">The method uses `Console.WriteLine` to display a string.</span></span> <span data-ttu-id="eb02c-115">매개 변수는 `Print` 메서드를 `aString`, 메서드는 <xref:System.String>클래스</xref:System.String> 확장 설정</span><span class="sxs-lookup"><span data-stu-id="eb02c-115">The parameter of the `Print` method, `aString`, establishes that the method extends the <xref:System.String> class.</span></span>  
  
 <span data-ttu-id="eb02c-116">[!code-vb[VbVbalrExtensionMethods #&1;](./codesnippet/VisualBasic/extension-methods_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb02c-116">[!code-vb[VbVbalrExtensionMethods#1](./codesnippet/VisualBasic/extension-methods_1.vb)]</span></span>  
  
 <span data-ttu-id="eb02c-117">확장 메서드 정의 확장 특성으로 표시 됩니다 `<Extension()>`합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-117">Notice that the extension method definition is marked with the extension attribute `<Extension()>`.</span></span> <span data-ttu-id="eb02c-118">메서드가 정의 된 모듈을 표시 하는 것은 선택적 이지만 각 확장 메서드가 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-118">Marking the module in which the method is defined is optional, but each extension method must be marked.</span></span> <span data-ttu-id="eb02c-119"><xref:System.Runtime.CompilerServices>확장 특성에 액세스 하기 위해 가져와야 합니다.</xref:System.Runtime.CompilerServices></span><span class="sxs-lookup"><span data-stu-id="eb02c-119"><xref:System.Runtime.CompilerServices> must be imported in order to access the extension attribute.</span></span>  
  
 <span data-ttu-id="eb02c-120">확장 메서드는 모듈 내 에서만 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-120">Extension methods can be declared only within modules.</span></span> <span data-ttu-id="eb02c-121">일반적으로 확장 메서드가 정의 된 모듈 호출 되는 것과 동일한 모듈이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-121">Typically, the module in which an extension method is defined is not the same module as the one in which it is called.</span></span> <span data-ttu-id="eb02c-122">대신, 확장 메서드를 포함 하는 모듈을 가져온 범위 가져오는 되어야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="eb02c-122">Instead, the module that contains the extension method is imported, if it needs to be, to bring it into scope.</span></span> <span data-ttu-id="eb02c-123">포함 된 모듈 후 `Print` 는 범위에는 메서드 마치 인수를 받지 않는 같은 일반 인스턴스 메서드인 것 처럼 `ToUpper`:</span><span class="sxs-lookup"><span data-stu-id="eb02c-123">After the module that contains `Print` is in scope, the method can be called as if it were an ordinary instance method that takes no arguments, such as `ToUpper`:</span></span>  
  
 <span data-ttu-id="eb02c-124">[!code-vb[VbVbalrExtensionMethods #&2;](./codesnippet/VisualBasic/extension-methods_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb02c-124">[!code-vb[VbVbalrExtensionMethods#2](./codesnippet/VisualBasic/extension-methods_2.vb)]</span></span>  
  
 <span data-ttu-id="eb02c-125">다음 예제에서는 `PrintAndPunctuate`에 대 한 확장 이기도 <xref:System.String>,이 이번에 두 개의 매개 변수를 사용 하 여 정의 합니다.</xref:System.String></span><span class="sxs-lookup"><span data-stu-id="eb02c-125">The next example, `PrintAndPunctuate`, is also an extension to <xref:System.String>, this time defined with two parameters.</span></span> <span data-ttu-id="eb02c-126">첫 번째 매개 변수 `aString`, 확장 메서드는 <xref:System.String>.</xref:System.String> 확장 설정</span><span class="sxs-lookup"><span data-stu-id="eb02c-126">The first parameter, `aString`, establishes that the extension method extends <xref:System.String>.</span></span> <span data-ttu-id="eb02c-127">두 번째 매개 변수 `punc`, 문장 부호는 메서드를 호출할 때 인수로 전달 되는 문자열 이어야 하기 위함입니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-127">The second parameter, `punc`, is intended to be a string of punctuation marks that is passed in as an argument when the method is called.</span></span> <span data-ttu-id="eb02c-128">메서드 뒤에 문장 부호는 문자열을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-128">The method displays the string followed by the punctuation marks.</span></span>  
  
 <span data-ttu-id="eb02c-129">[!code-vb[VbVbalrExtensionMethods #&3;](./codesnippet/VisualBasic/extension-methods_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb02c-129">[!code-vb[VbVbalrExtensionMethods#3](./codesnippet/VisualBasic/extension-methods_3.vb)]</span></span>  
  
 <span data-ttu-id="eb02c-130">메서드는 문자열 인수에 대 한 전송 하 여 `punc`:`example.PrintAndPunctuate(".")`</span><span class="sxs-lookup"><span data-stu-id="eb02c-130">The method is called by sending in a string argument for `punc`: `example.PrintAndPunctuate(".")`</span></span>  
  
 <span data-ttu-id="eb02c-131">다음 예제에서는 `Print` 및 `PrintAndPunctuate` 정의 및 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-131">The following example shows `Print` and `PrintAndPunctuate` defined and called.</span></span> <span data-ttu-id="eb02c-132"><xref:System.Runtime.CompilerServices>확장 특성에 액세스할 수 있도록 하기 위해 정의 모듈에서 가져오게 됩니다.</xref:System.Runtime.CompilerServices></span><span class="sxs-lookup"><span data-stu-id="eb02c-132"><xref:System.Runtime.CompilerServices> is imported in the definition module in order to enable access to the extension attribute.</span></span>  
  
### <a name="code"></a><span data-ttu-id="eb02c-133">코드</span><span class="sxs-lookup"><span data-stu-id="eb02c-133">Code</span></span>  
  
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
  
 <span data-ttu-id="eb02c-134">다음으로, 확장 메서드를 범위로 가져올 및 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-134">Next, the extension methods are brought into scope and called.</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="eb02c-135">설명</span><span class="sxs-lookup"><span data-stu-id="eb02c-135">Comments</span></span>  
 <span data-ttu-id="eb02c-136">실행할 수 있으려면 요구 또는 이와 유사한 확장 메서드 범위에서 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-136">All that is required to be able to run these or similar extension methods is that they be in scope.</span></span> <span data-ttu-id="eb02c-137">확장 메서드를 포함 하는 모듈 범위에 있으면 IntelliSense에 표시 되어 하 고 일반적인 인스턴스 메서드인 것 처럼 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-137">If the module that contains an extension method is in scope, it is visible in IntelliSense and can be called as if it were an ordinary instance method.</span></span>  
  
 <span data-ttu-id="eb02c-138">메서드를 호출할 때 인수가 전달 되지 첫 번째 매개 변수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-138">Notice that when the methods are invoked, no argument is sent in for the first parameter.</span></span> <span data-ttu-id="eb02c-139">매개 변수 `aString` 이전 메서드 정의에 바인딩된 `example`, 인스턴스의 `String` 호출 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-139">Parameter `aString` in the previous method definitions is bound to `example`, the instance of `String` that calls them.</span></span> <span data-ttu-id="eb02c-140">컴파일러는 사용 하 여 `example` 첫 번째 매개 변수로 전달 되는 인수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-140">The compiler will use `example` as the argument sent to the first parameter.</span></span>  
  
 <span data-ttu-id="eb02c-141">로 설정 된 개체에 대 한 확장 메서드를 호출 하는 경우 `Nothing`, 확장 메서드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-141">If an extension method is called for an object that is set to `Nothing`, the extension method executes.</span></span> <span data-ttu-id="eb02c-142">표준 인스턴스 메서드인에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-142">This does not apply to ordinary instance methods.</span></span> <span data-ttu-id="eb02c-143">명시적으로 확인할 수 있습니다 `Nothing` 확장 메서드에서.</span><span class="sxs-lookup"><span data-stu-id="eb02c-143">You can explicitly check for `Nothing` in the extension method.</span></span>  
  
## <a name="types-that-can-be-extended"></a><span data-ttu-id="eb02c-144">확장할 수 있는 형식</span><span class="sxs-lookup"><span data-stu-id="eb02c-144">Types That Can Be Extended</span></span>  
 <span data-ttu-id="eb02c-145">다음을 포함 하는 Visual Basic 매개 변수 목록에 표시할 수 있는 대부분의 형식에는 확장 메서드를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-145">You can define an extension method on most types that can be represented in a Visual Basic parameter list, including the following:</span></span>  
  
-   <span data-ttu-id="eb02c-146">클래스 (참조 형식)</span><span class="sxs-lookup"><span data-stu-id="eb02c-146">Classes (reference types)</span></span>  
  
-   <span data-ttu-id="eb02c-147">구조체 (값 형식)</span><span class="sxs-lookup"><span data-stu-id="eb02c-147">Structures (value types)</span></span>  
  
-   <span data-ttu-id="eb02c-148">인터페이스</span><span class="sxs-lookup"><span data-stu-id="eb02c-148">Interfaces</span></span>  
  
-   <span data-ttu-id="eb02c-149">대리자</span><span class="sxs-lookup"><span data-stu-id="eb02c-149">Delegates</span></span>  
  
-   <span data-ttu-id="eb02c-150">ByRef 및 ByVal 인수</span><span class="sxs-lookup"><span data-stu-id="eb02c-150">ByRef and ByVal arguments</span></span>  
  
-   <span data-ttu-id="eb02c-151">제네릭 메서드 매개 변수</span><span class="sxs-lookup"><span data-stu-id="eb02c-151">Generic method parameters</span></span>  
  
-   <span data-ttu-id="eb02c-152">배열</span><span class="sxs-lookup"><span data-stu-id="eb02c-152">Arrays</span></span>  
  
 <span data-ttu-id="eb02c-153">첫 번째 매개 변수는 확장 메서드를 확장 하는 데이터 형식으로 지정 하므로 필요 하며 선택적 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-153">Because the first parameter specifies the data type that the extension method extends, it is required and cannot be optional.</span></span> <span data-ttu-id="eb02c-154">이런 이유로 `Optional` 매개 변수 및 `ParamArray` 매개 변수는 매개 변수 목록에서 첫 번째 매개 변수 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-154">For that reason, `Optional` parameters and `ParamArray` parameters cannot be the first parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="eb02c-155">런타임에 바인딩에서는 확장 메서드를 사용 하는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-155">Extension methods are not considered in late binding.</span></span> <span data-ttu-id="eb02c-156">다음 예에서 문은 `anObject.PrintMe()` 를 발생 시킵니다는 <xref:System.MissingMemberException>예외, 동일한 예외 경우 두 번째 `PrintMe` 확장 메서드 정의 삭제 되었습니다.</xref:System.MissingMemberException></span><span class="sxs-lookup"><span data-stu-id="eb02c-156">In the following example, the statement `anObject.PrintMe()` raises a <xref:System.MissingMemberException> exception, the same exception you would see if the second `PrintMe` extension method definition were deleted.</span></span>  
  
 <span data-ttu-id="eb02c-157">[!code-vb[VbVbalrExtensionMethods #&9;](./codesnippet/VisualBasic/extension-methods_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb02c-157">[!code-vb[VbVbalrExtensionMethods#9](./codesnippet/VisualBasic/extension-methods_4.vb)]</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="eb02c-158">모범 사례</span><span class="sxs-lookup"><span data-stu-id="eb02c-158">Best Practices</span></span>  
 <span data-ttu-id="eb02c-159">확장 메서드는 기존 형식을 확장 하는 편리 하 고 강력한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-159">Extension methods provide a convenient and powerful way to extend an existing type.</span></span> <span data-ttu-id="eb02c-160">그러나이 성공적으로 사용 하려면 있습니다 몇 가지 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-160">However, to use them successfully, there are some points to consider.</span></span> <span data-ttu-id="eb02c-161">이러한 고려 사항은 주로 클래스 라이브러리 작성에 적용 되지만 확장 메서드를 사용 하는 모든 응용 프로그램에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-161">These considerations apply mainly to authors of class libraries, but they might affect any application that uses extension methods.</span></span>  
  
 <span data-ttu-id="eb02c-162">가장 일반적으로 소유 하지 않은 형식에 추가 하는 확장 메서드는 사용자가 제어 하는 형식에 추가 하는 확장 메서드보다 더 취약 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-162">Most generally, extension methods that you add to types that you do not own are more vulnerable than extension methods added to types that you control.</span></span> <span data-ttu-id="eb02c-163">여러 가지 확장 메서드를 방해할 수 있는 소유 하지 않은 클래스에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-163">A number of things can occur in classes you do not own that can interfere with your extension methods.</span></span>  
  
-   <span data-ttu-id="eb02c-164">액세스할 수 있는 인스턴스 멤버와 매개 변수에 필요한 인수에서 축소 변환을 문 호출의 인수와 호환 되는 시그니처가 있는 있으면 모든 확장 메서드 대신 인스턴스 메서드가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-164">If any accessible instance member exists that has a signature that is compatible with the arguments in the calling statement, with no narrowing conversions required from argument to parameter, the instance method will be used in preference to any extension method.</span></span> <span data-ttu-id="eb02c-165">따라서 적절 한 인스턴스 메서드는 언젠가 클래스에 추가 되 면에 의존 하는 기존 확장 멤버 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-165">Therefore, if an appropriate instance method is added to a class at some point, an existing extension member that you rely on may become inaccessible.</span></span>  
  
-   <span data-ttu-id="eb02c-166">확장 메서드의 작성자는 원래 확장 우선 순위를 있을 수 있는 충돌 하는 확장 메서드 작성에서 다른 프로그래머가 방지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-166">The author of an extension method cannot prevent other programmers from writing conflicting extension methods that may have precedence over the original extension.</span></span>  
  
-   <span data-ttu-id="eb02c-167">네임 스페이스에 확장 메서드를 삽입 하 여 견고성을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-167">You can improve robustness by putting extension methods in their own namespace.</span></span> <span data-ttu-id="eb02c-168">라이브러리 소비자가 다음 네임 스페이스를 포함 또는 제외, 되거나 라이브러리의 나머지 부분에서 별도로 네임 스페이스 중에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-168">Consumers of your library can then include a namespace or exclude it, or select among namespaces, separately from the rest of the library.</span></span>  
  
-   <span data-ttu-id="eb02c-169">인터페이스를 확장 인터페이스 또는 클래스를 소유 하지 않은 경우에 특히 클래스를 확장 하는 것 보다 더 안전할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-169">It may be safer to extend interfaces than it is to extend classes, especially if you do not own the interface or class.</span></span> <span data-ttu-id="eb02c-170">인터페이스의 변경을 구현 하는 모든 클래스를 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-170">A change in an interface affects every class that implements it.</span></span> <span data-ttu-id="eb02c-171">따라서 작성자는 추가 하거나 인터페이스에서 메서드를 변경 하려면 가능성이 줄어들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-171">Therefore, the author may be less likely to add or change methods in an interface.</span></span> <span data-ttu-id="eb02c-172">그러나 클래스는 서명이 같은 확장 메서드가 있는 두 가지 인터페이스를 구현 하는 경우 확장 메서드 모두 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-172">However, if a class implements two interfaces that have extension methods with the same signature, neither extension method is visible.</span></span>  
  
-   <span data-ttu-id="eb02c-173">할 수 있습니다 가장 구체적인 형식을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-173">Extend the most specific type you can.</span></span> <span data-ttu-id="eb02c-174">형식 계층 구조, 여러 가지 다른 형식을 파생 되는 형식을 선택 하면는 인스턴스 메서드 또는 사용자 방해할 수 있는 다른 확장 메서드가 도입 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-174">In a hierarchy of types, if you select a type from which many other types are derived, there are layers of possibilities for the introduction of instance methods or other extension methods that might interfere with yours.</span></span>  
  
## <a name="extension-methods-instance-methods-and-properties"></a><span data-ttu-id="eb02c-175">확장 메서드, 인스턴스 메서드 및 속성</span><span class="sxs-lookup"><span data-stu-id="eb02c-175">Extension Methods, Instance Methods, and Properties</span></span>  
 <span data-ttu-id="eb02c-176">범위 내의 인스턴스 메서드인에 문 호출의 인수와 호환 되는 서명이 있는 경우 모든 확장 메서드 대신 인스턴스 메서드를 사용 하 여 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-176">When an in-scope instance method has a signature that is compatible with the arguments of a calling statement, the instance method is chosen in preference to any extension method.</span></span> <span data-ttu-id="eb02c-177">인스턴스 메서드가 확장 메서드는 더 잘 일치 하는 경우에 우선을 순위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-177">The instance method has precedence even if the extension method is a better match.</span></span> <span data-ttu-id="eb02c-178">다음 예에서 `ExampleClass` 라는 인스턴스 메서드를 포함 `ExampleMethod` 매개 변수가 하나 형식의 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-178">In the following example, `ExampleClass` contains an instance method named `ExampleMethod` that has one parameter of type `Integer`.</span></span> <span data-ttu-id="eb02c-179">확장 메서드 `ExampleMethod` 확장 `ExampleClass`, 형식의 매개 변수가 하나 있고 `Long`합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-179">Extension method `ExampleMethod` extends `ExampleClass`, and has one parameter of type `Long`.</span></span>  
  
 <span data-ttu-id="eb02c-180">[!code-vb[VbVbalrExtensionMethods #&4;](./codesnippet/VisualBasic/extension-methods_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb02c-180">[!code-vb[VbVbalrExtensionMethods#4](./codesnippet/VisualBasic/extension-methods_5.vb)]</span></span>  
  
 <span data-ttu-id="eb02c-181">첫 번째 호출 `ExampleMethod` 때문에 다음 코드에는 확장 메서드를 호출 `arg1` 는 `Long` 과 호환 되며는 `Long` 확장 메서드의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-181">The first call to `ExampleMethod` in the following code calls the extension method, because `arg1` is `Long` and is compatible only with the `Long` parameter in the extension method.</span></span> <span data-ttu-id="eb02c-182">두 번째 호출은 `ExampleMethod` 에 `Integer` 인수 `arg2`, 인스턴스 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-182">The second call to `ExampleMethod` has an `Integer` argument, `arg2`, and it calls the instance method.</span></span>  
  
 <span data-ttu-id="eb02c-183">[!code-vb[VbVbalrExtensionMethods #&5;](./codesnippet/VisualBasic/extension-methods_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb02c-183">[!code-vb[VbVbalrExtensionMethods#5](./codesnippet/VisualBasic/extension-methods_6.vb)]</span></span>  
  
 <span data-ttu-id="eb02c-184">이제 역방향 두 메서드에 있는 매개 변수의 데이터 형식:</span><span class="sxs-lookup"><span data-stu-id="eb02c-184">Now reverse the data types of the parameters in the two methods:</span></span>  
  
 <span data-ttu-id="eb02c-185">[!code-vb[VbVbalrExtensionMethods #&6;](./codesnippet/VisualBasic/extension-methods_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb02c-185">[!code-vb[VbVbalrExtensionMethods#6](./codesnippet/VisualBasic/extension-methods_7.vb)]</span></span>  
  
 <span data-ttu-id="eb02c-186">이번에 코드에서 `Main` 인스턴스 메서드를 두 번 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-186">This time the code in `Main` calls the instance method both times.</span></span> <span data-ttu-id="eb02c-187">즉, 둘 다 `arg1` 및 `arg2` 확대 변환에 `Long`, 인스턴스 메서드가 확장 메서드 두 경우 모두 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-187">This is because both `arg1` and `arg2` have a widening conversion to `Long`, and the instance method takes precedence over the extension method in both cases.</span></span>  
  
 <span data-ttu-id="eb02c-188">[!code-vb[VbVbalrExtensionMethods #&7;](./codesnippet/VisualBasic/extension-methods_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb02c-188">[!code-vb[VbVbalrExtensionMethods#7](./codesnippet/VisualBasic/extension-methods_8.vb)]</span></span>  
  
 <span data-ttu-id="eb02c-189">따라서 확장 메서드는 기존 인스턴스 메서드를 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-189">Therefore, an extension method cannot replace an existing instance method.</span></span> <span data-ttu-id="eb02c-190">그러나 확장 메서드 이름이 같은 인스턴스 메서드로 하지만 서명을 충돌 하지 않는 경우 두 가지 방법은 모두 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-190">However, when an extension method has the same name as an instance method but the signatures do not conflict, both methods can be accessed.</span></span> <span data-ttu-id="eb02c-191">예를 들어 하는 경우 클래스 `ExampleClass` 라는 메서드가 있는 `ExampleMethod` 인수 없음, 이름이 같은 확장 메서드를 사용 하지만 다음 코드와 같이 다른 서명을 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-191">For example, if class `ExampleClass` contains a method named `ExampleMethod` that takes no arguments, extension methods with the same name but different signatures are permitted, as shown in the following code.</span></span>  
  
 <span data-ttu-id="eb02c-192">[!code-vb[VbVbalrExtensionMethods #&8;](./codesnippet/VisualBasic/extension-methods_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb02c-192">[!code-vb[VbVbalrExtensionMethods#8](./codesnippet/VisualBasic/extension-methods_9.vb)]</span></span>  
  
 <span data-ttu-id="eb02c-193">이 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-193">The output from this code is as follows:</span></span>  
  
 `Extension method`  
  
 `Instance method`  
  
 <span data-ttu-id="eb02c-194">상황은 속성으로 간단: 확장 클래스의 속성으로는 확장 메서드를 사용 하는 같은 이름의 경우 확장 메서드 표시 되지 않으며 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-194">The situation is simpler with properties: if an extension method has the same name as a property of the class it extends, the extension method is not visible and cannot be accessed.</span></span>  
  
## <a name="extension-method-precedence"></a><span data-ttu-id="eb02c-195">확장 메서드 우선 순위</span><span class="sxs-lookup"><span data-stu-id="eb02c-195">Extension Method Precedence</span></span>  
 <span data-ttu-id="eb02c-196">시그니처가 같은 두 가지 확장 메서드 범위에서 하 고 액세스할 수 있는 경우 우선 순위가 높은 것이 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-196">When two extension methods that have identical signatures are in scope and accessible, the one with higher precedence will be invoked.</span></span> <span data-ttu-id="eb02c-197">확장 메서드의 우선 순위는 메서드를 범위로 가져올 하는 데 사용 하는 메커니즘을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-197">An extension method's precedence is based on the mechanism used to bring the method into scope.</span></span> <span data-ttu-id="eb02c-198">다음 목록에서는 우선 순위 계층에서 순위가 높은 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-198">The following list shows the precedence hierarchy, from highest to lowest.</span></span>  
  
1.  <span data-ttu-id="eb02c-199">현재 모듈 내에 정의 된 메서드를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-199">Extension methods defined inside the current module.</span></span>  
  
2.  <span data-ttu-id="eb02c-200">확장 메서드 정의 된 데이터 내부의 형식은 현재 네임 스페이스 또는 부모 중 하나에 자식 네임 스페이스가 부모 네임 스페이스 보다 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-200">Extension methods defined inside data types in the current namespace or any one of its parents, with child namespaces having higher precedence than parent namespaces.</span></span>  
  
3.  <span data-ttu-id="eb02c-201">확장 메서드는 현재 파일의 형식 가져오기 안에 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-201">Extension methods defined inside any type imports in the current file.</span></span>  
  
4.  <span data-ttu-id="eb02c-202">확장 메서드는 현재 파일의 네임 스페이스 가져오기 내에서 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-202">Extension methods defined inside any namespace imports in the current file.</span></span>  
  
5.  <span data-ttu-id="eb02c-203">프로젝트 수준의 형식 가져오기 안에 정의 된 확장 메서드.</span><span class="sxs-lookup"><span data-stu-id="eb02c-203">Extension methods defined inside any project-level type imports.</span></span>  
  
6.  <span data-ttu-id="eb02c-204">프로젝트 수준의 네임 스페이스 가져오기 안에 정의 된 확장 메서드.</span><span class="sxs-lookup"><span data-stu-id="eb02c-204">Extension methods defined inside any project-level namespace imports.</span></span>  
  
 <span data-ttu-id="eb02c-205">우선 순위는 모호성을 해결 되지 않으면, 호출 하는 방법을 지정 하는 정규화 된 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-205">If precedence does not resolve the ambiguity, you can use the fully qualified name to specify the method that you are calling.</span></span> <span data-ttu-id="eb02c-206">하는 경우는 `Print` 앞의 예제에는 메서드가 라는 모듈에 정의 되어 `StringExtensions`, 정규화 된 이름이 `StringExtensions.Print(example)` 대신 `example.Print()`합니다.</span><span class="sxs-lookup"><span data-stu-id="eb02c-206">If the `Print` method in the earlier example is defined in a module named `StringExtensions`, the fully qualified name is `StringExtensions.Print(example)` instead of `example.Print()`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb02c-207">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb02c-207">See Also</span></span>  
 <span data-ttu-id="eb02c-208"><xref:System.Runtime.CompilerServices></xref:System.Runtime.CompilerServices></span><span class="sxs-lookup"><span data-stu-id="eb02c-208"><xref:System.Runtime.CompilerServices></span></span>   
 <span data-ttu-id="eb02c-209"><xref:System.Runtime.CompilerServices.ExtensionAttribute></xref:System.Runtime.CompilerServices.ExtensionAttribute></span><span class="sxs-lookup"><span data-stu-id="eb02c-209"><xref:System.Runtime.CompilerServices.ExtensionAttribute></span></span>   
<span data-ttu-id="eb02c-210"> [확장 메서드](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md) </span><span class="sxs-lookup"><span data-stu-id="eb02c-210"> [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md) </span></span>  
<span data-ttu-id="eb02c-211"> [Module 문](../../../../visual-basic/language-reference/statements/module-statement.md) </span><span class="sxs-lookup"><span data-stu-id="eb02c-211"> [Module Statement](../../../../visual-basic/language-reference/statements/module-statement.md) </span></span>  
<span data-ttu-id="eb02c-212"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="eb02c-212"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="eb02c-213"> [선택적 매개 변수](./optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="eb02c-213"> [Optional Parameters](./optional-parameters.md) </span></span>  
<span data-ttu-id="eb02c-214"> [매개 변수 배열](./parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="eb02c-214"> [Parameter Arrays](./parameter-arrays.md) </span></span>  
<span data-ttu-id="eb02c-215"> [특성 개요](../../../../visual-basic/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="eb02c-215"> [Attributes overview](../../../../visual-basic/programming-guide/concepts/attributes/index.md) </span></span>  
<span data-ttu-id="eb02c-216"> [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)</span><span class="sxs-lookup"><span data-stu-id="eb02c-216"> [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)</span></span>
