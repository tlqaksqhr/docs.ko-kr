---
title: "DateTimeOffset 개체 인스턴스화"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
- DateTimeOffset structure, converting to DateTime
- DateTimeOffset structure, instantiating
ms.assetid: 9648375f-d368-4373-a976-3332ece00c0a
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f072aecf45aaaf9bd4aec845a698d6f12916fedb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="instantiating-a-datetimeoffset-object"></a><span data-ttu-id="44686-102">DateTimeOffset 개체 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="44686-102">Instantiating a DateTimeOffset object</span></span>

<span data-ttu-id="44686-103"><xref:System.DateTimeOffset> 구조체는 새 <xref:System.DateTimeOffset> 값을 만들 수 있는 여러 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44686-103">The <xref:System.DateTimeOffset> structure offers a number of ways to create new <xref:System.DateTimeOffset> values.</span></span> <span data-ttu-id="44686-104">새로운을 인스턴스화하기 위한 사용할 수 있는 방법을 직접적으로 부합 그 중 대부분 <xref:System.DateTime> 값을 utc (협정 세계시) 로부터의 오프셋 날짜 및 시간 값을 지정할 수 있도록 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="44686-104">Many of them correspond directly to the methods available for instantiating new <xref:System.DateTime> values, with enhancements that allow you to specify the date and time value's offset from Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="44686-105">특히, 인스턴스화할 수 있습니다는 <xref:System.DateTimeOffset> 다음과 같은 방법으로 값:</span><span class="sxs-lookup"><span data-stu-id="44686-105">In particular, you can instantiate a <xref:System.DateTimeOffset> value in the following ways:</span></span>

* <span data-ttu-id="44686-106">날짜 및 시간 리터럴를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="44686-106">By using a date and time literal.</span></span>

* <span data-ttu-id="44686-107">호출 하 여 한 <xref:System.DateTimeOffset> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-107">By calling a <xref:System.DateTimeOffset> constructor.</span></span>

* <span data-ttu-id="44686-108">값을 암시적으로 변환 하 여 <xref:System.DateTimeOffset> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-108">By implicitly converting a value to <xref:System.DateTimeOffset> value.</span></span>

* <span data-ttu-id="44686-109">날짜 및 시간의 문자열 표현 구문 분석</span><span class="sxs-lookup"><span data-stu-id="44686-109">By parsing the string representation of a date and time.</span></span>

<span data-ttu-id="44686-110">이 항목에서는 이러한 메서드에 대 한 새로운 인스턴스화 작업과 큰 세부 정보 및 코드 예제를 제공 <xref:System.DateTimeOffset> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-110">This topic provides greater detail and code examples that illustrate these methods of instantiating new <xref:System.DateTimeOffset> values.</span></span>

## <a name="date-and-time-literals"></a><span data-ttu-id="44686-111">날짜 / 시간 리터럴</span><span class="sxs-lookup"><span data-stu-id="44686-111">Date and time literals</span></span>

<span data-ttu-id="44686-112">지 원하는 언어에,을 인스턴스화하는 가장 일반적인 방법 중 하나는 <xref:System.DateTime> 날짜와 시간을 하드 코드 된 리터럴 값으로 제공 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-112">For languages that support it, one of the most common ways to instantiate a <xref:System.DateTime> value is to provide the date and time as a hard-coded literal value.</span></span> <span data-ttu-id="44686-113">예를 들어 다음 Visual Basic 코드 만듭니다는 <xref:System.DateTime> 값을 가진 개체 2008 년 1 월 1 일 오전 10시입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-113">For example, the following Visual Basic code creates a <xref:System.DateTime> object whose value is January 1, 2008, at 10:00 AM.</span></span>

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

<span data-ttu-id="44686-114"><xref:System.DateTimeOffset>지 원하는 언어를 사용 하는 경우 날짜 및 시간 리터럴을 사용 하 여 값 초기화할 수도 있습니다 <xref:System.DateTime> 리터럴.</span><span class="sxs-lookup"><span data-stu-id="44686-114"><xref:System.DateTimeOffset> values can also be initialized using date and time literals when using languages that support <xref:System.DateTime> literals.</span></span> <span data-ttu-id="44686-115">예를 들어 다음 Visual Basic 코드 만듭니다는 <xref:System.DateTimeOffset> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-115">For example, the following Visual Basic code creates a <xref:System.DateTimeOffset> object.</span></span>

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

