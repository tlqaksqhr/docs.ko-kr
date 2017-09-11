---
title: "dynamic 형식 사용(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- dynamic [C#], about dynamic type
- dynamic type [C#]
ms.assetid: 3828989d-c967-4a51-b948-857ebc8fdf26
caps.latest.revision: 30
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
ms.openlocfilehash: 36e10ef6a63aae2e901be50b9286370caec50e6a
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="using-type-dynamic-c-programming-guide"></a><span data-ttu-id="b311e-102">dynamic 형식 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b311e-102">Using Type dynamic (C# Programming Guide)</span></span>
[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)]<span data-ttu-id="b311e-103">에서는 새로운 형식 `dynamic`을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-103"> introduces a new type, `dynamic`.</span></span> <span data-ttu-id="b311e-104">이 형식은 정적 형식이지만 `dynamic` 형식의 개체가 정적 형식 검사를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-104">The type is a static type, but an object of type `dynamic` bypasses static type checking.</span></span> <span data-ttu-id="b311e-105">대부분의 경우 이 형식은 `object` 형식을 가지고 있는 것처럼 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-105">In most cases, it functions like it has type `object`.</span></span> <span data-ttu-id="b311e-106">컴파일 시간에 `dynamic` 형식의 요소는 모든 연산을 지원하는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-106">At compile time, an element that is typed as `dynamic` is assumed to support any operation.</span></span> <span data-ttu-id="b311e-107">따라서 개체가 값을 COM API, IronPython 같은 동적 언어, HTML DOM(문서 개체 모델), 리플렉션 또는 프로그램의 다른 곳 등 어디서 가져오든 신경을 쓸 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-107">Therefore, you do not have to be concerned about whether the object gets its value from a COM API, from a dynamic language such as IronPython, from the HTML Document Object Model (DOM), from reflection, or from somewhere else in the program.</span></span> <span data-ttu-id="b311e-108">그러나 코드가 유효하지 않으면 런타임 시 오류가 catch됩니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-108">However, if the code is not valid, errors are caught at run time.</span></span>  
  
 <span data-ttu-id="b311e-109">예를 들어 다음 코드의 인스턴스 메서드 `exampleMethod1`에 매개 변수가 하나뿐인 경우, 컴파일러는 메서드 `ec.exampleMethod1(10, 4)`에 대한 첫 번째 호출이 유효하지 않음을 인식합니다. 여기에 인수가 두 개 포함되었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-109">For example, if instance method `exampleMethod1` in the following code has only one parameter, the compiler recognizes that the first call to the method, `ec.exampleMethod1(10, 4)`, is not valid because it contains two arguments.</span></span> <span data-ttu-id="b311e-110">호출 시 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-110">The call causes a compiler error.</span></span> <span data-ttu-id="b311e-111">컴파일러는 메서드 `dynamic_ec.exampleMethod1(10, 4)`에 대한 두 번째 호출을 확인하지 않습니다. `dynamic_ec`의 형식이 `dynamic`이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-111">The second call to the method, `dynamic_ec.exampleMethod1(10, 4)`, is not checked by the compiler because the type of `dynamic_ec` is `dynamic`.</span></span> <span data-ttu-id="b311e-112">따라서 컴파일러 오류가 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-112">Therefore, no compiler error is reported.</span></span> <span data-ttu-id="b311e-113">그러나 이 오류는 알림을 무기한 이스케이프하지 않고,</span><span class="sxs-lookup"><span data-stu-id="b311e-113">However, the error does not escape notice indefinitely.</span></span> <span data-ttu-id="b311e-114">런타임에 catch되며 런타임 예외를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-114">It is caught at run time and causes a run-time exception.</span></span>  
  
 <span data-ttu-id="b311e-115">[!code-cs[CsProgGuideTypes#50](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b311e-115">[!code-cs[CsProgGuideTypes#50](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_1.cs)]</span></span>  
  
 <span data-ttu-id="b311e-116">[!code-cs[CsProgGuideTypes#56](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b311e-116">[!code-cs[CsProgGuideTypes#56](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_2.cs)]</span></span>  
  
 <span data-ttu-id="b311e-117">이 예제에서 컴파일러의 역할은 `dynamic`으로 형식이 지정된 개체 또는 식에 대해 각 문이 해야 할 일에 대한 정보를 패키지하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-117">The role of the compiler in these examples is to package together information about what each statement is proposing to do to the object or expression that is typed as `dynamic`.</span></span> <span data-ttu-id="b311e-118">런타임에는 저장된 정보의 검사가 수행되며, 유효하지 않은 문에서 런타임 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-118">At run time, the stored information is examined, and any statement that is not valid causes a run-time exception.</span></span>  
  
 <span data-ttu-id="b311e-119">대부분의 동적 작업은 결과 그 자체가 `dynamic`입니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-119">The result of most dynamic operations is itself `dynamic`.</span></span> <span data-ttu-id="b311e-120">다음 예제에서 `testSum`이 사용된 곳에 마우스 포인터를 올려두면 IntelliSense에서 **(지역 변수) dynamic testSum** 형식을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-120">For example, if you rest the mouse pointer over the use of `testSum` in the following example, IntelliSense displays the type **(local variable) dynamic testSum**.</span></span>  
  
 <span data-ttu-id="b311e-121">[!code-cs[CsProgGuideTypes#51](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="b311e-121">[!code-cs[CsProgGuideTypes#51](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_3.cs)]</span></span>  
  
 <span data-ttu-id="b311e-122">결과가 `dynamic`이 아닌 작업은 `dynamic`에서 다른 형식으로의 변환, 그리고 `dynamic` 형식의 인수를 포함하는 생성자 호출을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-122">Operations in which the result is not `dynamic` include conversions from `dynamic` to another type, and constructor calls that include arguments of type `dynamic`.</span></span> <span data-ttu-id="b311e-123">예를 들어 다음 선언에서 `testInstance`의 형식은 `dynamic`이 아니라 `ExampleClass`입니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-123">For example, the type of `testInstance` in the following declaration is `ExampleClass`, not `dynamic`.</span></span>  
  
 <span data-ttu-id="b311e-124">[!code-cs[CsProgGuideTypes#52](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="b311e-124">[!code-cs[CsProgGuideTypes#52](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_4.cs)]</span></span>  
  
 <span data-ttu-id="b311e-125">변환 예제는 다음 섹션인 "변환"에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-125">Conversion examples are shown in the following section, "Conversions."</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="b311e-126">변환</span><span class="sxs-lookup"><span data-stu-id="b311e-126">Conversions</span></span>  
 <span data-ttu-id="b311e-127">동적 개체와 다른 형식 간에 손쉽게 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-127">Conversions between dynamic objects and other types are easy.</span></span> <span data-ttu-id="b311e-128">따라서 개발자는 동적 동작과 비동적 동작 간에 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-128">This enables the developer to switch between dynamic and non-dynamic behavior.</span></span>  
  
 <span data-ttu-id="b311e-129">다음 예제와 같이 개체를 동적 형식으로 암시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-129">Any object can be converted to dynamic type implicitly, as shown in the following examples.</span></span>  
  
 <span data-ttu-id="b311e-130">[!code-cs[CsProgGuideTypes#53](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="b311e-130">[!code-cs[CsProgGuideTypes#53](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_5.cs)]</span></span>  
  
 <span data-ttu-id="b311e-131">반대로, 암시적 변환을 `dynamic` 형식의 식에 동적으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-131">Conversely, an implicit conversion can be dynamically applied to any expression of type `dynamic`.</span></span>  
  
 <span data-ttu-id="b311e-132">[!code-cs[CsProgGuideTypes#54](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="b311e-132">[!code-cs[CsProgGuideTypes#54](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_6.cs)]</span></span>  
  
## <a name="overload-resolution-with-arguments-of-type-dynamic"></a><span data-ttu-id="b311e-133">동적 형식의 인수로 오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="b311e-133">Overload Resolution with Arguments of Type dynamic</span></span>  
 <span data-ttu-id="b311e-134">메서드 호출 내 하나 이상의 인수에 `dynamic` 형식이 있거나 메서드 호출의 수신자가 `dynamic` 형식인 경우 오버로드 확인은 컴파일 시간이 아니라 런타임에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-134">Overload resolution occurs at run time instead of at compile time if one or more of the arguments in a method call have the type `dynamic`, or if the receiver of the method call is of type `dynamic`.</span></span> <span data-ttu-id="b311e-135">다음 예제에서 액세스 가능한 유일한 `exampleMethod2` 메서드가 문자열 인수를 사용하도록 정의되는 경우, `d1`을 인수로서 전송하면 컴파일러 오류는 발생하지 않지만 런타임 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-135">In the following example, if the only accessible `exampleMethod2` method is defined to take a string argument, sending `d1` as the argument does not cause a compiler error, but it does cause a run-time exception.</span></span> <span data-ttu-id="b311e-136">`d1`의 런타임 형식은 `int`인데 `exampleMethod2`에는 문자열이 필요하므로 오버로드 확인이 런타임에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-136">Overload resolution fails at run time because the run-time type of `d1` is `int`, and `exampleMethod2` requires a string.</span></span>  
  
 <span data-ttu-id="b311e-137">[!code-cs[CsProgGuideTypes#55](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="b311e-137">[!code-cs[CsProgGuideTypes#55](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-type-dynamic_7.cs)]</span></span>  
  
## <a name="dynamic-language-runtime"></a><span data-ttu-id="b311e-138">동적 언어 런타임</span><span class="sxs-lookup"><span data-stu-id="b311e-138">Dynamic Language Runtime</span></span>  
 <span data-ttu-id="b311e-139">DLR(동적 언어 런타임)은 [!INCLUDE[net_v40_short](~/includes/net-v40-short-md.md)]의 새로운 API입니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-139">The dynamic language runtime (DLR) is a new API in [!INCLUDE[net_v40_short](~/includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="b311e-140">DLR은 C#에서 `dynamic` 형식을 지원하는 인프라를 제공하며, IronPython 및 IronRuby와 같은 동적 프로그래밍 언어를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-140">It provides the infrastructure that supports the `dynamic` type in C#, and also the implementation of dynamic programming languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="b311e-141">DLR에 대한 자세한 내용은 [동적 언어 런타임 개요](../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b311e-141">For more information about the DLR, see [Dynamic Language Runtime Overview](../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).</span></span>  
  
## <a name="com-interop"></a><span data-ttu-id="b311e-142">COM Interop</span><span class="sxs-lookup"><span data-stu-id="b311e-142">COM Interop</span></span>  
 [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)]<span data-ttu-id="b311e-143">에는 Office 자동화 API와 같은 COM API와의 상호 운용 환경을 개선하는 몇 가지 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-143"> includes several features that improve the experience of interoperating with COM APIs such as the Office Automation APIs.</span></span> <span data-ttu-id="b311e-144">개선 사항 중에는 `dynamic` 형식의 사용 및 [명명된 인수 및 선택적 인수](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)의 사용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-144">Among the improvements are the use of the `dynamic` type, and of [named and optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>  
  
 <span data-ttu-id="b311e-145">많은 COM 메서드는 형식을 `object`로 지정하여 인수 형식 및 반환 형식의 변환을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-145">Many COM methods allow for variation in argument types and return type by designating the types as `object`.</span></span> <span data-ttu-id="b311e-146">C#에서는 강력한 형식의 변수로 조정하기 위해 값을 명시적으로 캐스팅해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-146">This has necessitated explicit casting of the values to coordinate with strongly typed variables in C#.</span></span> <span data-ttu-id="b311e-147">[/link(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/link-compiler-option.md) 옵션을 사용하여 컴파일하는 경우 `dynamic` 형식을 사용하면 COM 서명에서 `object`의 발생을 마치 `dynamic` 형식인 것처럼 취급하여 캐스팅을 상당 부분 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-147">If you compile by using the [/link (C# Compiler Options)](../../../csharp/language-reference/compiler-options/link-compiler-option.md) option, the introduction of the `dynamic` type enables you to treat the occurrences of `object` in COM signatures as if they were of type `dynamic`, and thereby to avoid much of the casting.</span></span> <span data-ttu-id="b311e-148">예를 들어 다음 문은 `dynamic` 형식은 있고 `dynamic` 형식은 없는 Microsoft Office Excel 스프레드시트의 셀에 액세스하는 방법과 대조됩니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-148">For example, the following statements contrast how you access a cell in a Microsoft Office Excel spreadsheet with the `dynamic` type and without the `dynamic` type.</span></span>  
  
 <span data-ttu-id="b311e-149">[!code-cs[csOfficeWalkthrough#12](../../../csharp/programming-guide/interop/codesnippet/CSharp/using-type-dynamic_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="b311e-149">[!code-cs[csOfficeWalkthrough#12](../../../csharp/programming-guide/interop/codesnippet/CSharp/using-type-dynamic_8.cs)]</span></span>  
  
 <span data-ttu-id="b311e-150">[!code-cs[csOfficeWalkthrough#13](../../../csharp/programming-guide/interop/codesnippet/CSharp/using-type-dynamic_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="b311e-150">[!code-cs[csOfficeWalkthrough#13](../../../csharp/programming-guide/interop/codesnippet/CSharp/using-type-dynamic_9.cs)]</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="b311e-151">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b311e-151">Related Topics</span></span>  
  
|<span data-ttu-id="b311e-152">제목</span><span class="sxs-lookup"><span data-stu-id="b311e-152">Title</span></span>|<span data-ttu-id="b311e-153">설명</span><span class="sxs-lookup"><span data-stu-id="b311e-153">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b311e-154">dynamic</span><span class="sxs-lookup"><span data-stu-id="b311e-154">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)|<span data-ttu-id="b311e-155">`dynamic` 키워드의 사용법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-155">Describes the usage of the `dynamic` keyword.</span></span>|  
|[<span data-ttu-id="b311e-156">동적 언어 런타임 개요</span><span class="sxs-lookup"><span data-stu-id="b311e-156">Dynamic Language Runtime Overview</span></span>](../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)|<span data-ttu-id="b311e-157">동적 언어에 대한 서비스 집합을 CLR(공용 언어 런타임)에 추가하는 런타임 환경인 DLR 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-157">Provides an overview of the DLR, which is a runtime environment that adds a set of services for dynamic languages to the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="b311e-158">연습: 동적 개체 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="b311e-158">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)|<span data-ttu-id="b311e-159">사용자 지정 동적 개체를 만들고 `IronPython` 라이브러리에 액세스하는 프로젝트를 만드는 데 필요한 단계별 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-159">Provides step-by-step instructions for creating a custom dynamic object and for creating a project that accesses an `IronPython` library.</span></span>|  
|[<span data-ttu-id="b311e-160">방법: Visual C# 기능을 사용하여 Office Interop 개체에 액세스</span><span class="sxs-lookup"><span data-stu-id="b311e-160">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)|<span data-ttu-id="b311e-161">명명된 인수와 선택적 인수, `dynamic` 형식, Office API 개체에 대한 액세스를 간소화하는 기타 향상된 기능을 사용하는 프로젝트를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b311e-161">Demonstrates how to create a project that uses named and optional arguments, the `dynamic` type, and other enhancements that simplify access to Office API objects.</span></span>|

