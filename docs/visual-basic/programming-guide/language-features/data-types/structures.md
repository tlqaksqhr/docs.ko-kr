---
title: "구조체(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- structures [Visual Basic]
- user-defined data types [Visual Basic], structures
- user-defined types [Visual Basic], about user-defined types
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], about user-defined data types
- types [Visual Basic], user-defined
ms.assetid: 55e86462-5e99-4d33-8018-6d097ca491b2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: de99d67ee31d8fb8e92e0a351142b30f622bf5f0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="structures-visual-basic"></a><span data-ttu-id="41d96-102">구조체(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41d96-102">Structures (Visual Basic)</span></span>
<span data-ttu-id="41d96-103">A *구조* 사용자 정의 형식 (UDT)의 이전 버전에서 지 원하는 일반화 인 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="41d96-103">A *structure* is a generalization of the user-defined type (UDT) supported by previous versions of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="41d96-104">필드와 함께 구조는 속성, 메서드 및 이벤트를 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d96-104">In addition to fields, structures can expose properties, methods, and events.</span></span> <span data-ttu-id="41d96-105">구조체는 하나 이상의 인터페이스를 구현할 수 하 고 각 필드에 대 한 개별 액세스 수준을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d96-105">A structure can implement one or more interfaces, and you can declare individual access levels for each field.</span></span>  
  
 <span data-ttu-id="41d96-106">구조를 만들려면 다른 형식의 데이터 항목을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d96-106">You can combine data items of different types to create a structure.</span></span> <span data-ttu-id="41d96-107">구조체는 하나 이상의 연결 *요소* 통신과 구조체 자체와 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d96-107">A structure associates one or more *elements* with each other and with the structure itself.</span></span> <span data-ttu-id="41d96-108">구조를 선언할 때 됩니다는 *복합 데이터 형식을*, 형식의 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d96-108">When you declare a structure, it becomes a *composite data type*, and you can declare variables of that type.</span></span>  
  
 <span data-ttu-id="41d96-109">구조는 관련 된 일부의 정보를 보유 하는 단일 변수를 원하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d96-109">Structures are useful when you want a single variable to hold several related pieces of information.</span></span> <span data-ttu-id="41d96-110">예를 들어 다음 직원의 이름, 전화 확장 및 급여를 함께 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="41d96-110">For example, you might want to keep an employee's name, telephone extension, and salary together.</span></span> <span data-ttu-id="41d96-111">이 정보에 대 한 몇 가지 변수를 사용할 수 있습니다 또는 구조를 정의 하 고 단일 직원 변수로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41d96-111">You could use several variables for this information, or you could define a structure and use it for a single employee variable.</span></span> <span data-ttu-id="41d96-112">구조체의 장점은 직원 및 변수의 따라서 많은 인스턴스가 있을 때 드러납니다.</span><span class="sxs-lookup"><span data-stu-id="41d96-112">The advantage of the structure becomes apparent when you have many employees and therefore many instances of the variable.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="41d96-113">단원 내용</span><span class="sxs-lookup"><span data-stu-id="41d96-113">In This Section</span></span>  
 [<span data-ttu-id="41d96-114">방법: 구조체 선언</span><span class="sxs-lookup"><span data-stu-id="41d96-114">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 <span data-ttu-id="41d96-115">구조와 해당 요소를 선언 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41d96-115">Shows how to declare a structure and its elements.</span></span>  
  
 [<span data-ttu-id="41d96-116">구조체 변수</span><span class="sxs-lookup"><span data-stu-id="41d96-116">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 <span data-ttu-id="41d96-117">구조체를 변수에 할당 하 고 해당 요소에 액세스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d96-117">Covers assigning a structure to a variable and accessing its elements.</span></span>  
  
 [<span data-ttu-id="41d96-118">구조체 및 기타 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="41d96-118">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 <span data-ttu-id="41d96-119">구조 배열, 개체, 프로시저 및 서로 상호 작용 하는 방법을 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d96-119">Summarizes how structures interact with arrays, objects, procedures, and each other.</span></span>  
  
 [<span data-ttu-id="41d96-120">구조체와 클래스</span><span class="sxs-lookup"><span data-stu-id="41d96-120">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 <span data-ttu-id="41d96-121">유사성과 구조체와 클래스 간의 차이점에 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41d96-121">Describes the similarities and differences between structures and classes.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="41d96-122">관련 단원</span><span class="sxs-lookup"><span data-stu-id="41d96-122">Related Sections</span></span>  
 [<span data-ttu-id="41d96-123">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="41d96-123">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="41d96-124">소개는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 데이터 형식 및 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d96-124">Introduces the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="41d96-125">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="41d96-125">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="41d96-126">제공한 기본 데이터 형식 목록을 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="41d96-126">Lists the elementary data types supplied by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>
