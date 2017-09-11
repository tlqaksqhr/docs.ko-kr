---
title: "Visual Basic의 상수 및 열거형"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- enumerations [Visual Basic]
- Visual Basic code, constants
- constants
- object libraries, Object Browser
- Visual Basic code, enumerations
- declaring constants, enumerations
- naming conventions, constants
- Visual Basic code, improving readability with constants
ms.assetid: c8aba36e-fa47-4a33-8b68-cb2009218270
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 5ef8ade1100bb660af4d968d4b600aba41073fc2
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="constants-and-enumerations-in-visual-basic"></a><span data-ttu-id="3cf98-102">Visual Basic의 상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="3cf98-102">Constants and Enumerations in Visual Basic</span></span>
<span data-ttu-id="3cf98-103">상수는 변경되지 않는 값 대신 의미 있는 이름을 사용하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="3cf98-103">Constants are a way to use meaningful names in place of a value that does not change.</span></span> <span data-ttu-id="3cf98-104">상수는 응용 프로그램 실행 중 변함없이 유지되는 값을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf98-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="3cf98-105">상수를 사용하여 숫자 대신 의미 있는 이름을 제공하여 코드의 가독성을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf98-105">You can use constants to provide meaningful names, instead of numbers, making your code more readable.</span></span>  
  
 <span data-ttu-id="3cf98-106">열거형은 관련된 상수 집합으로 작업하고 이름과 상수 값을 연결하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf98-106">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="3cf98-107">예를 들어 요일과 연결된 정수 상수에 대한 열거형을 선언한 다음, 코드에 정수 값 대신 요일 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf98-107">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3cf98-108">단원 내용</span><span class="sxs-lookup"><span data-stu-id="3cf98-108">In This Section</span></span>  
  
|<span data-ttu-id="3cf98-109">용어</span><span class="sxs-lookup"><span data-stu-id="3cf98-109">Term</span></span>|<span data-ttu-id="3cf98-110">정의</span><span class="sxs-lookup"><span data-stu-id="3cf98-110">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="3cf98-111">상수 개요</span><span class="sxs-lookup"><span data-stu-id="3cf98-111">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)|<span data-ttu-id="3cf98-112">이 단원의 항목에서는 상수 및 해당 용도를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf98-112">Topics in this section describe constants and their uses.</span></span>|  
|[<span data-ttu-id="3cf98-113">열거형 개요</span><span class="sxs-lookup"><span data-stu-id="3cf98-113">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)|<span data-ttu-id="3cf98-114">이 단원의 항목에서는 열거형 및 해당 용도를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf98-114">Topics in this section describe enumerations and their uses.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="3cf98-115">관련 단원</span><span class="sxs-lookup"><span data-stu-id="3cf98-115">Related Sections</span></span>  
  
|<span data-ttu-id="3cf98-116">용어</span><span class="sxs-lookup"><span data-stu-id="3cf98-116">Term</span></span>|<span data-ttu-id="3cf98-117">정의</span><span class="sxs-lookup"><span data-stu-id="3cf98-117">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="3cf98-118">Const 문</span><span class="sxs-lookup"><span data-stu-id="3cf98-118">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)|<span data-ttu-id="3cf98-119">상수를 선언하는 데 사용되는 `Const` 문을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf98-119">Describes the `Const` statement, which is used to declare constants.</span></span>|  
|[<span data-ttu-id="3cf98-120">Enum 문</span><span class="sxs-lookup"><span data-stu-id="3cf98-120">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)|<span data-ttu-id="3cf98-121">열거형을 만드는 데 사용되는 `Enum` 문을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf98-121">Describes the `Enum` statement, which is used to create enumerations.</span></span>|  
|[<span data-ttu-id="3cf98-122">Option Explicit 문</span><span class="sxs-lookup"><span data-stu-id="3cf98-122">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)|<span data-ttu-id="3cf98-123">해당 모듈에서 모든 변수에 대해 명시적 선언을 적용하기 위해 모듈 수준에서 사용되는 `Option Explicit` 문을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf98-123">Describes the `Option Explicit` statement, which is used at module level to force explicit declaration of all variables in that module.</span></span>|  
|[<span data-ttu-id="3cf98-124">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="3cf98-124">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)|<span data-ttu-id="3cf98-125">변수를 선언할 때 지역 형식 유추를 사용하도록 설정하는 `Option Infer` 문을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf98-125">Describes the `Option Infer` statement, which enables the use of local type inference in declaring variables.</span></span>|  
|[<span data-ttu-id="3cf98-126">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="3cf98-126">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|<span data-ttu-id="3cf98-127">암시적 데이터 형식을 확대 변환으로만 제한하고, 런타임에 바인딩을 허용하지 않고, `Object` 형식이 되는 암시적 형식을 허용하지 않는 `Option Strict` 문을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf98-127">Describes the `Option Strict` statement, which restricts implicit data type conversions to only widening conversions, disallows late binding, and disallows implicit typing that results in an `Object` type.</span></span>|

