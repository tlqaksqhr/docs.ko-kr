---
title: "트리밍 및.NET의 문자열에서 문자를 제거 합니다."
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
- strings [.NET Framework], removing characters
- Remove method
- TrimEnd method
- Trim method
- trimming characters
- TrimStart method
- removing characters
ms.assetid: ab248dab-70d4-4413-81c6-542d153fd195
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fde24a97234d275d3d599f13bfc4063af939507b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="trimming-and-removing-characters-from-strings-in-net"></a><span data-ttu-id="ba461-102">트리밍 및.NET의 문자열에서 문자를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-102">Trimming and Removing Characters from Strings in .NET</span></span>
<span data-ttu-id="ba461-103">문장을 개별 단어로 구문 분석할 경우 단어의 끝에 빈 공간(공백이라고도 함)이 있는 단어가 생길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-103">If you are parsing a sentence into individual words, you might end up with words that have blank spaces (also called white spaces) on either end of the word.</span></span> <span data-ttu-id="ba461-104">이 경우에 **System.String** 클래스에서 trim 메서드 중 하나를 사용하여 문자열에 지정된 위치에서 공백의 수나 다른 문자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-104">In this situation, you can use one of the trim methods in the **System.String** class to remove any number of spaces or other characters from a specified position in the string.</span></span> <span data-ttu-id="ba461-105">다음 테이블에서는 사용할 수 있는 trim 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-105">The following table describes the available trim methods.</span></span>  
  
|<span data-ttu-id="ba461-106">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="ba461-106">Method name</span></span>|<span data-ttu-id="ba461-107">기능</span><span class="sxs-lookup"><span data-stu-id="ba461-107">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Trim%2A?displayProperty=nameWithType>|<span data-ttu-id="ba461-108">문자열의 시작과 끝에서 문자 배열에 지정된 문자 또는 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-108">Removes white spaces or characters specified in an array of characters from the beginning and end of a string.</span></span>|  
|<xref:System.String.TrimEnd%2A?displayProperty=nameWithType>|<span data-ttu-id="ba461-109">문자열의 끝에서 문자 배열에 지정된 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-109">Removes characters specified in an array of characters from the end of a string.</span></span>|  
|<xref:System.String.TrimStart%2A?displayProperty=nameWithType>|<span data-ttu-id="ba461-110">문자열의 시작에서 문자 배열에 지정된 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-110">Removes characters specified in an array of characters from the beginning of a string.</span></span>|  
|<xref:System.String.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="ba461-111">문자열의 지정한 인덱스 위치에서 지정한 개수의 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-111">Removes a specified number of characters from a specified index position in a string.</span></span>|  
  
