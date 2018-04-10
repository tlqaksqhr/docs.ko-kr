---
title: Visual Basic 언어 기능
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, elements of
- Visual Basic code
ms.assetid: b0b21730-298c-47e6-9a2f-cc81f628067b
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f7074206baa51259592cca3fdc224d99438791f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="visual-basic-language-features"></a><span data-ttu-id="ccf54-102">Visual Basic 언어 기능</span><span class="sxs-lookup"><span data-stu-id="ccf54-102">Visual Basic Language Features</span></span>
<span data-ttu-id="ccf54-103">다음 항목에서는 개체 지향 프로그래밍 언어인 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]의 필수 구성 요소를 소개하고 관련 내용을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-103">The following topics introduce and discuss the essential components of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], an object-oriented programming language.</span></span> <span data-ttu-id="ccf54-104">폼 및 컨트롤을 사용하여 자신의 응용 프로그램에 사용할 사용자 인터페이스를 만든 다음에는 응용 프로그램의 동작을 정의하는 코드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-104">After creating the user interface for your application using forms and controls, you need to write the code that defines the application's behavior.</span></span> <span data-ttu-id="ccf54-105">모든 최신 프로그래밍 언어와 마찬가지로 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에서도 일반적인 여러 프로그래밍 구문과 언어 요소를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-105">As with any modern programming language, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] supports a number of common programming constructs and language elements.</span></span>  
  
 <span data-ttu-id="ccf54-106">다른 언어로 프로그래밍해본 경우 이 섹션에서 다루는 내용의 상당 부분이 익숙할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-106">If you have programmed in other languages, much of the material covered in this section might seem familiar.</span></span> <span data-ttu-id="ccf54-107">대부분의 구문이 유사한 다른 언어의 구문과 비슷하지만 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]의 이벤트 구동 특성에는 몇 가지 미묘한 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-107">While most of the constructs are similar to those in other languages, the event-driven nature of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] introduces some subtle differences.</span></span>  
  
 <span data-ttu-id="ccf54-108">프로그래밍을 처음 접하는 경우 이 섹션의 자료가 코드 작성을 위한 기본 구성 요소에 대한 소개 문서가 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-108">If you are new to programming, the material in this section serves as an introduction to the basic building blocks for writing code.</span></span> <span data-ttu-id="ccf54-109">기본 사항을 이해하면 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]를 사용하여 강력한 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-109">Once you understand the basics, you can create powerful applications using [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ccf54-110">단원 내용</span><span class="sxs-lookup"><span data-stu-id="ccf54-110">In This Section</span></span>  
 [<span data-ttu-id="ccf54-111">배열</span><span class="sxs-lookup"><span data-stu-id="ccf54-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 <span data-ttu-id="ccf54-112">여러 관련 값을 포함하는 배열을 선언하고 사용하여 더 간단하면서 강력한 코드를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-112">Discusses making your code more compact and powerful by declaring and using arrays, which hold multiple related values.</span></span>  
  
 [<span data-ttu-id="ccf54-113">컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="ccf54-113">Collection Initializers</span></span>](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 <span data-ttu-id="ccf54-114">컬렉션을 만들고 값의 초기 집합으로 채울 수 있도록 하는 컬렉션 이니셜라이저에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-114">Describes collection initializers, which enable you to create a collection and populate it with an initial set of values.</span></span>  
  
 [<span data-ttu-id="ccf54-115">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="ccf54-115">Constants and Enumerations</span></span>](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 <span data-ttu-id="ccf54-116">반복 사용을 위해 관련된 상수 값 집합을 포함하여 변경되지 않는 값을 저장하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-116">Discusses storing unchanging values for repeated use, including sets of related constant values.</span></span>  
  
 [<span data-ttu-id="ccf54-117">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="ccf54-117">Control Flow</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 <span data-ttu-id="ccf54-118">프로그램의 실행 흐름을 제어하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-118">Shows how to regulate the flow of your program's execution.</span></span>  
  
 [<span data-ttu-id="ccf54-119">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ccf54-119">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="ccf54-120">프로그래밍 요소가 보유할 수 있는 데이터 종류와 데이터가 저장되는 방식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-120">Describes what kinds of data a programming element can hold and how that data is stored.</span></span>  
  
 [<span data-ttu-id="ccf54-121">선언 요소</span><span class="sxs-lookup"><span data-stu-id="ccf54-121">Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 <span data-ttu-id="ccf54-122">선언할 수 있는 프로그래밍 요소, 해당 이름과 특성, 컴파일러가 해당 참조를 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-122">Covers programming elements you can declare, their names and characteristics, and how the compiler resolves references to them.</span></span>  
  
 [<span data-ttu-id="ccf54-123">대리자</span><span class="sxs-lookup"><span data-stu-id="ccf54-123">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 <span data-ttu-id="ccf54-124">대리자를 소개하고 Visual Basic에서 대리자를 사용하는 방식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-124">Provides an introduction to delegates and how they are used in Visual Basic.</span></span>  
  
 [<span data-ttu-id="ccf54-125">초기 바인딩 및 런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="ccf54-125">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 <span data-ttu-id="ccf54-126">개체가 개체 변수에 할당될 때 컴파일러가 수행하는 바인딩과 초기 바인딩된 개체 및 런타임에 바인딩된 개체 간의 차이점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-126">Describes binding, which is performed by the compiler when an object is assigned to an object variable, and the differences between early-bound and late-bound objects.</span></span>  
  
 [<span data-ttu-id="ccf54-127">오류 형식</span><span class="sxs-lookup"><span data-stu-id="ccf54-127">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 <span data-ttu-id="ccf54-128">구문 오류, 런타임 오류 및 논리 오류에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-128">Provides an overview of syntax errors, run-time errors, and logic errors.</span></span>  
  
 [<span data-ttu-id="ccf54-129">이벤트</span><span class="sxs-lookup"><span data-stu-id="ccf54-129">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)  
 <span data-ttu-id="ccf54-130">이벤트를 선언하고 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-130">Shows how to declare and use events.</span></span>  
  
 [<span data-ttu-id="ccf54-131">인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccf54-131">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 <span data-ttu-id="ccf54-132">인터페이스의 정의와 응용 프로그램에서 사용할 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-132">Describes what interfaces are and how you can use them in your applications.</span></span>  
  
 [<span data-ttu-id="ccf54-133">LINQ</span><span class="sxs-lookup"><span data-stu-id="ccf54-133">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="ccf54-134">[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 기능 및 프로그래밍을 소개하는 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-134">Provides links to topics that introduce [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] features and programming.</span></span>  
  
 [<span data-ttu-id="ccf54-135">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="ccf54-135">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 <span data-ttu-id="ccf54-136">개체 및 클래스의 개요, 사용 방법, 서로 간의 관계, 개체와 클래스가 노출하는 속성, 메서드 및 이벤트의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-136">Provides an overview of objects and classes, how they are used, their relationships to each other, and the properties, methods, and events they expose.</span></span>  
  
 [<span data-ttu-id="ccf54-137">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="ccf54-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 <span data-ttu-id="ccf54-138">값 저장 요소를 조작하는 코드 요소, 효율적으로 사용하는 방법 및 조합해서 새 값을 산출하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-138">Describes the code elements that manipulate value-holding elements, how to use them efficiently, and how to combine them to yield new values.</span></span>  
  
 [<span data-ttu-id="ccf54-139">절차</span><span class="sxs-lookup"><span data-stu-id="ccf54-139">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 <span data-ttu-id="ccf54-140">`Sub`, `Function`, `Property` 및 `Operator` 프로시저는 물론, 재귀 및 오버로드된 프로시저와 같은 고급 항목에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-140">Describes `Sub`, `Function`, `Property`, and `Operator` procedures, as well as advanced topics such as recursive and overloaded procedures.</span></span>  
  
 [<span data-ttu-id="ccf54-141">문</span><span class="sxs-lookup"><span data-stu-id="ccf54-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 <span data-ttu-id="ccf54-142">선언 및 실행 파일 문에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-142">Describes declaration and executable statements.</span></span>  
  
 [<span data-ttu-id="ccf54-143">문자열</span><span class="sxs-lookup"><span data-stu-id="ccf54-143">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 <span data-ttu-id="ccf54-144">Visual Basic에서 문자열을 사용하는 방법에 대한 기본 개념을 설명하는 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-144">Provides links to topics that describe the basic concepts about using strings in Visual Basic.</span></span>  
  
 [<span data-ttu-id="ccf54-145">변수</span><span class="sxs-lookup"><span data-stu-id="ccf54-145">Variables</span></span>](../../../visual-basic/programming-guide/language-features/variables/index.md)  
 <span data-ttu-id="ccf54-146">변수를 소개하고 Visual Basic에서 변수를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-146">Introduces variables and describes how to use them in Visual Basic.</span></span>  
  
 [<span data-ttu-id="ccf54-147">XML</span><span class="sxs-lookup"><span data-stu-id="ccf54-147">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="ccf54-148">Visual Basic에서 XML을 사용하는 방법을 설명하는 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-148">Provides links to topics that describe how to use XML in Visual Basic.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ccf54-149">관련 단원</span><span class="sxs-lookup"><span data-stu-id="ccf54-149">Related Sections</span></span>  
 [<span data-ttu-id="ccf54-150">컬렉션</span><span class="sxs-lookup"><span data-stu-id="ccf54-150">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)  
 <span data-ttu-id="ccf54-151">.NET Framework에서 제공되는 컬렉션의 형식 중 일부에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-151">Describes some of the types of collections that are provided by the .NET Framework.</span></span> <span data-ttu-id="ccf54-152">간단한 컬렉션 및 키/값 쌍의 컬렉션을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-152">Demonstrates how to use simple collections and collections of key/value pairs.</span></span>  
  
 [<span data-ttu-id="ccf54-153">Visual Basic 언어 참조</span><span class="sxs-lookup"><span data-stu-id="ccf54-153">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
 <span data-ttu-id="ccf54-154">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 프로그래밍의 다양한 측면에 대한 참조 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf54-154">Provides reference information on various aspects of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programming.</span></span>
