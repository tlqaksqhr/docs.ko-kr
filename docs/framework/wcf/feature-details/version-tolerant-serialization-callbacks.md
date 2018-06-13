---
title: 버전 독립적 Serialization 콜백
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OnDeserializedAttribute [WCF]
- OnDeserializingAttribute [WCF]
- OnSerializingAttribute [WCF]
- serialization [WCF], setting default values
- OnSerializedAttribute [WCF]
ms.assetid: aa4a3a6f-05ec-4efd-bdbf-2181e13e6468
ms.openlocfilehash: 84e38451f10acc341642c0bf0923cc73b79d771f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497934"
---
# <a name="version-tolerant-serialization-callbacks"></a><span data-ttu-id="a6965-102">버전 독립적 Serialization 콜백</span><span class="sxs-lookup"><span data-stu-id="a6965-102">Version-Tolerant Serialization Callbacks</span></span>
<span data-ttu-id="a6965-103">데이터 계약 프로그래밍 모델에서는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 및 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> 클래스에서 지원하는 버전 독립적 serialization 콜백 메서드를 완전히 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a6965-103">The data contract programming model fully supports the version-tolerant serialization callback methods that the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> and <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> classes support.</span></span>  
  
## <a name="version-tolerant-attributes"></a><span data-ttu-id="a6965-104">버전 독립적 특성</span><span class="sxs-lookup"><span data-stu-id="a6965-104">Version-Tolerant Attributes</span></span>  
 <span data-ttu-id="a6965-105">4개의 콜백 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6965-105">There are four callback attributes.</span></span> <span data-ttu-id="a6965-106">각 특성은 다양한 시기에 serialization/deserialization 엔진에서 호출하는 메서드에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6965-106">Each attribute can be applied to a method that the serialization/deserialization engine calls at various times.</span></span> <span data-ttu-id="a6965-107">다음 표에서는 각 특성을 사용하는 시기에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a6965-107">The table below explains when to use each attribute.</span></span>  
  
|<span data-ttu-id="a6965-108">특성</span><span class="sxs-lookup"><span data-stu-id="a6965-108">Attribute</span></span>|<span data-ttu-id="a6965-109">해당 메서드를 호출하는 시기</span><span class="sxs-lookup"><span data-stu-id="a6965-109">When the corresponding method is called</span></span>|  
|---------------|---------------------------------------------|  
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|<span data-ttu-id="a6965-110">형식을 serialize하기 전에 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6965-110">Called before serializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|<span data-ttu-id="a6965-111">형식을 serialize한 후에 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6965-111">Called after serializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|<span data-ttu-id="a6965-112">형식을 deserialize하기 전에 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6965-112">Called before deserializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|<span data-ttu-id="a6965-113">형식을 deserialize한 후에 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6965-113">Called after deserializing the type.</span></span>|  
  
 <span data-ttu-id="a6965-114">메서드에서는 <xref:System.Runtime.Serialization.StreamingContext> 매개 변수를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6965-114">The methods must accept a <xref:System.Runtime.Serialization.StreamingContext> parameter.</span></span>  
  
 <span data-ttu-id="a6965-115">이 메서드는 주로 버전 지정 또는 초기화에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6965-115">These methods are primarily intended for use with versioning or initialization.</span></span> <span data-ttu-id="a6965-116">deserialization을 수행하는 동안에는 생성자가 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6965-116">During deserialization, no constructors are called.</span></span> <span data-ttu-id="a6965-117">따라서 들어오는 스트림에 이러한 멤버의 데이터가 없는 경우(예: 데이터가 일부 데이터 멤버가 없는 이전 버전의 형식으로부터 오는 경우) 데이터 멤버가 의도한 기본값으로 올바르게 초기화되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6965-117">Therefore, data members may not be correctly initialized (to intended default values) if the data for these members is missing in the incoming stream, for example, if the data comes from a previous version of a type that is missing some data members.</span></span> <span data-ttu-id="a6965-118">이 문제를 해결하려면 다음 예제처럼 <xref:System.Runtime.Serialization.OnDeserializingAttribute>로 표시된 콜백 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a6965-118">To correct this, use the callback method marked with the <xref:System.Runtime.Serialization.OnDeserializingAttribute>, as shown in the following example.</span></span>  
  
 <span data-ttu-id="a6965-119">위의 각 콜백 특성에서 형식 당 1개의 메서드만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6965-119">You can mark only one method per type with each of the preceding callback attributes.</span></span>  
  
### <a name="example"></a><span data-ttu-id="a6965-120">예제</span><span class="sxs-lookup"><span data-stu-id="a6965-120">Example</span></span>  
 [!code-csharp[C_DataContract#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#9)]
 [!code-vb[C_DataContract#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="a6965-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6965-121">See Also</span></span>  
 <xref:System.Runtime.Serialization.OnSerializingAttribute>  
 <xref:System.Runtime.Serialization.OnSerializedAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
 <xref:System.Runtime.Serialization.StreamingContext>  
 [<span data-ttu-id="a6965-122">버전 독립적 serialization</span><span class="sxs-lookup"><span data-stu-id="a6965-122">Version Tolerant Serialization</span></span>](../../../../docs/standard/serialization/version-tolerant-serialization.md)