## <a name="trim"></a><span data-ttu-id="ba461-112">Trim</span><span class="sxs-lookup"><span data-stu-id="ba461-112">Trim</span></span>  
 <span data-ttu-id="ba461-113">사용 하 여 문자열의 양쪽 끝에서 공백의 쉽게 제거할 수는 <xref:System.String.Trim%2A?displayProperty=nameWithType> 메서드를 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-113">You can easily remove white spaces from both ends of a string by using the <xref:System.String.Trim%2A?displayProperty=nameWithType> method, as shown in the following example.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#17)]
 [!code-csharp[Conceptual.String.BasicOps#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#17)]
 [!code-vb[Conceptual.String.BasicOps#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#17)]  
  
 <span data-ttu-id="ba461-114">문자열의 시작과 끝의 문자 배열에서 지정하는 문자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-114">You can also remove characters that you specify in a character array from the beginning and end of a string.</span></span> <span data-ttu-id="ba461-115">다음 예제에서는 공백 문자, 마침표 또는 별표를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-115">The following example removes white-space characters, periods, and asterisks.</span></span>  
  
 [!code-csharp[Conceptual.String.BasicOps#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trim2.cs#22)]
 [!code-vb[Conceptual.String.BasicOps#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trim2.vb#22)]  
  
## <a name="trimend"></a><span data-ttu-id="ba461-116">TrimEnd</span><span class="sxs-lookup"><span data-stu-id="ba461-116">TrimEnd</span></span>  
 <span data-ttu-id="ba461-117">**String.TrimEnd** 메서드는 새 문자열 개체를 생성하여 문자열의 끝에서 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-117">The **String.TrimEnd** method removes characters from the end of a string, creating a new string object.</span></span> <span data-ttu-id="ba461-118">문자 배열을 이 메서드에 전달하여 제거할 문자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-118">An array of characters is passed to this method to specify the characters to be removed.</span></span> <span data-ttu-id="ba461-119">문자 배열에서 요소의 순서는 trim 작업에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-119">The order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="ba461-120">배열에 지정되지 않은 문자가 발견되면 trim이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-120">The trim stops when a character not specified in the array is found.</span></span>  
  
 <span data-ttu-id="ba461-121">사용 하 여 문자열의 마지막 문자를 제거 하는 다음 예제는 **TrimEnd** 메서드.</span><span class="sxs-lookup"><span data-stu-id="ba461-121">The following example removes the last letters of a string using the **TrimEnd** method.</span></span> <span data-ttu-id="ba461-122">이 예제에서 배열에 있는 문자의 순서를 설명하기 위해 바뀐 `'r'` 문자 및 `'W'` 문자의 위치는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-122">In this example, the position of the `'r'` character and the `'W'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span> <span data-ttu-id="ba461-123">이 코드는 `MyString`의 마지막 단어 및 첫 번째 단어의 일부를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-123">Notice that this code removes the last word of `MyString` plus part of the first.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#18)]
 [!code-csharp[Conceptual.String.BasicOps#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#18)]
 [!code-vb[Conceptual.String.BasicOps#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#18)]  
  
 <span data-ttu-id="ba461-124">이 코드는 콘솔에 `He`를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-124">This code displays `He` to the console.</span></span>  
  
 <span data-ttu-id="ba461-125">다음 예제에서는 **TrimEnd** 메서드를 사용하여 문자열의 마지막 단어를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-125">The following example removes the last word of a string using the **TrimEnd** method.</span></span> <span data-ttu-id="ba461-126">이 코드에서 쉼표는 `Hello` 단어 뒤에 오면 쉼표가 trim에 대한 문자의 배열에 지정되지 않기 때문에 해당 trim은 쉼표에서 끝나게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-126">In this code, a comma follows the word `Hello` and, because the comma is not specified in the array of characters to trim, the trim ends at the comma.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#19)]
 [!code-csharp[Conceptual.String.BasicOps#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#19)]
 [!code-vb[Conceptual.String.BasicOps#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#19)]  
  
 <span data-ttu-id="ba461-127">이 코드는 콘솔에 `Hello,`를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-127">This code displays `Hello,` to the console.</span></span>  
  
## <a name="trimstart"></a><span data-ttu-id="ba461-128">TrimStart</span><span class="sxs-lookup"><span data-stu-id="ba461-128">TrimStart</span></span>  
 <span data-ttu-id="ba461-129">**String.TrimStart** 메서드는 기존 문자열 개체의 시작 부분에서 문자를 제거하여 새 문자열을 만든다는 점을 제외하고 **String.TrimEnd** 메서드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-129">The **String.TrimStart** method is similar to the **String.TrimEnd** method except that it creates a new string by removing characters from the beginning of an existing string object.</span></span> <span data-ttu-id="ba461-130">문자 배열을 **TrimStart** 메서드에 전달하여 제거할 문자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-130">An array of characters is passed to the **TrimStart** method to specify the characters to be removed.</span></span> <span data-ttu-id="ba461-131">**TrimEnd** 메서드와 마찬가지로 문자 배열에서 요소의 순서는 트리밍 작업에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-131">As with the **TrimEnd** method, the order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="ba461-132">배열에 지정되지 않은 문자가 발견되면 trim이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-132">The trim stops when a character not specified in the array is found.</span></span>  
  
 <span data-ttu-id="ba461-133">다음 예제에서는 문자열의 첫 번째 단어를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-133">The following example removes the first word of a string.</span></span> <span data-ttu-id="ba461-134">이 예제에서 배열에 있는 문자의 순서를 설명하기 위해 바뀐 `'l'` 문자 및 `'H'` 문자의 위치는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-134">In this example, the position of the `'l'` character and the `'H'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#20)]
 [!code-csharp[Conceptual.String.BasicOps#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#20)]
 [!code-vb[Conceptual.String.BasicOps#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#20)]  
  
 <span data-ttu-id="ba461-135">이 코드는 콘솔에 `World!`를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-135">This code displays `World!` to the console.</span></span>  
  
## <a name="remove"></a><span data-ttu-id="ba461-136">제거</span><span class="sxs-lookup"><span data-stu-id="ba461-136">Remove</span></span>  
 <span data-ttu-id="ba461-137"><xref:System.String.Remove%2A?displayProperty=nameWithType> 메서드는 지정된 된 수의 기존 문자열의 지정된 된 위치에서 시작 하는 문자를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-137">The <xref:System.String.Remove%2A?displayProperty=nameWithType> method removes a specified number of characters that begin at a specified position in an existing string.</span></span> <span data-ttu-id="ba461-138">이 메서드에서는 0 기반 인덱스를 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-138">This method assumes a zero-based index.</span></span>  
  
 <span data-ttu-id="ba461-139">다음 예제에서는 문자열의 0 기반 인덱스 중 5번째 위치에서 시작하는 문자열에서 10개의 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-139">The following example removes ten characters from a string beginning at position five of a zero-based index of the string.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#21)]
 [!code-csharp[Conceptual.String.BasicOps#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#21)]
 [!code-vb[Conceptual.String.BasicOps#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#21)]  
  
 <span data-ttu-id="ba461-140">제거할 수도 있습니다는 지정 된 문자 또는 하위 문자열이 문자열에서 호출 하 여는 <xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=nameWithType> 메서드 및 빈 문자열을 지정 (<xref:System.String.Empty?displayProperty=nameWithType>)의 대체 값으로.</span><span class="sxs-lookup"><span data-stu-id="ba461-140">You can also remove a specified character or substring from a string by calling the <xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=nameWithType> method and specifying an empty string (<xref:System.String.Empty?displayProperty=nameWithType>) as the replacement.</span></span> <span data-ttu-id="ba461-141">다음 예제에서는 문자열에서 모든 쉼표를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ba461-141">The following example removes all commas from a string.</span></span>  
  
 [!code-csharp[Conceptual.String.BasicOps#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/replace1.cs#23)]
 [!code-vb[Conceptual.String.BasicOps#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/replace1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="ba461-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba461-142">See Also</span></span>  
 [<span data-ttu-id="ba461-143">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="ba461-143">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)
