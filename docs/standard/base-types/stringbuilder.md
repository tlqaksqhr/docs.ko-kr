---
title: ".NET에서 StringBuilder 클래스 사용"
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
- cpp
helpviewer_keywords:
- Remove method
- strings [.NET Framework], capacities
- StringBuilder object
- Replace method
- AppendFormat method
- Append method
- Insert method
- strings [.NET Framework], StringBuilder object
ms.assetid: 5c14867c-9a99-45bc-ae7f-2686700d377a
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3a6c8f6dee9f2a1da6ed4a8219c1b4832464d9aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-stringbuilder-class-in-net"></a><span data-ttu-id="1888d-102">.NET에서 StringBuilder 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="1888d-102">Using the StringBuilder Class in .NET</span></span>
<span data-ttu-id="1888d-103"><xref:System.String> 개체는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-103">The <xref:System.String> object is immutable.</span></span> <span data-ttu-id="1888d-104">메서드 중 하나를 사용할 때마다는 <xref:System.String?displayProperty=nameWithType> 해당 새 개체에 대 한 공간이 새로 할당 해야 하는 메모리에를 새 string 개체를 만드는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-104">Every time you use one of the methods in the <xref:System.String?displayProperty=nameWithType> class, you create a new string object in memory, which requires a new allocation of space for that new object.</span></span> <span data-ttu-id="1888d-105">문자열에 반복적 수정 해야 하는 경우에는 오버 헤드를 새로 만들 연관 <xref:System.String> 개체 비용이 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-105">In situations where you need to perform repeated modifications to a string, the overhead associated with creating a new <xref:System.String> object can be costly.</span></span> <span data-ttu-id="1888d-106"><xref:System.Text.StringBuilder?displayProperty=nameWithType> 새 개체를 만들지 않고 문자열을 수정 하려는 경우에 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-106">The <xref:System.Text.StringBuilder?displayProperty=nameWithType> class can be used when you want to modify a string without creating a new object.</span></span> <span data-ttu-id="1888d-107">예를 들어,를 사용 하는 <xref:System.Text.StringBuilder> 클래스는 루프에서 많은 문자열을 연결할 때 성능을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-107">For example, using the <xref:System.Text.StringBuilder> class can boost performance when concatenating many strings together in a loop.</span></span>  
  
