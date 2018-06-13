---
title: 특성 적용
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- attributes [.NET Framework], applying
ms.assetid: dd7604eb-9fa3-4b60-b2dd-b47739fa3148
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3a0151f6cc3ce25ca0c52a25be328ece8cb4434
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567369"
---
# <a name="applying-attributes"></a><span data-ttu-id="9aa14-102">특성 적용</span><span class="sxs-lookup"><span data-stu-id="9aa14-102">Applying Attributes</span></span>
<span data-ttu-id="9aa14-103">다음 프로세스를 사용하여 코드 요소에 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-103">Use the following process to apply an attribute to an element of your code.</span></span>  
  
1.  <span data-ttu-id="9aa14-104">새 특성을 정의하거나 .NET Framework에서 기존 특성의 네임스페이스를 가져와 이 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-104">Define a new attribute or use an existing attribute by importing its namespace from the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="9aa14-105">코드 요소 바로 앞에 특성을 배치하여 이 요소에 해당 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-105">Apply the attribute to the code element by placing it immediately before the element.</span></span>  
  
     <span data-ttu-id="9aa14-106">각 언어마다 고유한 특성 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-106">Each language has its own attribute syntax.</span></span> <span data-ttu-id="9aa14-107">C++ 및 C#의 경우 특성은 대괄호로 묶고, 공백으로 요소와 구분되며, 줄 바꿈 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-107">In C++ and C#, the attribute is surrounded by square brackets and separated from the element by white space, which can include a line break.</span></span> <span data-ttu-id="9aa14-108">Visual Basic의 경우 특성은 꺾쇠 괄호로 묶고, 같은 논리 줄에 있어야 합니다. 줄 바꿈이 필요하면 줄 연속 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-108">In Visual Basic, the attribute is surrounded by angle brackets and must be on the same logical line; the line continuation character can be used if a line break is desired.</span></span>
  
3.  <span data-ttu-id="9aa14-109">특성에 대한 위치 매개 변수와 명명된 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-109">Specify positional parameters and named parameters for the attribute.</span></span>  
  
     <span data-ttu-id="9aa14-110">위치 매개 변수는 필수 요소로서 명명된 매개 변수 앞에 와야 하며, 특성의 생성자 중 하나의 매개 변수에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-110">Positional parameters are required and must come before any named parameters; they correspond to the parameters of one of the attribute's constructors.</span></span> <span data-ttu-id="9aa14-111">명명된 매개 변수는 선택적 요소이며, 특성의 읽기/쓰기 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-111">Named parameters are optional and correspond to read/write properties of the attribute.</span></span> <span data-ttu-id="9aa14-112">C++ 및 C#의 경우 각 선택적 매개 변수에 `name`=`value`를 지정합니다. 여기서 `name`은 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-112">In C++, and C#, specify `name`=`value` for each optional parameter, where `name` is the name of the property.</span></span> <span data-ttu-id="9aa14-113">Visual Basic의 경우 `name`:=`value`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-113">In Visual Basic, specify `name`:=`value`.</span></span>  
  
 <span data-ttu-id="9aa14-114">특성은 코드를 컴파일할 때 메타데이터로 내보내지며, 공용 언어 런타임과 사용자 지정 도구 또는 응용 프로그램에서 런타임 리플렉션 서비스를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-114">The attribute is emitted into metadata when you compile your code and is available to the common language runtime and any custom tool or application through the runtime reflection services.</span></span>  
  
 <span data-ttu-id="9aa14-115">모든 특성 이름은 규칙에 따라 Attribute로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-115">By convention, all attribute names end with Attribute.</span></span> <span data-ttu-id="9aa14-116">하지만 런타임을 목적으로 하는 일부 언어(예: Visual Basic 및 C#)에서는 특성의 전체 이름을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-116">However, several languages that target the runtime, such as Visual Basic and C#, do not require you to specify the full name of an attribute.</span></span> <span data-ttu-id="9aa14-117">예를 들어 <xref:System.ObsoleteAttribute?displayProperty=nameWithType>를 초기화하려는 경우 **Obsolete**로만 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-117">For example, if you want to initialize <xref:System.ObsoleteAttribute?displayProperty=nameWithType>, you only need to reference it as **Obsolete**.</span></span>  
  
