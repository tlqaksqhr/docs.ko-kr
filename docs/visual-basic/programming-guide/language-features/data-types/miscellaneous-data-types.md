---
title: "기타 데이터 형식 (Visual Basic) | Microsoft 문서"
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
- Object data type, data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
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
ms.openlocfilehash: ed7b61a5ec57ff85347f2c257e321ab9ec425274
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="3c364-102">기타 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c364-102">Miscellaneous Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="3c364-103">숫자 또는 문자 분류 되지 않는 몇 가지 데이터 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c364-103"> supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="3c364-104">대신,은 특수 한 데이터 처리와 같은 예/아니요 값, 날짜/시간 값 및 개체 주소 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c364-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="3c364-105">나란히 비교를 보여 주는 표는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 데이터 형식 참조 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3c364-105">For a table showing a side-by-side comparison of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="3c364-106">부울 형식</span><span class="sxs-lookup"><span data-stu-id="3c364-106">Boolean Type</span></span>  
 <span data-ttu-id="3c364-107">[Boolean 데이터 형식](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) 로 해석 되는 부호 없는 값은 `True` 또는 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="3c364-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="3c364-108">데이터 너비 구현 하는 플랫폼에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="3c364-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="3c364-109">변수를 포함할 수 있으면 true/false와 같은 두 가지 상태 값만 예/아니요 또는 켜기/끄기로 선언 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="3c364-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="3c364-110">날짜 형식</span><span class="sxs-lookup"><span data-stu-id="3c364-110">Date Type</span></span>  
 <span data-ttu-id="3c364-111">[Date 데이터 형식](../../../../visual-basic/language-reference/data-types/date-data-type.md) 날짜와 시간 정보를 보유 하는 64 비트 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3c364-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="3c364-112">각 증분 일반 달력에서 1 년 1 월 1 (오전 12시)부터 경과 된 시간 (100 나노초)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c364-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="3c364-113">변수는 날짜 값, 시간 값 또는 둘 다를 포함할 수 있으면로 선언 `Date`합니다.</span><span class="sxs-lookup"><span data-stu-id="3c364-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="3c364-114">개체 형식</span><span class="sxs-lookup"><span data-stu-id="3c364-114">Object Type</span></span>  
 <span data-ttu-id="3c364-115">[Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md) 응용 프로그램 내에서 또는 일부 다른 응용 프로그램에서 개체 인스턴스를 가리키는 32 비트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3c364-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="3c364-116">`Object` 변수는 모든 데이터 형식의 데이터 또는 응용 프로그램에서 인식, 모든 개체를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c364-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="3c364-117">모두 포함이 *값 형식*와 같은 `Integer`, `Boolean`, 및 구조 인스턴스 및 *참조 형식*이며와 같은 클래스에서 생성 된 개체의 인스턴스인 `String` 및 <xref:System.Windows.Forms.Form>, 배열 인스턴스.</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="3c364-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="3c364-118">컴파일 타임에 모르는 하는 클래스의 인스턴스에 대 한 포인터를 저장 하는 변수 또는 다양 한 데이터 형식의 데이터를 가리키는 수로 선언 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="3c364-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="3c364-119">장점은 `Object` 데이터 형식을 사용 하면 모든 데이터 형식의 데이터를 저장 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c364-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="3c364-120">단점은 실행 시간이 더 오래 걸리는 느리게 수행 하는 응용 프로그램을 확인 하는 추가 작업을 인해 발생 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c364-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="3c364-121">사용 하는 경우는 `Object` 유발 값 형식에 대 한 변수를 *boxing* 및 *unboxing*합니다.</span><span class="sxs-lookup"><span data-stu-id="3c364-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="3c364-122">참조 형식에 대해 사용 하는 경우 발생할 *런타임에 바인딩*합니다.</span><span class="sxs-lookup"><span data-stu-id="3c364-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c364-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c364-123">See Also</span></span>  
 <span data-ttu-id="3c364-124">[형식 문자](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span><span class="sxs-lookup"><span data-stu-id="3c364-124">[Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span></span>  
<span data-ttu-id="3c364-125"> [기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="3c364-125"> [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="3c364-126"> [숫자 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="3c364-126"> [Numeric Data Types](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span></span>  
<span data-ttu-id="3c364-127"> [문자 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="3c364-127"> [Character Data Types](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md) </span></span>  
<span data-ttu-id="3c364-128"> [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="3c364-128"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="3c364-129"> [초기 바인딩 및 런타임에 바인딩](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span><span class="sxs-lookup"><span data-stu-id="3c364-129"> [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span></span>
