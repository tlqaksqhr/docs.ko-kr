---
title: "리플렉션(C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 68a586fd8a8a8fbe6e351efa3e51c5ba1d2ff4d7
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="reflection-c"></a><span data-ttu-id="833cd-102">리플렉션(C#)</span><span class="sxs-lookup"><span data-stu-id="833cd-102">Reflection (C#)</span></span>
<span data-ttu-id="833cd-103">리플렉션은 어셈블리, 모듈 및 형식을 설명하는 개체(<xref:System.Type> 형식)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="833cd-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="833cd-104">리플렉션을 사용하면 동적으로 형식 인스턴스를 만들거나, 형식을 기존 개체에 바인딩하거나, 기존 개체에서 형식을 가져와 해당 메서드를 호출하거나, 필드 및 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="833cd-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="833cd-105">코드에서 특성을 사용하는 경우 리플렉션은 특성에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="833cd-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="833cd-106">자세한 내용은 [특성](../../../../docs/standard/attributes/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="833cd-106">For more information, see [Attributes](../../../../docs/standard/attributes/index.md).</span></span>  
  
 <span data-ttu-id="833cd-107">다음은 정적 메서드 `GetType`(`Object` 기본 클래스의 모든 형식에 상속됨)을 사용하여 변수 형식을 가져오는 간단한 리플렉션 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="833cd-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```csharp  
// Using GetType to obtain type information:  
int i = 42;  
System.Type type = i.GetType();  
System.Console.WriteLine(type);  
```  
  
 <span data-ttu-id="833cd-108">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="833cd-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="833cd-109">다음 예제에서는 리플렉션을 사용하여 로드된 어셈블리의 전체 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="833cd-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```csharp  
// Using Reflection to get information from an Assembly:  
System.Reflection.Assembly info = typeof(System.Int32).Assembly;  
System.Console.WriteLine(info);  
```  
  
 <span data-ttu-id="833cd-110">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="833cd-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
> [!NOTE]
>  <span data-ttu-id="833cd-111">C# 키워드 `protected` 및 `internal`은 IL에서 아무런 의미가 없으며 리플렉션 API에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="833cd-111">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="833cd-112">IL의 해당 용어는 *Family* 및 *Assembly*입니다.</span><span class="sxs-lookup"><span data-stu-id="833cd-112">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="833cd-113">리플렉션을 사용하는 `internal` 메서드를 식별하려면 <xref:System.Reflection.MethodBase.IsAssembly%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="833cd-113">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="833cd-114">`protected internal` 메서드를 식별하려면 <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="833cd-114">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>  
  
## <a name="reflection-overview"></a><span data-ttu-id="833cd-115">리플렉션 개요</span><span class="sxs-lookup"><span data-stu-id="833cd-115">Reflection Overview</span></span>  
 <span data-ttu-id="833cd-116">리플렉션은 다음과 같은 상황에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="833cd-116">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="833cd-117">프로그램 메타데이터의 특성에 액세스해야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="833cd-117">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="833cd-118">자세한 내용은 [특성에 저장된 정보 검색](../../../standard/attributes/retrieving-information-stored-in-attributes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="833cd-118">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>  
  
-   <span data-ttu-id="833cd-119">어셈블리에서 형식을 검사하고 인스턴스화하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="833cd-119">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="833cd-120">런타임에 새 형식을 빌드하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="833cd-120">For building new types at runtime.</span></span> <span data-ttu-id="833cd-121"><xref:System.Reflection.Emit>의 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="833cd-121">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="833cd-122">런타임에 바인딩을 수행하고 런타임에 생성된 형식의 메서드에 액세스하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="833cd-122">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="833cd-123">[동적으로 형식 로드 및 사용](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="833cd-123">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="833cd-124">관련 단원</span><span class="sxs-lookup"><span data-stu-id="833cd-124">Related Sections</span></span>  
 <span data-ttu-id="833cd-125">추가 정보</span><span class="sxs-lookup"><span data-stu-id="833cd-125">For more information:</span></span>  
  
-   [<span data-ttu-id="833cd-126">리플렉션</span><span class="sxs-lookup"><span data-stu-id="833cd-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
  
-   [<span data-ttu-id="833cd-127">형식 정보 보기</span><span class="sxs-lookup"><span data-stu-id="833cd-127">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
-   [<span data-ttu-id="833cd-128">리플렉션 및 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="833cd-128">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
-   <xref:System.Reflection.Emit>  
  
-   [<span data-ttu-id="833cd-129">특성에 저장된 정보 검색</span><span class="sxs-lookup"><span data-stu-id="833cd-129">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a><span data-ttu-id="833cd-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="833cd-130">See Also</span></span>  
 [<span data-ttu-id="833cd-131">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="833cd-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="833cd-132">공용 언어 런타임의 어셈블리</span><span class="sxs-lookup"><span data-stu-id="833cd-132">Assemblies in the Common Language Runtime</span></span>](../../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
