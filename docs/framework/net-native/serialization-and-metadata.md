---
title: "Serialization 및 메타데이터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e7216f14fb0b8da27b870fc8e66b24f6d87fcaad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="serialization-and-metadata"></a><span data-ttu-id="ca89b-102">Serialization 및 메타데이터</span><span class="sxs-lookup"><span data-stu-id="ca89b-102">Serialization and Metadata</span></span>
<span data-ttu-id="ca89b-103">앱이 개체를 serialize 및 deserialize하는 경우에는 런타임에 필요한 메타데이터가 제공되도록 런타임 지시문(.rd.xml) 파일에 항목을 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-103">If your app serializes and deserializes objects, you may need to add entries to your runtime directives (.rd.xml) file to ensure that the necessary metadata is present at run time.</span></span> <span data-ttu-id="ca89b-104">serializer에는 두 가지 범주가 있으며 각 범주는 런타임 지시문 파일에서 서로 다른 방식으로 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-104">There are two categories of serializers, and each requires different handling in your runtime directives file:</span></span>  
  
-   <span data-ttu-id="ca89b-105">리플렉션 기반 타사 serializer.</span><span class="sxs-lookup"><span data-stu-id="ca89b-105">Reflection-based third-party serializers.</span></span> <span data-ttu-id="ca89b-106">이러한 serializer의 경우 런타임 지시문 파일을 수정해야 합니다. 여기에 대해서는 다음 섹션에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-106">These require modifications to your runtime directives file, and are discussed in the next section.</span></span>  
  