<span data-ttu-id="44686-116">콘솔 출력에서 볼 수 있듯이 <xref:System.DateTimeOffset> 이 방법으로 만든 하는 값이 현지 표준 시간대 오프셋을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="44686-116">As the console output shows, the <xref:System.DateTimeOffset> value created in this way is assigned the offset of the local time zone.</span></span> <span data-ttu-id="44686-117">즉, 한 <xref:System.DateTimeOffset> 코드는 서로 다른 컴퓨터에서 실행 되 면 리터럴 문자를 사용 하 여 할당 된 값에 단일 시점으로 식별 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44686-117">This means that a <xref:System.DateTimeOffset> value assigned using a character literal does not identify a single point of time if the code is run on different computers.</span></span>

## <a name="datetimeoffset-constructors"></a><span data-ttu-id="44686-118">DateTimeOffset 생성자</span><span class="sxs-lookup"><span data-stu-id="44686-118">DateTimeOffset constructors</span></span>

<span data-ttu-id="44686-119"><xref:System.DateTimeOffset> 형식은 6 개 생성자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="44686-119">The <xref:System.DateTimeOffset> type defines six constructors.</span></span> <span data-ttu-id="44686-120">에 직접 해당 중 4 개 <xref:System.DateTime> 형식의 추가 매개 변수를 가진 생성자 <xref:System.TimeSpan> 날짜를 정의 하 고 UTC에서의 시간 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-120">Four of them correspond directly to <xref:System.DateTime> constructors, with an additional parameter of type <xref:System.TimeSpan> that defines the date and time's offset from UTC.</span></span> <span data-ttu-id="44686-121">정의할 수 있습니다는 <xref:System.DateTimeOffset> 값의 개별 날짜 및 시간 구성 요소 값에 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="44686-121">These allow you to define a <xref:System.DateTimeOffset> value based on the value of its individual date and time components.</span></span> <span data-ttu-id="44686-122">예를 들어 다음 코드를 사용 하 여 이러한 네 가지 생성자 인스턴스화할 <xref:System.DateTimeOffset> 7/1/2008의 동일한 값을 사용 하 여 개체 오전 12시 05분 + 01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-122">For example, the following code uses these four constructors to instantiate <xref:System.DateTimeOffset> objects with identical values of 7/1/2008 12:05 AM +01:00.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

<span data-ttu-id="44686-123">때의 값은 <xref:System.DateTimeOffset> 개체를 사용 하 여 인스턴스화될는 <xref:System.Globalization.PersianCalendar> 개체의 생성자에 대 한 인수 중 하나로 콘솔에 표시 되 면 페르시아 력의 아니라 그레고리오의 날짜로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44686-123">Note that, when the value of the <xref:System.DateTimeOffset> object instantiated using a <xref:System.Globalization.PersianCalendar> object as one of the arguments to its constructor is displayed to the console, it is expressed as a date in the Gregorian rather than the Persian calendar.</span></span> <span data-ttu-id="44686-124">페르시아력을 사용 하 여 날짜를 출력 하려면에서 예제를 참조 하십시오.는 <xref:System.Globalization.PersianCalendar> 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-124">To output a date using the Persian calendar, see the example in the <xref:System.Globalization.PersianCalendar> topic.</span></span>

<span data-ttu-id="44686-125">다른 두 생성자는 <xref:System.DateTimeOffset> 에서 개체는 <xref:System.DateTime> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-125">The other two constructors create a <xref:System.DateTimeOffset> object from a <xref:System.DateTime> value.</span></span> <span data-ttu-id="44686-126">그 중 첫 번째에는 단일 매개 변수는 <xref:System.DateTime> 값으로 변환할는 <xref:System.DateTimeOffset> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-126">The first of these has a single parameter, the <xref:System.DateTime> value to convert to a <xref:System.DateTimeOffset> value.</span></span> <span data-ttu-id="44686-127">결과의 오프셋 <xref:System.DateTimeOffset> 값에 따라 달라 집니다는 <xref:System.DateTime.Kind%2A> 생성자의 단일 매개 변수 속성.</span><span class="sxs-lookup"><span data-stu-id="44686-127">The offset of the resulting <xref:System.DateTimeOffset> value depends on the <xref:System.DateTime.Kind%2A> property of the constructor's single parameter.</span></span> <span data-ttu-id="44686-128">값이 <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, 오프셋 같게 설정 된 <xref:System.TimeSpan.Zero?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="44686-128">If its value is <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, the offset is set equal to <xref:System.TimeSpan.Zero?displayProperty=nameWithType>.</span></span> <span data-ttu-id="44686-129">그렇지 않은 경우 해당 오프셋은 현지 표준 시간대의 값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="44686-129">Otherwise, its offset is set equal to that of the local time zone.</span></span> <span data-ttu-id="44686-130">다음 예제에서는이 생성자를 인스턴스화하 <xref:System.DateTimeOffset> UTC와 현지 표준 시간대를 나타내는 개체:</span><span class="sxs-lookup"><span data-stu-id="44686-130">The following example illustrates the use of this constructor to instantiate <xref:System.DateTimeOffset> objects representing UTC and the local time zone:</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> <span data-ttu-id="44686-131">호출의 오버 로드는 <xref:System.DateTimeOffset> 단일 생성자 <xref:System.DateTime> 매개 변수는 변환 하는 암시적 변환을 수행 하는 <xref:System.DateTime> 값을 <xref:System.DateTimeOffset> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-131">Calling the overload of the <xref:System.DateTimeOffset> constructor that has a single <xref:System.DateTime> parameter is equivalent to performing an implicit conversion of a <xref:System.DateTime> value to a <xref:System.DateTimeOffset> value.</span></span>

