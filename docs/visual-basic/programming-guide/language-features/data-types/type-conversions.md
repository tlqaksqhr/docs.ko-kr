---
title: Visual Basic의 형식 변환
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- changing data types [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f1487d98f37e7ef00982de365d0d164435f84567
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="128e3-102">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="128e3-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="128e3-103">데이터 형식을 다른 형식으로 값을 변경 하는 프로세스 라고 *변환*합니다.</span><span class="sxs-lookup"><span data-stu-id="128e3-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="128e3-104">변환에는 하나 *확대* 또는 *축소*는 형식의 데이터 용량에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="128e3-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="128e3-105">또한 *암시적* 또는 *명시적*소스 코드의 구문에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="128e3-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="128e3-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="128e3-106">In This Section</span></span>  
 [<span data-ttu-id="128e3-107">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="128e3-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="128e3-108">변환 대상 형식의 데이터를 보유할 수 있는지 여부에 따라 분류에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="128e3-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="128e3-109">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="128e3-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="128e3-110">수행 여부를 Visual Basic 자동으로 분류 하는 변환에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="128e3-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="128e3-111">문자열과 다른 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="128e3-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="128e3-112">문자열과 숫자, 간의 변환에 대해 설명 `Boolean`, 또는 날짜/시간 값입니다.</span><span class="sxs-lookup"><span data-stu-id="128e3-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="128e3-113">방법: Visual Basic에서 다른 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="128e3-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="128e3-114">변환 하는 방법을 보여 줍니다.는 `Object` 변수를 다른 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="128e3-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="128e3-115">배열 규칙</span><span class="sxs-lookup"><span data-stu-id="128e3-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="128e3-116">배열 데이터 형식이 다른 형식 사이의 변환 과정을 단계별로 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="128e3-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="128e3-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="128e3-117">Related Sections</span></span>  
 [<span data-ttu-id="128e3-118">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="128e3-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="128e3-119">Visual Basic 데이터 형식을 소개 하 고 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="128e3-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="128e3-120">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="128e3-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="128e3-121">Visual Basic에서 제공 된 기본 데이터 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="128e3-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="128e3-122">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="128e3-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="128e3-123">데이터 형식으로 작업할 때 발생할 수 있는 몇 가지 일반적인 문제에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="128e3-123">Discusses some common problems that can arise when working with data types.</span></span>
