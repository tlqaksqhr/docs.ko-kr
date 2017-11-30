---
title: "방법: 날짜 및 시간 값 라운드트립"
ms.custom: 
ms.date: 03/30/2017
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
- round-trip date and time values
- dates [.NET Framework], round-trip values
- time zones [.NET Framework], round-trip date and time values
- time [.NET Framework], round-trip values
- formatting strings [.NET Framework], round-trip values
ms.assetid: b609b277-edc6-4c74-b03e-ea73324ecbdb
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 515a29e279cfa8fc100e0612fc19df7abc6a3b36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-round-trip-date-and-time-values"></a><span data-ttu-id="486e9-102">방법: 날짜 및 시간 값 라운드트립</span><span class="sxs-lookup"><span data-stu-id="486e9-102">How to: Round-trip Date and Time Values</span></span>
<span data-ttu-id="486e9-103">많은 응용 프로그램에서 날짜 및 시간 값은 단일 시점을 명확하게 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-103">In many applications, a date and time value is intended to unambiguously identify a single point in time.</span></span> <span data-ttu-id="486e9-104">이 항목에서는 저장 하 고 복원 하는 방법을 보여 줍니다.는 <xref:System.DateTime> 값은 <xref:System.DateTimeOffset> 값 및 시간을 사용 하 여 날짜 및 시간 값을 표준 시간대 정보와 하 여 저장된 된 값과 같은 시간을 식별 하는 복원 된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-104">This topic shows how to save and restore a <xref:System.DateTime> value, a <xref:System.DateTimeOffset> value, and a date and time value with time zone information so that the restored value identifies the same time as the saved value.</span></span>  
  
### <a name="to-round-trip-a-datetime-value"></a><span data-ttu-id="486e9-105">DateTime 값을 라운드트립하려면</span><span class="sxs-lookup"><span data-stu-id="486e9-105">To round-trip a DateTime value</span></span>  
  
1.  <span data-ttu-id="486e9-106">변환에서 <xref:System.DateTime> 값을 호출 하 여 해당 문자열 표현에서 <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> "o" 서식 지정자를 사용 하 여 메서드.</span><span class="sxs-lookup"><span data-stu-id="486e9-106">Convert the <xref:System.DateTime> value to its string representation by calling the <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>  
  
2.  <span data-ttu-id="486e9-107">문자열 표현을 저장는 <xref:System.DateTime> 파일에 값 또는 프로세스, 응용 프로그램 도메인 또는 컴퓨터 경계 너머로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-107">Save the string representation of the <xref:System.DateTime> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>  
  
3.  <span data-ttu-id="486e9-108">나타내는 문자열을 검색 된 <xref:System.DateTime> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-108">Retrieve the string that represents the <xref:System.DateTime> value.</span></span>  
  
4.  <span data-ttu-id="486e9-109">호출 된 <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> 메서드와 패스 <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> 의 값으로는 `styles` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-109">Call the <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>  
  
 <span data-ttu-id="486e9-110">다음 예제에서는 라운드트립 하는 방법을 <xref:System.DateTime> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-110">The following example illustrates how to round-trip a <xref:System.DateTime> value.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
 [!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]  
  
 <span data-ttu-id="486e9-111">때 라운드트립은 <xref:System.DateTime> 값,이 기술을 현지 및 범용 모든 시간에 대 한 시간 성공적으로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-111">When round-tripping a <xref:System.DateTime> value, this technique successfully preserves the time for all local and universal times.</span></span> <span data-ttu-id="486e9-112">예를 들어 로컬 <xref:System.DateTime> 값이은 미국 영어 시스템에 저장 됩니다. 태평양 표준 시간대는 미국에 있는 시스템에서 복원됩니다. 중앙 표준 시간대인 복원된 날짜 및 시간은 원래 시간보다 2시간이 늦어지며 이것은 두 표준 시간대 사이의 시간 차이를 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-112">For example, if a local <xref:System.DateTime> value is saved on a system in the U.S. Pacific Standard Time zone and is restored on a system in the U.S. Central Standard Time zone, the restored date and time will be two hours later than the original time, which reflects the time difference between the two time zones.</span></span> <span data-ttu-id="486e9-113">그러나 이 기술은 지정되지 않은 시간에 대해 반드시 정확하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-113">However, this technique is not necessarily accurate for unspecified times.</span></span> <span data-ttu-id="486e9-114">모든 <xref:System.DateTime> 값을 갖는 <xref:System.DateTime.Kind%2A> 속성은 <xref:System.DateTimeKind.Unspecified> 는 현지 시간으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-114">All <xref:System.DateTime> values whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Unspecified> are treated as if they are local times.</span></span> <span data-ttu-id="486e9-115">이 경우, 아닌 경우는 <xref:System.DateTime> 성공적으로 올바른 시점 시간으로 식별 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-115">If this is not the case, the <xref:System.DateTime> will not successfully identify the correct point in time.</span></span> <span data-ttu-id="486e9-116">이 제한에 대한 해결책은 저장 및 복원 작업의 표준 시간대와 날짜 및 시간 값을 밀접하게 연결하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-116">The workaround for this limitation is to tightly couple a date and time value with its time zone for the save and restore operation.</span></span>  
  