<span data-ttu-id="44686-132">만드는 두 번째 생성자는 <xref:System.DateTimeOffset> 에서 개체는 <xref:System.DateTime> 값에 두 개의 매개 변수:는 <xref:System.DateTime> 변환할 값 및 <xref:System.TimeSpan> 값 날짜 및 시간을 나타내는 UTC에서 오프셋 합니다.</span><span class="sxs-lookup"><span data-stu-id="44686-132">The second constructor that creates a <xref:System.DateTimeOffset> object from a <xref:System.DateTime> value has two parameters: the <xref:System.DateTime> value to convert, and a <xref:System.TimeSpan> value representing the date and time's offset from UTC.</span></span> <span data-ttu-id="44686-133">오프셋된 값이 일치 해야는 <xref:System.DateTime.Kind%2A> 생성자의 첫 번째 매개 변수 속성 또는 <xref:System.ArgumentException> throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44686-133">This offset value must correspond to the <xref:System.DateTime.Kind%2A> property of the constructor's first parameter or an <xref:System.ArgumentException> is thrown.</span></span> <span data-ttu-id="44686-134">경우는 <xref:System.DateTime.Kind%2A> 첫 번째 매개 변수 속성은 <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, 두 번째 매개 변수 값 이어야 합니다 <xref:System.TimeSpan.Zero?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="44686-134">If the <xref:System.DateTime.Kind%2A> property of the first parameter is <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, the value of the second parameter must be <xref:System.TimeSpan.Zero?displayProperty=nameWithType>.</span></span> <span data-ttu-id="44686-135">경우는 <xref:System.DateTime.Kind%2A> 첫 번째 매개 변수 속성은 <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, 두 번째 매개 변수 값에는 로컬 시스템의 표준 시간대 오프셋 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44686-135">If the <xref:System.DateTime.Kind%2A> property of the first parameter is <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, the value of the second parameter must be the offset of the local system's time zone.</span></span> <span data-ttu-id="44686-136">경우는 <xref:System.DateTime.Kind%2A> 첫 번째 매개 변수 속성은 <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, 오프셋 유효한 값이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44686-136">If the <xref:System.DateTime.Kind%2A> property of the first parameter is <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, the offset can be any valid value.</span></span> <span data-ttu-id="44686-137">다음 코드에서는이 생성자를 호출 변환할 <xref:System.DateTime> 를 <xref:System.DateTimeOffset> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-137">The following code illustrates calls to this constructor to convert <xref:System.DateTime> to <xref:System.DateTimeOffset> values.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a><span data-ttu-id="44686-138">암시적 형식 변환</span><span class="sxs-lookup"><span data-stu-id="44686-138">Implicit type conversion</span></span>

