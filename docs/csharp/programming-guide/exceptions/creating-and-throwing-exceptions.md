---
title: "예외 만들기 및 Throw(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- catching exceptions [C#]
- throwing exceptions [C#]
- exceptions [C#], creating
- exceptions [C#], throwing
ms.assetid: 6bbba495-a115-4c6d-90cc-1f4d7b5f39e2
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5f49b0911aa94480988987f209bc73d187451620
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="creating-and-throwing-exceptions-c-programming-guide"></a><span data-ttu-id="3fb34-102">예외 만들기 및 Throw(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="3fb34-102">Creating and Throwing Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="3fb34-103">예외는 프로그램을 실행하는 동안 오류가 발생했음을 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-103">Exceptions are used to indicate that an error has occurred while running the program.</span></span> <span data-ttu-id="3fb34-104">오류를 설명하는 예외 개체가 만들어지고 [throw](../../../csharp/language-reference/keywords/throw.md) 키워드를 통해 *throw*됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-104">Exception objects that describe an error are created and then *thrown* with the [throw](../../../csharp/language-reference/keywords/throw.md) keyword.</span></span> <span data-ttu-id="3fb34-105">그런 다음 런타임에 가장 호환성이 높은 예외 처리기를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-105">The runtime then searches for the most compatible exception handler.</span></span>  
  
 <span data-ttu-id="3fb34-106">프로그래머는 다음 조건 중 하나 이상에 해당할 경우 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-106">Programmers should throw exceptions when one or more of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="3fb34-107">메서드가 정의된 기능을 완료할 수 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="3fb34-107">The method cannot complete its defined functionality.</span></span>  
  
     <span data-ttu-id="3fb34-108">예를 들어 메서드에 대한 매개 변수에 잘못된 값이 포함된 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-108">For example, if a parameter to a method has an invalid value:</span></span>  
  
     <span data-ttu-id="3fb34-109">[!code-cs[csProgGuideExceptions#12](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3fb34-109">[!code-cs[csProgGuideExceptions#12](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_1.cs)]</span></span>  
  
-   <span data-ttu-id="3fb34-110">개체 상태에 따라 개체에 대한 부적절한 호출이 이루어진 경우.</span><span class="sxs-lookup"><span data-stu-id="3fb34-110">An inappropriate call to an object is made, based on the object state.</span></span>  
  
     <span data-ttu-id="3fb34-111">한 가지 예는 읽기 전용 파일에 쓰려고 시도하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-111">One example might be trying to write to a read-only file.</span></span> <span data-ttu-id="3fb34-112">개체 상태가 작업을 허용하지 않을 경우 이 클래스의 파생에 따라 <xref:System.InvalidOperationException>의 인스턴스 또는 개체를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-112">In cases where an object state does not allow an operation, throw an instance of <xref:System.InvalidOperationException> or an object based on a derivation of this class.</span></span> <span data-ttu-id="3fb34-113">다음은 <xref:System.InvalidOperationException> 개체를 throw하는 메서드의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-113">This is an example of a method that throws an <xref:System.InvalidOperationException> object:</span></span>  
  
     <span data-ttu-id="3fb34-114">[!code-cs[csProgGuideExceptions#13](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3fb34-114">[!code-cs[csProgGuideExceptions#13](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_2.cs)]</span></span>  
  
-   <span data-ttu-id="3fb34-115">메서드에 대한 인수가 예외를 일으키는 경우.</span><span class="sxs-lookup"><span data-stu-id="3fb34-115">When an argument to a method causes an exception.</span></span>  
  
     <span data-ttu-id="3fb34-116">이 경우 원래 예외가 catch되고 <xref:System.ArgumentException> 인스턴스가 만들어져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-116">In this case, the original exception should be caught and an <xref:System.ArgumentException> instance should be created.</span></span> <span data-ttu-id="3fb34-117">원래 예외를 <xref:System.ArgumentException>의 생성자에 <xref:System.Exception.InnerException%2A> 매개 변수로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-117">The original exception should be passed to the constructor of the <xref:System.ArgumentException> as the <xref:System.Exception.InnerException%2A> parameter:</span></span>  
  
     <span data-ttu-id="3fb34-118">[!code-cs[csProgGuideExceptions#14](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="3fb34-118">[!code-cs[csProgGuideExceptions#14](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_3.cs)]</span></span>  
  
 <span data-ttu-id="3fb34-119">예외에 이름이 <xref:System.Exception.StackTrace%2A>인 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-119">Exceptions contain a property named <xref:System.Exception.StackTrace%2A>.</span></span> <span data-ttu-id="3fb34-120">이 문자열에는 현재 콜 스택에 대한 메서드의 이름과 각 메서드에 대해 예외가 throw된 파일 이름 및 줄 번호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-120">This string contains the name of the methods on the current call stack, together with the file name and line number where the exception was thrown for each method.</span></span> <span data-ttu-id="3fb34-121"><xref:System.Exception.StackTrace%2A> 개체는 `throw` 문의 지점에서 CLR(공용 언어 런타임)에 의해 자동으로 만들어지므로 해당 예외는 스택 추적이 시작되는 지점에서 throw되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-121">A <xref:System.Exception.StackTrace%2A> object is created automatically by the common language runtime (CLR) from the point of the `throw` statement, so that exceptions must be thrown from the point where the stack trace should begin.</span></span>  
  
 <span data-ttu-id="3fb34-122">모든 예외에 이름이 <xref:System.Exception.Message%2A>인 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-122">All exceptions contain a property named <xref:System.Exception.Message%2A>.</span></span> <span data-ttu-id="3fb34-123">예외의 이유를 설명하려면 이 문자열을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-123">This string should be set to explain the reason for the exception.</span></span> <span data-ttu-id="3fb34-124">보안이 중요한 정보는 메시지 텍스트에 넣으면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-124">Note that information that is sensitive to security should not be put in the message text.</span></span> <span data-ttu-id="3fb34-125"><xref:System.Exception.Message%2A> 외에 <xref:System.ArgumentException>에는 예외를 throw한 인수의 이름으로 설정해야 하는 <xref:System.ArgumentException.ParamName%2A> 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-125">In addition to <xref:System.Exception.Message%2A>, <xref:System.ArgumentException> contains a property named <xref:System.ArgumentException.ParamName%2A> that should be set to the name of the argument that caused the exception to be thrown.</span></span> <span data-ttu-id="3fb34-126">속성 setter의 경우 <xref:System.ArgumentException.ParamName%2A>을 `value`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-126">In the case of a property setter, <xref:System.ArgumentException.ParamName%2A> should be set to `value`.</span></span>  
  
 <span data-ttu-id="3fb34-127">Public 및 protected 메서드 멤버는 의도한 함수를 완료할 수 없을 때마다 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-127">Public and protected methods members should throw exceptions whenever they cannot complete their intended functions.</span></span> <span data-ttu-id="3fb34-128">throw된 예외 클래스는 오류 조건에 맞을 수 있는 가장 구체적인 예외여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-128">The exception class that is thrown should be the most specific exception available that fits the error conditions.</span></span> <span data-ttu-id="3fb34-129">이러한 예외는 클래스 기능의 일부로 문서화해야 하고 파생 클래스 또는 원래 클래스의 업데이트는 이전 버전과의 호환성을 위해 같은 동작을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-129">These exceptions should be documented as part of the class functionality, and derived classes or updates to the original class should retain the same behavior for backward compatibility.</span></span>  
  
## <a name="things-to-avoid-when-throwing-exceptions"></a><span data-ttu-id="3fb34-130">예외를 throw할 때 피해야 하는 작업</span><span class="sxs-lookup"><span data-stu-id="3fb34-130">Things to Avoid When Throwing Exceptions</span></span>  
 <span data-ttu-id="3fb34-131">다음 목록은 예외를 throw할 때 피해야 할 사례를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-131">The following list identifies practices to avoid when throwing exceptions:</span></span>  
  
-   <span data-ttu-id="3fb34-132">프로그램 흐름을 일반 예외의 일부로 변경하는 데는 예외를 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-132">Exceptions should not be used to change the flow of a program as part of ordinary execution.</span></span> <span data-ttu-id="3fb34-133">오류 조건을 보고하고 처리하는 데만 예외를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-133">Exceptions should only be used to report and handle error conditions.</span></span>  
  
-   <span data-ttu-id="3fb34-134">예외는 throw하는 대신 반환 값 또는 매개 변수로 반환하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-134">Exceptions should not be returned as a return value or parameter instead of being thrown.</span></span>  
  
-   <span data-ttu-id="3fb34-135">고유한 소스 코드에서 의도적으로 <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, <xref:System.NullReferenceException?displayProperty=fullName> 또는 <xref:System.IndexOutOfRangeException?displayProperty=fullName>을 throw하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3fb34-135">Do not throw <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, <xref:System.NullReferenceException?displayProperty=fullName>, or <xref:System.IndexOutOfRangeException?displayProperty=fullName> intentionally from your own source code.</span></span>  
  
-   <span data-ttu-id="3fb34-136">릴리스 모드가 아닌 디버그 모드에서 throw될 수 있는 예외를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3fb34-136">Do not create exceptions that can be thrown in debug mode but not release mode.</span></span> <span data-ttu-id="3fb34-137">개발 단계에서 런타임 오류를 식별하려면 대신 디버그 어설션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="3fb34-137">To identify run-time errors during the development phase, use Debug Assert instead.</span></span>  
  
## <a name="defining-exception-classes"></a><span data-ttu-id="3fb34-138">예외 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="3fb34-138">Defining Exception Classes</span></span>  
 <span data-ttu-id="3fb34-139">프로그램에서는 <xref:System> 네임스페이스의 미리 정의된 예외 클래스를 throw하거나(이전에 언급한 위치 제외) <xref:System.Exception>에서 파생시켜 자체 예외 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-139">Programs can throw a predefined exception class in the <xref:System> namespace (except where previously noted), or create their own exception classes by deriving from <xref:System.Exception>.</span></span> <span data-ttu-id="3fb34-140">파생 클래스는 기본 생성자, 메시지 속성을 설정하는 생성자, <xref:System.Exception.Message%2A> 및 <xref:System.Exception.InnerException%2A> 속성을 설정하는 생성자 두 개를 포함하여 네 개 이상의 생성자를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-140">The derived classes should define at least four constructors: one default constructor, one that sets the message property, and one that sets both the <xref:System.Exception.Message%2A> and <xref:System.Exception.InnerException%2A> properties.</span></span> <span data-ttu-id="3fb34-141">네 번째 생성자는 예외를 serialize하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-141">The fourth constructor is used to serialize the exception.</span></span> <span data-ttu-id="3fb34-142">새 예외 클래스는 serialize할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-142">New exception classes should be serializable.</span></span> <span data-ttu-id="3fb34-143">예:</span><span class="sxs-lookup"><span data-stu-id="3fb34-143">For example:</span></span>  
  
 <span data-ttu-id="3fb34-144">[!code-cs[csProgGuideExceptions#15](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="3fb34-144">[!code-cs[csProgGuideExceptions#15](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_4.cs)]</span></span>  
  
 <span data-ttu-id="3fb34-145">새로운 속성이 제공하는 데이터가 예외 확인에 유용할 경우에만 해당 속성을 예외 클래스에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-145">New properties should only be added to the exception class when the data they provide is useful to resolving the exception.</span></span> <span data-ttu-id="3fb34-146">새 속성이 파생 예외 클래스에 추가되면 추가된 정보를 반환하기 위해 `ToString()`을 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb34-146">If new properties are added to the derived exception class, `ToString()` should be overridden to return the added information.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3fb34-147">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="3fb34-147">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3fb34-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3fb34-148">See Also</span></span>  
 <span data-ttu-id="3fb34-149">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3fb34-149">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3fb34-150">[예외 및 예외 처리](../../../csharp/programming-guide/exceptions/index.md) </span><span class="sxs-lookup"><span data-stu-id="3fb34-150">[Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md) </span></span>  
 <span data-ttu-id="3fb34-151">[예외 계층 구조](http://msdn.microsoft.com/library/f7d68675-be06-40fb-a555-05f0c5a6f66b) </span><span class="sxs-lookup"><span data-stu-id="3fb34-151">[Exception Hierarchy](http://msdn.microsoft.com/library/f7d68675-be06-40fb-a555-05f0c5a6f66b) </span></span>  
 [<span data-ttu-id="3fb34-152">예외 처리</span><span class="sxs-lookup"><span data-stu-id="3fb34-152">Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/exception-handling.md)