### <a name="to-round-trip-a-datetimeoffset-value"></a><span data-ttu-id="486e9-117">DateTimeOffset 값을 라운드트립하려면</span><span class="sxs-lookup"><span data-stu-id="486e9-117">To round-trip a DateTimeOffset value</span></span>  
  
1.  <span data-ttu-id="486e9-118">변환에서 <xref:System.DateTimeOffset> 값을 호출 하 여 해당 문자열 표현에서 <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> "o" 서식 지정자를 사용 하 여 메서드.</span><span class="sxs-lookup"><span data-stu-id="486e9-118">Convert the <xref:System.DateTimeOffset> value to its string representation by calling the <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>  
  
2.  <span data-ttu-id="486e9-119">문자열 표현을 저장는 <xref:System.DateTimeOffset> 파일에 값 또는 프로세스, 응용 프로그램 도메인 또는 컴퓨터 경계 너머로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-119">Save the string representation of the <xref:System.DateTimeOffset> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>  
  
3.  <span data-ttu-id="486e9-120">나타내는 문자열을 검색 된 <xref:System.DateTimeOffset> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-120">Retrieve the string that represents the <xref:System.DateTimeOffset> value.</span></span>  
  
4.  <span data-ttu-id="486e9-121">호출 된 <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> 메서드와 패스 <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> 의 값으로는 `styles` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-121">Call the <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>  
  
 <span data-ttu-id="486e9-122">다음 예제에서는 라운드트립 하는 방법을 <xref:System.DateTimeOffset> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-122">The following example illustrates how to round-trip a <xref:System.DateTimeOffset> value.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
 [!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]  
  
 <span data-ttu-id="486e9-123">이 기술은 항상 명확 하 게 식별 하는 <xref:System.DateTimeOffset> 단일 지정 시간으로 값입니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-123">This technique always unambiguously identifies a <xref:System.DateTimeOffset> value as a single point in time.</span></span> <span data-ttu-id="486e9-124">값 다음 변환 될 수 utc (협정 세계시)로 호출 하 여는 <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> 호출 하 여 메서드 또는 것을 특정 표준 시간대의 시간으로 변환 수는 <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> 또는 <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="486e9-124">The value can then be converted to Coordinated Universal Time (UTC) by calling the <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> method, or it can be converted to the time in a particular time zone by calling the <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> or <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="486e9-125">이 방법의 주요 제한 사항은 해당 날짜 및 시간 산술 연산을 수행 하는 경우는 <xref:System.DateTimeOffset> 특정 표준 시간대의 시간을 나타내는 값 해당 표준 시간대에 대 한 정확한 결과 생성 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-125">The major limitation of this technique is that date and time arithmetic, when performed on a <xref:System.DateTimeOffset> value that represents the time in a particular time zone, may not produce accurate results for that time zone.</span></span> <span data-ttu-id="486e9-126">즉 때는 <xref:System.DateTimeOffset> 값 인스턴스화될, 표준 시간대에서 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-126">This is because when a <xref:System.DateTimeOffset> value is instantiated, it is disassociated from its time zone.</span></span> <span data-ttu-id="486e9-127">따라서 날짜 및 시간 계산을 수행할 경우에 해당 표준 시간대의 조정 규칙은 더 이상 적용될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-127">Therefore, that time zone's adjustment rules can no longer be applied when you perform date and time calculations.</span></span> <span data-ttu-id="486e9-128">날짜 및 시간 값과 동반되는 표준 시간대를 포함하는 사용자 지정 형식을 정의하여 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-128">You can work around this problem by defining a custom type that includes both a date and time value and its accompanying time zone.</span></span>  
  
### <a name="to-round-trip-a-date-and-time-value-with-its-time-zone"></a><span data-ttu-id="486e9-129">에 해당 표준 시간대를 사용 하 여 날짜 및 시간 값 라운드트립</span><span class="sxs-lookup"><span data-stu-id="486e9-129">To round-trip a date and time value with its time zone</span></span>  
  