<span data-ttu-id="44686-139"><xref:System.DateTimeOffset> 형식이 암시적 형식 변환 지원:에서 <xref:System.DateTime> 값을 <xref:System.DateTimeOffset> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-139">The <xref:System.DateTimeOffset> type supports one implicit type conversion: from a <xref:System.DateTime> value to a <xref:System.DateTimeOffset> value.</span></span> <span data-ttu-id="44686-140">암시적 형식 변환은 명시적 캐스팅(C#의 경우) 또는 변환(Visual Basic의 경우)을 필요로 하지 않고 정보를 손실하지 않는 형식 간의 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-140">(An implicit type conversion is a conversion from one type to another that does not require an explicit cast (in C#) or conversion (in Visual Basic) and that does not lose information.</span></span> <span data-ttu-id="44686-141">이를 사용하면 다음과 같은 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44686-141">It makes code like the following possible.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

<span data-ttu-id="44686-142">결과의 오프셋 <xref:System.DateTimeOffset> 값에 따라 달라 집니다는 <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> 속성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-142">The offset of the resulting <xref:System.DateTimeOffset> value depends on the <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> property value.</span></span> <span data-ttu-id="44686-143">값이 <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, 오프셋 같게 설정 된 <xref:System.TimeSpan.Zero?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="44686-143">If its value is <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, the offset is set equal to <xref:System.TimeSpan.Zero?displayProperty=nameWithType>.</span></span> <span data-ttu-id="44686-144">값이 하나 <xref:System.DateTimeKind.Local?displayProperty=nameWithType> 또는 <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, 오프셋은 현지 표준 시간대의으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44686-144">If its value is either <xref:System.DateTimeKind.Local?displayProperty=nameWithType> or <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, the offset is set equal to that of the local time zone.</span></span>

## <a name="parsing-the-string-representation-of-a-date-and-time"></a><span data-ttu-id="44686-145">날짜 및 시간의 문자열 표현을 구문 분석</span><span class="sxs-lookup"><span data-stu-id="44686-145">Parsing the string representation of a date and time</span></span>

<span data-ttu-id="44686-146"><xref:System.DateTimeOffset> 형식은 지원 날짜의 문자열 표현으로 변환 하 여 시간을 사용할 수 있는 네 가지 메서드는 <xref:System.DateTimeOffset> 값:</span><span class="sxs-lookup"><span data-stu-id="44686-146">The <xref:System.DateTimeOffset> type supports four methods that allow you to convert the string representation of a date and time into a <xref:System.DateTimeOffset> value:</span></span>

* <span data-ttu-id="44686-147"><xref:System.DateTimeOffset.Parse%2A>는 데 필요한 시간 및 날짜의 문자열 표현으로 변환 하려고 하는 <xref:System.DateTimeOffset> 값 및 변환에 실패 하는 경우 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="44686-147"><xref:System.DateTimeOffset.Parse%2A>, which tries to convert the string representation of a date and time to a <xref:System.DateTimeOffset> value and throws an exception if the conversion fails.</span></span>

* <span data-ttu-id="44686-148"><xref:System.DateTimeOffset.TryParse%2A>날짜의 문자열 표현으로 변환 하는 데 필요한 시간 하려고 시도 하는 <xref:System.DateTimeOffset> 값과 반환 `false` 경우 변환이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="44686-148"><xref:System.DateTimeOffset.TryParse%2A>, which tries to convert the string representation of a date and time to a <xref:System.DateTimeOffset> value and returns `false` if the conversion fails.</span></span>

* <span data-ttu-id="44686-149"><xref:System.DateTimeOffset.ParseExact%2A>날짜 및 시간 지정 된 형식으로 문자열 표현으로 변환 하려고 하는 <xref:System.DateTimeOffset> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-149"><xref:System.DateTimeOffset.ParseExact%2A>, which tries to convert the string representation of a date and time in a specified format to a <xref:System.DateTimeOffset> value.</span></span> <span data-ttu-id="44686-150">변환이 실패하면 메서드는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="44686-150">The method throws an exception if the conversion fails.</span></span>

* <span data-ttu-id="44686-151"><xref:System.DateTimeOffset.TryParseExact%2A>날짜 및 시간 지정 된 형식으로 문자열 표현으로 변환 하려고 하는 <xref:System.DateTimeOffset> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-151"><xref:System.DateTimeOffset.TryParseExact%2A>, which tries to convert the string representation of a date and time in a specified format to a <xref:System.DateTimeOffset> value.</span></span> <span data-ttu-id="44686-152">변환에 실패하는 경우 메서드가 `false`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="44686-152">The method returns `false` if the conversion fails.</span></span>

<span data-ttu-id="44686-153">다음 예제에서는 인스턴스화할 이러한 4 개의 문자열 변환 메서드는 각각에 대 한 호출을 <xref:System.DateTimeOffset> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="44686-153">The following example illustrates calls to each of these four string conversion methods to instantiate a <xref:System.DateTimeOffset> value.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a><span data-ttu-id="44686-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44686-154">See also</span></span>

[<span data-ttu-id="44686-155">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="44686-155">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
