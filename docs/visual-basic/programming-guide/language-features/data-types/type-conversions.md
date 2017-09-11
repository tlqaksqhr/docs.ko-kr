---
title: "Visual Basic의 형식 변환 | Microsoft 문서"
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
- conversions, type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion
- conversions, data type
- changing data types
- data type conversion
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 61606572dd1f10dc5df4ed4baec02f230a23c8d6
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="c2584-102">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="c2584-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="c2584-103">데이터 형식을 다른 형식으로 값을 변경 하는 프로세스 라고 *변환*합니다.</span><span class="sxs-lookup"><span data-stu-id="c2584-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="c2584-104">변환 중 하나에 *확대* 또는 *축소*는 형식의 데이터 용량에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2584-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="c2584-105">또한 *암시적* 또는 *명시적*소스 코드의 구문에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2584-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c2584-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="c2584-106">In This Section</span></span>  
 [<span data-ttu-id="c2584-107">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="c2584-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="c2584-108">대상 형식에서 데이터를 저장할 수 있는지 여부에 따라 분류 하는 변환에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2584-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="c2584-109">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="c2584-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="c2584-110">여부를 기준으로 분류 하는 변환에 설명 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 자동으로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2584-110">Discusses conversions classified by whether [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] performs them automatically.</span></span>  
  
 [<span data-ttu-id="c2584-111">문자열과 다른 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="c2584-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="c2584-112">문자열과 숫자, 간의 변환에 대해 설명 `Boolean`, 또는 날짜/시간 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c2584-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="c2584-113">방법: Visual Basic에서 다른 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="c2584-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="c2584-114">변환 하는 방법을 보여 줍니다는 `Object` 변수를 다른 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c2584-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="c2584-115">배열 규칙</span><span class="sxs-lookup"><span data-stu-id="c2584-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="c2584-116">서로 다른 데이터 형식의 배열 간 변환 과정을 단계별로 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2584-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c2584-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="c2584-117">Related Sections</span></span>  
 [<span data-ttu-id="c2584-118">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c2584-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="c2584-119">소개는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 데이터 형식 및 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2584-119">Introduces the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="c2584-120">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c2584-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="c2584-121">제공 하는 기본 데이터 형식 나열 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="c2584-121">Lists the elementary data types supplied by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 [<span data-ttu-id="c2584-122">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c2584-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="c2584-123">데이터 형식으로 작업할 때 발생할 수 있는 몇 가지 일반적인 문제에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2584-123">Discusses some common problems that can arise when working with data types.</span></span>