1.  <span data-ttu-id="486e9-130">클래스 또는 구조에 두 필드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-130">Define a class or a structure with two fields.</span></span> <span data-ttu-id="486e9-131">첫 번째 필드는 한 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 개체 및 두 번째는는 <xref:System.TimeZoneInfo> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-131">The first field is either a <xref:System.DateTime> or a <xref:System.DateTimeOffset> object, and the second is a <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="486e9-132">다음 예제에서는 이러한 형식의 단순 버전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-132">The following example is a simple version of such a type.</span></span>  
  
     [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
     [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]  
  
2.  <span data-ttu-id="486e9-133">고 클래스는 <xref:System.SerializableAttribute> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-133">Mark the class with the <xref:System.SerializableAttribute> attribute.</span></span>  
  
3.  <span data-ttu-id="486e9-134">사용 하 여 개체를 직렬화는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="486e9-134">Serialize the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> method.</span></span>  
  
4.  <span data-ttu-id="486e9-135">사용 하 여 개체 복원의 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="486e9-135">Restore the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> method.</span></span>  
  
5.  <span data-ttu-id="486e9-136">캐스팅 (C#) 하거나 변환 (Visual Basic)의 deserialize 된 개체는 적절 한 형식의 개체 합니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-136">Cast (in C#) or convert (in Visual Basic) the deserialized object to an object of the appropriate type.</span></span>  
  
 <span data-ttu-id="486e9-137">다음 예제에서는 어떻게 날짜 및 시간, 표준 시간대 정보 저장 라운드트립 개체를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-137">The following example illustrates how to round-trip an object that stores both date and time and time zone information.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
 [!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]  
  
 <span data-ttu-id="486e9-138">이 방법 항상 명확 하 게 반영는 올바른 둘 다를 저장 하 고 복원한 후 제공 되는 시간 결합 된 날짜 및 시간과 표준 시간대 개체의 구현와 동기화 날짜 값을 허용 하지 않습니다는 표준 시간대 값입니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-138">This technique should always unambiguously reflect the correct point of time both before and after it is saved and restored, provided that the implementation of the combined date and time and time zone object does not allow the date value to become out of sync with the time zone value.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="486e9-139">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="486e9-139">Compiling the Code</span></span>  
 <span data-ttu-id="486e9-140">이러한 예제에는 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-140">These examples require:</span></span>  
  
-   <span data-ttu-id="486e9-141">다음 네임 스페이스는 C#으로 가져올 수 `using` 문 또는 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="486e9-141">That the following namespaces be imported with C# `using` statements or [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` statements:</span></span>  
  
    -   <span data-ttu-id="486e9-142"><xref:System>(C#에 해당)입니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-142"><xref:System> (C# only).</span></span>  
  
    -   <span data-ttu-id="486e9-143"><xref:System.Globalization?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="486e9-143"><xref:System.Globalization?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="486e9-144"><xref:System.IO?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="486e9-144"><xref:System.IO?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="486e9-145"><xref:System.Runtime.Serialization?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="486e9-145"><xref:System.Runtime.Serialization?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="486e9-146"><xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="486e9-146"><xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="486e9-147">System.Core.dll에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="486e9-147">A reference to System.Core.dll.</span></span>  
  
-   <span data-ttu-id="486e9-148">이외의 각 코드 예제는 `DateInTimeZone` 클래스, 클래스 또는 Visual Basic 모듈에 포함 된, 메서드에 래핑되어야 하 고 해야에서 호출 된 `Main` 메서드.</span><span class="sxs-lookup"><span data-stu-id="486e9-148">Each code example, other than the `DateInTimeZone` class, should be included in a class or Visual Basic module, wrapped in methods, and called from the `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="486e9-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="486e9-149">See Also</span></span>  
 [<span data-ttu-id="486e9-150">서식 지정 작업 수행</span><span class="sxs-lookup"><span data-stu-id="486e9-150">Performing Formatting Operations</span></span>](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [<span data-ttu-id="486e9-151">DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo 중 선택</span><span class="sxs-lookup"><span data-stu-id="486e9-151">Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo</span></span>](../../../docs/standard/datetime/choosing-between-datetime.md)  
 [<span data-ttu-id="486e9-152">Standard Date and Time Format Strings</span><span class="sxs-lookup"><span data-stu-id="486e9-152">Standard Date and Time Format Strings</span></span>](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
