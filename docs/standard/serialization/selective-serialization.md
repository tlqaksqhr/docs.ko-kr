---
title: 선택적 serialization
ms.date: 08/07/2017
dev_langs:
- CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
ms.openlocfilehash: 6a91501c4c3763250a64c9849694bc4e5fa4829f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581539"
---
# <a name="selective-serialization"></a><span data-ttu-id="eb371-102">선택적 serialization</span><span class="sxs-lookup"><span data-stu-id="eb371-102">Selective serialization</span></span>
<span data-ttu-id="eb371-103">클래스에는 흔히 직렬화하지 않아야 하는 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb371-103">A class often contains fields that shouldn't be serialized.</span></span> <span data-ttu-id="eb371-104">예를 들어 클래스가 멤버 변수에 스레드 ID를 저장하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="eb371-104">For example, assume a class stores a thread ID in a member variable.</span></span> <span data-ttu-id="eb371-105">클래스가 deserialize되면 클래스가 직렬화된 시점에 대한 ID가 저장된 스레드가 더 이상 실행 중이지 않을 수 있으므로 이 값을 직렬화하는 것은 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb371-105">When the class is deserialized, the thread stored the ID for when the class was serialized might no longer be running; so serializing this value doesn't make sense.</span></span> <span data-ttu-id="eb371-106">다음과 같이 멤버 변수를 [NonSerialized](xref:System.NonSerializedAttribute) 특성으로 표시하여 해당 변수가 직렬화되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb371-106">You can prevent member variables from being serialized by marking them with the [NonSerialized](xref:System.NonSerializedAttribute) attribute as follows.</span></span>  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

<span data-ttu-id="eb371-107">가능한 경우 보안에 민감한 데이터가 포함될 수 있는 개체는 serialize할 수 없게 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="eb371-107">If possible, make an object that could contain security-sensitive data nonserializable.</span></span> <span data-ttu-id="eb371-108">개체를 직렬화할 수 있어야 하는 경우에는 중요한 데이터가 저장되는 특정 필드에 `NonSerialized` 특성을 적용하세요.</span><span class="sxs-lookup"><span data-stu-id="eb371-108">If the object must be serialized, apply the `NonSerialized` attribute to specific fields that store sensitive data.</span></span> <span data-ttu-id="eb371-109">이러한 필드를 serialization에서 제외하지 않는 경우에는 저장되는 데이터가 직렬화 권한이 있는 모든 코드에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb371-109">If you don't exclude these fields from serialization, be aware that the data they store are exposed to any code that has permission to serialize.</span></span> <span data-ttu-id="eb371-110">보안 serialization 코드 작성에 대한 자세한 내용은 [보안 및 Serialization](../../../docs/framework/misc/security-and-serialization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb371-110">For more information about writing secure serialization code, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="eb371-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="eb371-111">See also</span></span>  
 [<span data-ttu-id="eb371-112">이진 serialization</span><span class="sxs-lookup"><span data-stu-id="eb371-112">Binary Serialization</span></span>](binary-serialization.md)  
 [<span data-ttu-id="eb371-113">XML 및 SOAP serialization</span><span class="sxs-lookup"><span data-stu-id="eb371-113">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)  
 [<span data-ttu-id="eb371-114">보안 및 Serialization</span><span class="sxs-lookup"><span data-stu-id="eb371-114">Security and Serialization</span></span>](../../../docs/framework/misc/security-and-serialization.md)