## <a name="importing-the-systemtext-namespace"></a><span data-ttu-id="1888d-108">System.Text 네임스페이스 가져오기</span><span class="sxs-lookup"><span data-stu-id="1888d-108">Importing the System.Text Namespace</span></span>  
 <span data-ttu-id="1888d-109"><xref:System.Text.StringBuilder> 클래스에서 발견 되는 <xref:System.Text> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-109">The <xref:System.Text.StringBuilder> class is found in the <xref:System.Text> namespace.</span></span>  <span data-ttu-id="1888d-110">코드에서 정규화 된 형식 이름을 제공할 필요가 없도록를 가져올 수 있습니다는 <xref:System.Text> 네임 스페이스:</span><span class="sxs-lookup"><span data-stu-id="1888d-110">To avoid having to provide a fully qualified type name in your code,  you can import the <xref:System.Text> namespace:</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#11)]
 [!code-csharp[Conceptual.StringBuilder#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#11)]
 [!code-vb[Conceptual.StringBuilder#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#11)]  
  
## <a name="instantiating-a-stringbuilder-object"></a><span data-ttu-id="1888d-111">StringBuilder 개체 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="1888d-111">Instantiating a StringBuilder Object</span></span>  
 <span data-ttu-id="1888d-112">새 인스턴스를 만들 수 있습니다는 <xref:System.Text.StringBuilder> 클래스에서는 다음 예제와 같이 변수 오버 로드 된 생성자 메서드 중 하나를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-112">You can create a new instance of the <xref:System.Text.StringBuilder> class by initializing your variable with one of the overloaded constructor methods, as illustrated in the following example.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#1)]
 [!code-csharp[Conceptual.StringBuilder#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#1)]
 [!code-vb[Conceptual.StringBuilder#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#1)]  
  
## <a name="setting-the-capacity-and-length"></a><span data-ttu-id="1888d-113">용량 및 길이 설정</span><span class="sxs-lookup"><span data-stu-id="1888d-113">Setting the Capacity and Length</span></span>  
 <span data-ttu-id="1888d-114">하지만 <xref:System.Text.StringBuilder> 를 캡슐화 하는 문자열의 문자 수를 확장할 수 있는 동적 개체는 저장할 수 있는 문자의 최대 수에 대 한 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-114">Although the <xref:System.Text.StringBuilder> is a dynamic object that allows you to expand the number of characters in the string that it encapsulates, you can specify a value for the maximum number of characters that it can hold.</span></span> <span data-ttu-id="1888d-115">이 값은 프로젝트의 용량 이라고 하며 문자열의 길이와 혼동 해서는 안 하는 현재 <xref:System.Text.StringBuilder> 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-115">This value is called the capacity of the object and should not be confused with the length of the string that the current <xref:System.Text.StringBuilder> holds.</span></span> <span data-ttu-id="1888d-116">예를 들어,의 새 인스턴스를 만들 수는 <xref:System.Text.StringBuilder> 5의 길이 "Hello" 문자열을 사용 하 여 클래스 개체의 25 최대 용량을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-116">For example, you might create a new instance of the <xref:System.Text.StringBuilder> class with the string "Hello", which has a length of 5, and you might specify that the object has a maximum capacity of 25.</span></span> <span data-ttu-id="1888d-117">수정 하는 경우는 <xref:System.Text.StringBuilder>, 할당 되지 않습니다 크기 자체에 대 한 용량에 도달할 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-117">When you modify the <xref:System.Text.StringBuilder>, it does not reallocate size for itself until the capacity is reached.</span></span> <span data-ttu-id="1888d-118">이 경우 새 공간이 자동으로 할당되고 용량이 두 배로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-118">When this occurs, the new space is allocated automatically and the capacity is doubled.</span></span> <span data-ttu-id="1888d-119">용량을 지정할 수는 <xref:System.Text.StringBuilder> 클래스 오버 로드 된 생성자 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-119">You can specify the capacity of the <xref:System.Text.StringBuilder> class using one of the overloaded constructors.</span></span> <span data-ttu-id="1888d-120">다음 예에서는 `MyStringBuilder` 개체를 최대 25개 공간으로 확장할 수 있도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-120">The following example specifies that the `MyStringBuilder` object can be expanded to a maximum of 25 spaces.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#2)]
 [!code-csharp[Conceptual.StringBuilder#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#2)]
 [!code-vb[Conceptual.StringBuilder#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#2)]  
  
 <span data-ttu-id="1888d-121">또한 읽기/쓰기를 사용할 수 있습니다 <xref:System.Text.StringBuilder.Capacity%2A> 속성을 개체의 최대 길이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-121">Additionally, you can use the read/write <xref:System.Text.StringBuilder.Capacity%2A> property to set the maximum length of your object.</span></span> <span data-ttu-id="1888d-122">다음 예에서는 **Capacity** 속성을 사용하여 최대 개체 길이를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-122">The following example uses the **Capacity** property to define the maximum object length.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#3)]
 [!code-csharp[Conceptual.StringBuilder#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#3)]
 [!code-vb[Conceptual.StringBuilder#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#3)]  
  
 <span data-ttu-id="1888d-123"><xref:System.Text.StringBuilder.EnsureCapacity%2A> 메서드를 사용 하 여 현재 용량을 확인할 수 **StringBuilder**합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-123">The <xref:System.Text.StringBuilder.EnsureCapacity%2A> method can be used to check the capacity of the current **StringBuilder**.</span></span> <span data-ttu-id="1888d-124">용량이 전달된 값보다 크면 변경되지 않고, 용량이 전달된 값보다 작으면 현재 용량이 전달된 값과 일치하도록 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-124">If the capacity is greater than the passed value, no change is made; however, if the capacity is smaller than the passed value, the current capacity is changed to match the passed value.</span></span>  
  
 <span data-ttu-id="1888d-125"><xref:System.Text.StringBuilder.Length%2A> 속성을 표시 하거나 설정도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-125">The <xref:System.Text.StringBuilder.Length%2A> property can also be viewed or set.</span></span> <span data-ttu-id="1888d-126">**Length** 속성을 **Capacity** 속성보다 큰 값으로 설정하면 **Capacity** 속성이 **Length** 속성과 동일한 값으로 자동으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-126">If you set the **Length** property to a value that is greater than the **Capacity** property, the **Capacity** property is automatically changed to the same value as the **Length** property.</span></span> <span data-ttu-id="1888d-127">**Length** 속성을 현재 **StringBuilder** 내의 문자열 길이보다 작은 값으로 설정하면 문자열이 단축됩니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-127">Setting the **Length** property to a value that is less than the length of the string within the current **StringBuilder** shortens the string.</span></span>  
  
## <a name="modifying-the-stringbuilder-string"></a><span data-ttu-id="1888d-128">StringBuilder 문자열 수정</span><span class="sxs-lookup"><span data-stu-id="1888d-128">Modifying the StringBuilder String</span></span>  
 <span data-ttu-id="1888d-129">다음 표에서는 **StringBuilder**의 내용을 수정하는 데 사용할 수 있는 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-129">The following table lists the methods you can use to modify the contents of a **StringBuilder**.</span></span>  
  
|<span data-ttu-id="1888d-130">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="1888d-130">Method name</span></span>|<span data-ttu-id="1888d-131">기능</span><span class="sxs-lookup"><span data-stu-id="1888d-131">Use</span></span>|  
|-----------------|---------|  
|<xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>|<span data-ttu-id="1888d-132">현재 **StringBuilder**의 끝에 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-132">Appends information to the end of the current **StringBuilder**.</span></span>|  
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>|<span data-ttu-id="1888d-133">문자열에 전달된 서식 지정자를 서식 있는 텍스트로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-133">Replaces a format specifier passed in a string with formatted text.</span></span>|  
|<xref:System.Text.StringBuilder.Insert%2A?displayProperty=nameWithType>|<span data-ttu-id="1888d-134">현재 **StringBuilder**의 지정된 인덱스에 문자열 또는 개체를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-134">Inserts a string or object into the specified index of the current **StringBuilder**.</span></span>|  
|<xref:System.Text.StringBuilder.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="1888d-135">현재 **StringBuilder**에서 지정된 수의 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-135">Removes a specified number of characters from the current **StringBuilder**.</span></span>|  
|<xref:System.Text.StringBuilder.Replace%2A?displayProperty=nameWithType>|<span data-ttu-id="1888d-136">지정된 인덱스에서 지정된 문자를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-136">Replaces a specified character at a specified index.</span></span>|  
  
### <a name="append"></a><span data-ttu-id="1888d-137">추가</span><span class="sxs-lookup"><span data-stu-id="1888d-137">Append</span></span>  
 <span data-ttu-id="1888d-138">**Append** 메서드를 사용 하 여 텍스트 또는 개체의 문자열 표현이 현재 문자열의 끝에 추가할 수 **StringBuilder**합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-138">The **Append** method can be used to add text or a string representation of an object to the end of a string represented by the current **StringBuilder**.</span></span> <span data-ttu-id="1888d-139">다음 예에서는 **StringBuilder**를 "Hello World"로 초기화한 다음 개체의 끝에 일부 텍스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-139">The following example initializes a **StringBuilder** to "Hello World" and then appends some text to the end of the object.</span></span> <span data-ttu-id="1888d-140">필요한 경우 공간이 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-140">Space is allocated automatically as needed.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#4)]
 [!code-csharp[Conceptual.StringBuilder#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#4)]
 [!code-vb[Conceptual.StringBuilder#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#4)]  
  
### <a name="appendformat"></a><span data-ttu-id="1888d-141">AppendFormat</span><span class="sxs-lookup"><span data-stu-id="1888d-141">AppendFormat</span></span>  
 <span data-ttu-id="1888d-142"><xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType> 의 끝에 텍스트를 추가 하는 메서드는 <xref:System.Text.StringBuilder> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-142">The <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType> method adds text to the end of the <xref:System.Text.StringBuilder> object.</span></span> <span data-ttu-id="1888d-143">복합 서식 지정 기능을 지원 (자세한 내용은 참조 [합성 서식 지정](../../../docs/standard/base-types/composite-formatting.md))를 호출 하 여는 <xref:System.IFormattable> 의 서식을 지정 하는 개체를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-143">It supports the composite formatting feature (for more information, see [Composite Formatting](../../../docs/standard/base-types/composite-formatting.md)) by calling the <xref:System.IFormattable> implementation of the object or objects to be formatted.</span></span> <span data-ttu-id="1888d-144">따라서 숫자, 날짜 및 시간, 열거형 값에 대한 표준 서식 문자열, 숫자, 날짜 및 시간 값에 대한 사용자 지정 서식 문자열, 사용자 지정 형식에 대해 정의된 서식 문자열을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-144">Therefore, it accepts the standard format strings for numeric, date and time, and enumeration values, the custom format strings for numeric and date and time values, and the format strings defined for custom types.</span></span> <span data-ttu-id="1888d-145">서식 지정에 대한 자세한 내용은 [서식 지정 형식](../../../docs/standard/base-types/formatting-types.md)을 참조하세요. 이 메서드를 사용 하 여 변수의 서식을 사용자 지정 하 고 해당 값을 추가 하는 <xref:System.Text.StringBuilder>합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-145">(For information about formatting, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).) You can use this method to customize the format of variables and append those values to a <xref:System.Text.StringBuilder>.</span></span> <span data-ttu-id="1888d-146">다음 예제에서는 <xref:System.Text.StringBuilder.AppendFormat%2A> 의 끝에 통화 값으로 서식이 지정 된 정수 값을 배치 하는 메서드는 <xref:System.Text.StringBuilder> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-146">The following example uses the <xref:System.Text.StringBuilder.AppendFormat%2A> method to place an integer value formatted as a currency value at the end of a <xref:System.Text.StringBuilder> object.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#5)]
 [!code-csharp[Conceptual.StringBuilder#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#5)]
 [!code-vb[Conceptual.StringBuilder#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#5)]  
  
### <a name="insert"></a><span data-ttu-id="1888d-147">Insert</span><span class="sxs-lookup"><span data-stu-id="1888d-147">Insert</span></span>  
 <span data-ttu-id="1888d-148"><xref:System.Text.StringBuilder.Insert%2A> 현재에서 지정 된 위치에 문자열 또는 개체를 추가 하는 메서드 <xref:System.Text.StringBuilder> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-148">The <xref:System.Text.StringBuilder.Insert%2A> method adds a string or object to a specified position in the current <xref:System.Text.StringBuilder> object.</span></span> <span data-ttu-id="1888d-149">다음 예제에서는이 메서드를 사용 하 여 단어의 6 번째 위치에 삽입 하는 <xref:System.Text.StringBuilder> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-149">The following example uses this method to insert a word into the sixth position of a <xref:System.Text.StringBuilder> object.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#6)]
 [!code-csharp[Conceptual.StringBuilder#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#6)]
 [!code-vb[Conceptual.StringBuilder#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#6)]  
  
### <a name="remove"></a><span data-ttu-id="1888d-150">제거</span><span class="sxs-lookup"><span data-stu-id="1888d-150">Remove</span></span>  
 <span data-ttu-id="1888d-151">사용할 수는 **제거** 현재에서 지정한 개수의 문자를 제거 하는 메서드 <xref:System.Text.StringBuilder> 개체, 지정 된 인덱스에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-151">You can use the **Remove** method to remove a specified number of characters from the current <xref:System.Text.StringBuilder> object, beginning at a specified zero-based index.</span></span> <span data-ttu-id="1888d-152">다음 예제에서는 **제거** 길이를 단축할 메서드는 <xref:System.Text.StringBuilder> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-152">The following example uses the **Remove** method to shorten a <xref:System.Text.StringBuilder> object.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#7)]
 [!code-csharp[Conceptual.StringBuilder#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#7)]
 [!code-vb[Conceptual.StringBuilder#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#7)]  
  
### <a name="replace"></a><span data-ttu-id="1888d-153">바꾸기</span><span class="sxs-lookup"><span data-stu-id="1888d-153">Replace</span></span>  
 <span data-ttu-id="1888d-154">**대체** 메서드 내에서 문자를 바꾸는 데 사용할 수는 <xref:System.Text.StringBuilder> 개체를 다른 문자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-154">The **Replace** method can be used to replace characters within the <xref:System.Text.StringBuilder> object with another specified character.</span></span> <span data-ttu-id="1888d-155">다음 예제에서는 **대체** 검색 하는 메서드는 <xref:System.Text.StringBuilder> 개체에서 느낌표 함수의 모든 인스턴스의 문자 (!) 및 물음표 문자 (?)으로 바꾸세요.</span><span class="sxs-lookup"><span data-stu-id="1888d-155">The following example uses the **Replace** method to search a <xref:System.Text.StringBuilder> object for all instances of the exclamation point character (!) and replace them with the question mark character (?).</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#8](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#8)]
 [!code-csharp[Conceptual.StringBuilder#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#8)]
 [!code-vb[Conceptual.StringBuilder#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#8)]  
  
## <a name="converting-a-stringbuilder-object-to-a-string"></a><span data-ttu-id="1888d-156">StringBuilder 개체를 문자열로 변환</span><span class="sxs-lookup"><span data-stu-id="1888d-156">Converting a StringBuilder Object to a String</span></span>  
 <span data-ttu-id="1888d-157">변환 해야 합니다는 <xref:System.Text.StringBuilder> 개체를 <xref:System.String> 이 나타내는 문자열을 전달할 수 전에 개체는 <xref:System.Text.StringBuilder> 개체 변수가 있는 메서드를 한 <xref:System.String> 매개 변수 또는 사용자 인터페이스에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-157">You must convert the <xref:System.Text.StringBuilder> object to a <xref:System.String> object before you can pass the string represented by the <xref:System.Text.StringBuilder> object to a method that has a <xref:System.String> parameter or display it in the user interface.</span></span> <span data-ttu-id="1888d-158">이 변환을 호출 하 여 수행 된 <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="1888d-158">You do this conversion by calling the <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1888d-159">다음 예제에서는 다양 한 <xref:System.Text.StringBuilder> 메서드 및 호출은 <xref:System.Text.StringBuilder.ToString?displayProperty=nameWithType> 메서드 문자열 표시를 합니다.</span><span class="sxs-lookup"><span data-stu-id="1888d-159">The following example calls a number of <xref:System.Text.StringBuilder> methods and then calls the <xref:System.Text.StringBuilder.ToString?displayProperty=nameWithType> method to display the string.</span></span>  
  
 [!code-csharp[Conceptual.StringBuilder#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/tostringexample1.cs#10)]
 [!code-vb[Conceptual.StringBuilder#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/tostringexample1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="1888d-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1888d-160">See Also</span></span>  
 <xref:System.Text.StringBuilder?displayProperty=nameWithType>  
 [<span data-ttu-id="1888d-161">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="1888d-161">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)  
 [<span data-ttu-id="1888d-162">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="1888d-162">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)
