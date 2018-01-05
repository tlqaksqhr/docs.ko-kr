---
title: "방법: 표준.NET 개체를 직렬화 가능 인지 확인"
description: "런타임 시.NET 표준 형식이 serialize 될 수 있는지 여부를 결정 하는 방법을 보여 줍니다."
ms.custom: 
ms.date: 10/20/2017
ms.prod: .net
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7c44e350ad4e561f03bf6c598172058a0a9ca41e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="5a0b9-103">방법: 표준.NET 개체를 직렬화 가능 인지 확인</span><span class="sxs-lookup"><span data-stu-id="5a0b9-103">How to: Determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="5a0b9-104">.NET 표준 형식 및 해당 버전의 표준에 맞는 특정.NET 구현에 제공 되어야 하는 멤버를 정의 하는 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="5a0b9-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="5a0b9-105">그러나.NET 표준을 정의 하지 않습니다는 형식이 직렬화 가능 인지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a0b9-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="5a0b9-106">.NET 표준 라이브러리에 정의 된 형식으로 표시 되지 않은 <xref:System.SerializableAttribute> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5a0b9-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="5a0b9-107">대신,.NET Framework 및.NET Core와 같은 특정.NET 구현이 특정 형식이 직렬화 가능 인지를 확인 하려면.</span><span class="sxs-lookup"><span data-stu-id="5a0b9-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span> 

<span data-ttu-id="5a0b9-108">사용자가 작성 한 라이브러리를 대상으로 하는.NET Standard, 하는 경우를 지 원하는.NET 표준.NET 구현 하 여 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a0b9-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="5a0b9-109">즉, 있는지 알 수는 없습니다 사전에 특정 형식이 직렬화 가능; 인지 만 인지 직렬화 가능 실행 시 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a0b9-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="5a0b9-110">개체의 값을 검색 하 여 런타임 시 직렬화 가능 인지를 확인할 수 있습니다는 <xref:System.Type.IsSerializable> 의 속성을 <xref:System.Type> 해당 개체의 형식을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5a0b9-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="5a0b9-111">다음 예제에는 하나의 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5a0b9-111">The following example provides one implementation.</span></span> <span data-ttu-id="5a0b9-112">정의 `IsSerializable(Object)` 확장 메서드를 나타내는 있는지 여부를 <xref:System.Object> 인스턴스를 serialize 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a0b9-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="5a0b9-113">모든 개체를 확인 하는지 여부를 것 수 직렬화 및 역직렬화 될 경우 현재.NET 구현에 다음 예제와 같이 메서드에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a0b9-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

# <a name="see-also"></a><span data-ttu-id="5a0b9-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a0b9-114">See also</span></span>

<span data-ttu-id="5a0b9-115">[이진 serialization](binary-serialization.md) </span><span class="sxs-lookup"><span data-stu-id="5a0b9-115">[Binary serialization](binary-serialization.md) </span></span>  
<span data-ttu-id="5a0b9-116"><xref:System.SerializableAttribute?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="5a0b9-116"><xref:System.SerializableAttribute?displayProperty=fullName></span></span>    
<xref:System.Type.IsSerializable?displayProperty=nameWithType>   
