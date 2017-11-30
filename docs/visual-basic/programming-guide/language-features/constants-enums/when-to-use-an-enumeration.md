---
title: "열거형을 사용하는 경우(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a3b2937cc71c0c31bd8dce3d77fb33f48e1b5750
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="6ed09-102">열거형을 사용하는 경우(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ed09-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="6ed09-103">열거형에는 쉽게 관련된 상수 집합으로 작업 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="6ed09-104">열거형, 또는 `Enum`, 값 집합에 대 한 기호화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="6ed09-105">열거형 데이터 형식으로 처리 되 고 변수 및 속성과 함께 사용 하기 위해 상수 집합을 만드는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="6ed09-106">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="6ed09-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="6ed09-107">프로시저에서 제한 된 변수 집합을 열거를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="6ed09-108">의미 있는 이름을 사용 하는 경우에 특히 더 명확 하 게 하 고 읽기 쉬운 코드에 대 한 열거형을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="6ed09-109">열거형을 사용 하 여의 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-109">The benefits of using enumerations include:</span></span>  
  
-   <span data-ttu-id="6ed09-110">숫자를 잘못 입력 하 여 발생 하는 오류를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="6ed09-111">나중에 값을 변경 하려면 쉽게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-111">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="6ed09-112">에서는 코드는 오류 쉬워지므로 가능성이 더 낮아집니다 것을 의미를 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
-   <span data-ttu-id="6ed09-113">다음 버전과 호환성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-113">Ensures forward compatibility.</span></span> <span data-ttu-id="6ed09-114">열거형을 사용 하면 코드는 나중에 멤버 이름에 해당 하는 값 변경 되 면 실패할 가능성이 적습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="6ed09-115">열거형 이름 지정</span><span class="sxs-lookup"><span data-stu-id="6ed09-115">Naming Enumerations</span></span>  
 <span data-ttu-id="6ed09-116">열거형 멤버에 대 한 명명 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="6ed09-117">때 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 열거형 멤버 이름을 발견 다른 참조 된 형식 라이브러리의 이름이 같으면 예외가 throw 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-117">When [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="6ed09-118">응용 프로그램 또는 구성 요소에서 값을 식별 하는 고유한 접두사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="6ed09-119">열거형의 멤버를 참조할 때 있습니다 해야 멤버 이름을 열거형 이름으로 한정. 그렇지 않으면 사용 하 여는 `Imports` 문.</span><span class="sxs-lookup"><span data-stu-id="6ed09-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="6ed09-120">자세한 내용은 참조 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="6ed09-121">미리 정의 된 열거형</span><span class="sxs-lookup"><span data-stu-id="6ed09-121">Predefined Enumerations</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="6ed09-122">와 같은 다양 한 미리 정의 된 열거형 제공 `FirstDayOfWeek` 및 `MsgBoxResult`, 코드를 용이 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-122"> provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="6ed09-123">이러한 기능의 목록은 참조 [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed09-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ed09-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ed09-124">See Also</span></span>  
 [<span data-ttu-id="6ed09-125">방법: 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="6ed09-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="6ed09-126">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="6ed09-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="6ed09-127">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="6ed09-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="6ed09-128">방법: Visual Basic에서 열거형 반복</span><span class="sxs-lookup"><span data-stu-id="6ed09-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="6ed09-129">방법: 열거형 값과 연결된 문자열 확인</span><span class="sxs-lookup"><span data-stu-id="6ed09-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="6ed09-130">Enum 문</span><span class="sxs-lookup"><span data-stu-id="6ed09-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="6ed09-131">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="6ed09-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