-   <span data-ttu-id="ca89b-107">.NET Framework 클래스 라이브러리에 포함된 리플렉션을 기반으로 하지 않는 serializer.</span><span class="sxs-lookup"><span data-stu-id="ca89b-107">Non-reflection based serializers found in the .NET Framework class library.</span></span> <span data-ttu-id="ca89b-108">이러한 직렬 변환기의 경우 런타임 지시문 파일을 수정해야 할 수도 있습니다. 아래의 [Microsoft 직렬 변환기](#Microsoft) 섹션에서 여기에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-108">These may require modifications to your runtime directives file, and are discussed in the [Microsoft serializers](#Microsoft) section.</span></span>  
  
<a name="ThirdParty"></a>   
## <a name="third-party-serializers"></a><span data-ttu-id="ca89b-109">타사 serializer</span><span class="sxs-lookup"><span data-stu-id="ca89b-109">Third-party serializers</span></span>  
 <span data-ttu-id="ca89b-110">Newtonsoft.JSON을 비롯한 타사 serializer는 대개 리플렉션을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-110">Third-part serializers, including Newtonsoft.JSON, typically are reflection-based.</span></span> <span data-ttu-id="ca89b-111">serialize된 데이터의 BLOB(Binary Large Object)가 지정되면 데이터의 필드는 대상 형식의 필드를 이름으로 조회하여 구체적 형식에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-111">Given a binary large object (BLOB) of serialized data, the fields in the data are assigned to a concrete type by looking up the fields of the target type by name.</span></span> <span data-ttu-id="ca89b-112">이러한 라이브러리를 사용하는 경우 `List<Type>` 컬렉션에서 직렬화 또는 deserialize하려는 각 <xref:System.Type> 개체에 대해 최소한 [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-112">At a minimum, using these libraries causes [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exceptions for each <xref:System.Type> object that you try to serialize or deserialize in a `List<Type>` collection.</span></span>  
  
 <span data-ttu-id="ca89b-113">이러한 serializer용 메타데이터 누락으로 인해 발생하는 문제를 해결하는 가장 쉬운 방법은 serialization에 사용할 형식을 `App.Models`와 같은 네임스페이스 하나에 수집하고 해당 네임스페이스에 `Serialize` 메타데이터 지시문을 적용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-113">The easiest way to address issues caused by missing metadata for these serializers is to collect types that will be used in serialization under a single namespace (such as `App.Models`) and apply a `Serialize` metadata directive to it:</span></span>  
  
```xml  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 <span data-ttu-id="ca89b-114">이 예제에 사용된 구문에 대한 자세한 내용은 [\<Namespace> 요소](../../../docs/framework/net-native/namespace-element-net-native.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca89b-114">For information about the syntax used in the example, see [\<Namespace> Element](../../../docs/framework/net-native/namespace-element-net-native.md).</span></span>  
  
<a name="Microsoft"></a>   
## <a name="microsoft-serializers"></a><span data-ttu-id="ca89b-115">Microsoft serializer</span><span class="sxs-lookup"><span data-stu-id="ca89b-115">Microsoft serializers</span></span>  
 <span data-ttu-id="ca89b-116"><xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 및 <xref:System.Xml.Serialization.XmlSerializer> 클래스는 리플렉션을 사용하지는 않지만 serialize 또는 deserialize하려는 코드를 기반으로 코드는 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-116">Although the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes do not rely on reflection, they do require code to be generated based on the object to be serialized or deserialized.</span></span> <span data-ttu-id="ca89b-117">각 serializer의 오버로드된 생성자는 serialize 또는 deserialize할 형식을 지정하는 <xref:System.Type> 매개 변수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-117">The overloaded constructors for each serializer include a <xref:System.Type> parameter that specifies the type to be serialized or deserialized.</span></span> <span data-ttu-id="ca89b-118">코드에서 해당 형식을 지정하는 방법에 따라 수행해야 하는 작업이 정의됩니다. 여기에 대해서는 다음 두 섹션에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-118">How you specify that type in your code defines the action you must take, as discussed in the next two sections.</span></span>  
  
### <a name="typeof-used-in-the-constructor"></a><span data-ttu-id="ca89b-119">생성자 내부에서 사용되는 typeof</span><span class="sxs-lookup"><span data-stu-id="ca89b-119">typeof used in the constructor</span></span>  
 <span data-ttu-id="ca89b-120">이러한 serialization 클래스의 생성자를 호출하고 C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md) 키워드를 메서드 호출에 포함하는 경우에는 **추가 작업을 수행할 필요가 없습니다**.</span><span class="sxs-lookup"><span data-stu-id="ca89b-120">If you call a constructor of these serialization classes and include the C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md) keyword in the method call, **you do not have to do any additional work**.</span></span> <span data-ttu-id="ca89b-121">예를 들어 serialization 클래스 생성자에 대한 다음의 각 호출에서 `typeof` 키워드는 생성자에 전달되는 식의 일부로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-121">For example, in each of the following calls to a serialization class constructor, the `typeof` keyword is used as part of the expression passed to the constructor.</span></span>  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 <span data-ttu-id="ca89b-122">[!INCLUDE[net_native](../../../includes/net-native-md.md)] 컴파일러는 이 코드를 자동으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-122">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler will automatically handle this code.</span></span>  
  
### <a name="typeof-used-outside-the-constructor"></a><span data-ttu-id="ca89b-123">생성자 외부에서 사용되는 typeof</span><span class="sxs-lookup"><span data-stu-id="ca89b-123">typeof used outside the constructor</span></span>  
 <span data-ttu-id="ca89b-124">이러한 serialization 클래스의 생성자를 호출하고 생성자 <xref:System.Type> 매개 변수에 제공된 식 외부에서 C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md) 키워드를 사용하는 경우, 다음 코드에서처럼 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 컴파일러는 형식을 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-124">If you call a constructor of these serialization classes and use the C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md) keyword outside the expression supplied to the constructor’s <xref:System.Type> parameter, as in the following code, the [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler cannot resolve the type:</span></span>  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 <span data-ttu-id="ca89b-125">이 경우 다음과 같은 항목을 추가하여 런타임 지시문 파일에서 형식을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-125">In this case, you must specify the type in the runtime directives file by adding an entry like this:</span></span>  
  
```xml  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 <span data-ttu-id="ca89b-126">마찬가지로 다음 코드에서와 같이 <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType> 등의 생성자를 호출하고 serialize할 추가 <xref:System.Type> 개체 배열을 제공하는 경우 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 컴파일러는 해당 형식을 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-126">Similarly, if you call a constructor such as <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType> and provide an array of additional <xref:System.Type> objects to serialize, as in the following code, the [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler cannot resolve these types.</span></span>  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
 <span data-ttu-id="ca89b-127">따라서 각 형식에 대한 다음과 같은 항목을 런타임 지시문 파일에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca89b-127">You must add entries such as the following for each type to the runtime directives file:</span></span>  
  
```xml  
<Type Name="t" Browse="Required Public" />  
```  
  
 <span data-ttu-id="ca89b-128">이 예제에 사용된 구문에 대한 자세한 내용은 [\<Type> 요소](../../../docs/framework/net-native/type-element-net-native.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca89b-128">For information about the syntax used in the example, see [\<Type> Element](../../../docs/framework/net-native/type-element-net-native.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca89b-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca89b-129">See Also</span></span>  
 [<span data-ttu-id="ca89b-130">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="ca89b-130">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="ca89b-131">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="ca89b-131">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="ca89b-132">\<형식 > 요소</span><span class="sxs-lookup"><span data-stu-id="ca89b-132">\<Type> Element</span></span>](../../../docs/framework/net-native/type-element-net-native.md)  
 [<span data-ttu-id="ca89b-133">\<Namespace> 요소</span><span class="sxs-lookup"><span data-stu-id="ca89b-133">\<Namespace> Element</span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)
