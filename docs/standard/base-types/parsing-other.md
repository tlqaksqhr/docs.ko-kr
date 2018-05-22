---
title: .NET에서 기타 문자열 구문 분석
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Char data type, parsing strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- parsing strings, other strings
- Boolean data type, parsing strings
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7becf993db866e24381fe9013c82d74dd91ee9a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="parsing-other-strings-in-net"></a><span data-ttu-id="0ff7d-102">.NET에서 기타 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="0ff7d-102">Parsing Other Strings in .NET</span></span>
<span data-ttu-id="0ff7d-103">숫자 및 <xref:System.DateTime> 문자열 외에도 <xref:System.Char>, <xref:System.Boolean> 및 <xref:System.Enum> 형식을 나타내는 문자열을 데이터 형식으로 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-103">In addition to numeric and <xref:System.DateTime> strings, you can also parse strings that represent the types <xref:System.Char>, <xref:System.Boolean>, and <xref:System.Enum> into data types.</span></span>  
  
## <a name="char"></a><span data-ttu-id="0ff7d-104">Char</span><span class="sxs-lookup"><span data-stu-id="0ff7d-104">Char</span></span>  
 <span data-ttu-id="0ff7d-105">**Char** 데이터 형식과 연결된 고정 구문 분석 메서드는 단일 문자를 포함하는 문자열을 해당 유니코드 값으로 변환하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-105">The static parse method associated with the **Char** data type is useful for converting a string that contains a single character into its Unicode value.</span></span> <span data-ttu-id="0ff7d-106">다음 코드 예제에서는 문자열을 유니코드 문자로 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-106">The following code example parses a string into a Unicode character.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a><span data-ttu-id="0ff7d-107">부울</span><span class="sxs-lookup"><span data-stu-id="0ff7d-107">Boolean</span></span>  
 <span data-ttu-id="0ff7d-108">**부울** 데이터 형식은 부울 값을 나타내는 문자열을 실제 **부울** 형식으로 변환하는 데 사용할 수 있는 **Parse** 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-108">The **Boolean** data type contains a **Parse** method that you can use to convert a string that represents a Boolean value into an actual **Boolean** type.</span></span> <span data-ttu-id="0ff7d-109">이 메서드는 대/소문자를 구분하지 않으며 "True" 또는 "False"를 포함하는 문자열을 성공적으로 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-109">This method is not case-sensitive and can successfully parse a string containing "True" or "False."</span></span> <span data-ttu-id="0ff7d-110">**부울** 형식과 연결된 **Parse** 메서드는 공백으로 둘러싸인 문자열도 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-110">The **Parse** method associated with the **Boolean** type can also parse strings that are surrounded by white spaces.</span></span> <span data-ttu-id="0ff7d-111">다른 문자열을 전달하면 <xref:System.FormatException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-111">If any other string is passed, a <xref:System.FormatException> is thrown.</span></span>  
  
 <span data-ttu-id="0ff7d-112">다음 코드 예제에서는 **Parse** 메서드를 사용하여 문자열을 부울 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-112">The following code example uses the **Parse** method to convert a string into a Boolean value.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a><span data-ttu-id="0ff7d-113">열거형</span><span class="sxs-lookup"><span data-stu-id="0ff7d-113">Enumeration</span></span>  
 <span data-ttu-id="0ff7d-114">고정 **Parse** 메서드를 사용하여 문자열 값에 대한 열거형 형식을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-114">You can use the static **Parse** method to initialize an enumeration type to the value of a string.</span></span> <span data-ttu-id="0ff7d-115">이 메서드는 구문 분석하는 열거형 형식, 구문 분석할 문자열 및 구문 분석이 대/소문자를 구분하는지 여부를 나타내는 선택적 부울 플래그를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-115">This method accepts the enumeration type you are parsing, the string to parse, and an optional Boolean flag indicating whether or not the parse is case-sensitive.</span></span> <span data-ttu-id="0ff7d-116">구문 분석하는 문자열은 쉼표로 구분된 여러 값을 포함할 수 있으며 앞이나 뒤에는 하나 이상의 빈 공간(공백이라고도 함)이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-116">The string you are parsing can contain several values separated by commas, which can be preceded or followed by one or more empty spaces (also called white spaces).</span></span> <span data-ttu-id="0ff7d-117">문자열에 여러 값이 포함된 경우 반환된 개체의 값은 비트 OR 연산과 함께 결합된 모든 지정된 값과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-117">When the string contains multiple values, the value of the returned object is the value of all specified values combined with a bitwise OR operation.</span></span>  
  
 <span data-ttu-id="0ff7d-118">다음 예제에서는 **Parse** 메서드를 사용하여 문자열 표현을 열거형 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-118">The following example uses the **Parse** method to convert a string representation into an enumeration value.</span></span> <span data-ttu-id="0ff7d-119"><xref:System.DayOfWeek> 열거형은 문자열에서 **목요일**로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff7d-119">The <xref:System.DayOfWeek> enumeration is initialized to **Thursday** from a string.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="0ff7d-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ff7d-120">See Also</span></span>  
 [<span data-ttu-id="0ff7d-121">Parsing Strings</span><span class="sxs-lookup"><span data-stu-id="0ff7d-121">Parsing Strings</span></span>](../../../docs/standard/base-types/parsing-strings.md)  
 [<span data-ttu-id="0ff7d-122">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="0ff7d-122">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 [<span data-ttu-id="0ff7d-123">.NET에서 형식 변환</span><span class="sxs-lookup"><span data-stu-id="0ff7d-123">Type Conversion in the .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)
