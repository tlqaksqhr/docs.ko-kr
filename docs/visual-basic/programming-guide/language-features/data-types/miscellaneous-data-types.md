---
title: 기타 데이터 형식(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f80aacccab4c215b3e3917cc73097080aa6b9941
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="82343-102">기타 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82343-102">Miscellaneous Data Types (Visual Basic)</span></span>
<span data-ttu-id="82343-103">Visual Basic에서 숫자 또는 문자 분류 되지 않는 몇 가지 데이터 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="82343-103">Visual Basic supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="82343-104">를 처리 특수 데이터와 같은 예/아니요 값, 날짜/시간 값 및 개체 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="82343-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="82343-105">Visual Basic 데이터 형식-나란히 비교를 보여 주는 테이블을 참조 하십시오. [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82343-105">For a table showing a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="82343-106">부울 유형</span><span class="sxs-lookup"><span data-stu-id="82343-106">Boolean Type</span></span>  
 <span data-ttu-id="82343-107">[Boolean 데이터 형식](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) 로 해석 되는 부호 없는 값은 `True` 또는 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="82343-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="82343-108">데이터 너비 구현 하는 플랫폼에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="82343-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="82343-109">변수를 포함할 수 있으면 true/false 같은 두 가지 상태 값만 예/아니요 또는 켜기/끄기로 선언 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="82343-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="82343-110">날짜 형식</span><span class="sxs-lookup"><span data-stu-id="82343-110">Date Type</span></span>  
 <span data-ttu-id="82343-111">[Date 데이터 형식](../../../../visual-basic/language-reference/data-types/date-data-type.md) 는 날짜와 시간 정보를 보유 하는 64 비트 값입니다.</span><span class="sxs-lookup"><span data-stu-id="82343-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="82343-112">각 증분은 일반 달력에서 1 년 1 월 1의 시작 부분 (오전 12시) 이후 경과 된 시간의 100 나노초를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="82343-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="82343-113">변수 값을 날짜, 시간 값 또는 둘 다를 포함할 수 있으면로 선언 `Date`합니다.</span><span class="sxs-lookup"><span data-stu-id="82343-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="82343-114">개체 형식</span><span class="sxs-lookup"><span data-stu-id="82343-114">Object Type</span></span>  
 <span data-ttu-id="82343-115">[Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md) 응용 프로그램 내에서 또는 다른 응용 프로그램의 개체 인스턴스를 가리키는 32 비트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="82343-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="82343-116">`Object` 변수 데이터 형식의 모든 데이터를 응용 프로그램에서 인식 하는 모든 개체를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82343-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="82343-117">여기에 둘 다 *값 형식이*와 같은 `Integer`, `Boolean`, 및 구조 인스턴스 및 *참조 형식*, 와같은클래스에서생성된개체의인스턴스는`String`및 <xref:System.Windows.Forms.Form>, 배열 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="82343-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="82343-118">변수는 컴파일 타임에 알지 못하는 하는 클래스의 인스턴스에 대 한 포인터를 저장 하거나 다양 한 데이터 형식의 데이터를 가리킬 수로 선언 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="82343-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="82343-119">이점은 `Object` 데이터 형식을 사용 하면 모든 데이터 형식의 데이터를 저장 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="82343-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="82343-120">단점은 실행 시간이 오래을 느리게 수행 하는 응용 프로그램을 확인 하는 추가 작업을 인해 발생 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="82343-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="82343-121">사용 하는 경우는 `Object` 유발 값 형식에 대 한 변수를 *boxing* 및 *unboxing*합니다.</span><span class="sxs-lookup"><span data-stu-id="82343-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="82343-122">참조 형식에 대해 사용 하는 경우 발생할 *런타임에 바인딩*합니다.</span><span class="sxs-lookup"><span data-stu-id="82343-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82343-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82343-123">See Also</span></span>  
 [<span data-ttu-id="82343-124">형식 문자</span><span class="sxs-lookup"><span data-stu-id="82343-124">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [<span data-ttu-id="82343-125">기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82343-125">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="82343-126">숫자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82343-126">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [<span data-ttu-id="82343-127">문자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82343-127">Character Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [<span data-ttu-id="82343-128">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="82343-128">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="82343-129">초기 바인딩 및 런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="82343-129">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