## <a name="applying-an-attribute-to-a-method"></a><span data-ttu-id="9aa14-118">메서드에 특성 적용</span><span class="sxs-lookup"><span data-stu-id="9aa14-118">Applying an Attribute to a Method</span></span>  
 <span data-ttu-id="9aa14-119">다음 코드 예제에서는 코드를 오래된 것으로 표시하는 **System.ObsoleteAttribute**를 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-119">The following code example shows how to declare **System.ObsoleteAttribute**, which marks code as obsolete.</span></span> <span data-ttu-id="9aa14-120">`"Will be removed in next version"` 문자열이 특성에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-120">The string `"Will be removed in next version"` is passed to the attribute.</span></span> <span data-ttu-id="9aa14-121">이 특성이 설명하는 코드가 호출되면 이 특성으로 인해 전달된 문자열을 표시하는 컴파일러 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-121">This attribute causes a compiler warning that displays the passed string when code that the attribute describes is called.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#3)]
 [!code-csharp[Conceptual.Attributes.Usage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#3)]
 [!code-vb[Conceptual.Attributes.Usage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#3)]  
  
## <a name="applying-attributes-at-the-assembly-level"></a><span data-ttu-id="9aa14-122">어셈블리 수준에서 특성 적용</span><span class="sxs-lookup"><span data-stu-id="9aa14-122">Applying Attributes at the Assembly Level</span></span>  
 <span data-ttu-id="9aa14-123">어셈블리 수준에서 특성을 적용하려면 **assembly**(Visual Basic에서는 `Assembly`) 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-123">If you want to apply an attribute at the assembly level, use the **assembly** (`Assembly` in Visual Basic) keyword.</span></span> <span data-ttu-id="9aa14-124">다음 코드에서는 어셈블리 수준에서 적용된 **AssemblyTitleAttribute**를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-124">The following code shows the **AssemblyTitleAttribute** applied at the assembly level.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#2)]
 [!code-csharp[Conceptual.Attributes.Usage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#2)]
 [!code-vb[Conceptual.Attributes.Usage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#2)]  
  
 <span data-ttu-id="9aa14-125">이 특성을 적용하면 `"My Assembly"` 문자열이 해당 파일의 메타데이터 부분에 있는 어셈블리 매니페스트에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-125">When this attribute is applied, the string `"My Assembly"` is placed in the assembly manifest in the metadata portion of the file.</span></span> <span data-ttu-id="9aa14-126">[Ildasm.exe(MSIL 디스어셈블러)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하거나 특성을 검색하는 사용자 지정 프로그램을 만들어 이 특성을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa14-126">You can view the attribute either by using the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by creating a custom program to retrieve the attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aa14-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9aa14-127">See Also</span></span>  
 [<span data-ttu-id="9aa14-128">특성</span><span class="sxs-lookup"><span data-stu-id="9aa14-128">Attributes</span></span>](../../../docs/standard/attributes/index.md)  
 [<span data-ttu-id="9aa14-129">특성에 저장된 정보 검색</span><span class="sxs-lookup"><span data-stu-id="9aa14-129">Retrieving Information Stored in Attributes</span></span>](../../../docs/standard/attributes/retrieving-information-stored-in-attributes.md)  
 [<span data-ttu-id="9aa14-130">개념</span><span class="sxs-lookup"><span data-stu-id="9aa14-130">Concepts</span></span>](/cpp/windows/attributed-programming-concepts)  
 [<span data-ttu-id="9aa14-131">특성</span><span class="sxs-lookup"><span data-stu-id="9aa14-131">Attributes</span></span>](https://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)
