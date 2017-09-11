---
title: "리플렉션 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: acfcb519128de0d616757398c94ec70dc7de6ef1
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="reflection-visual-basic"></a><span data-ttu-id="dd635-102">리플렉션 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd635-102">Reflection (Visual Basic)</span></span>
<span data-ttu-id="dd635-103">리플렉션은 개체를 제공 (형식의 <xref:System.Type>) 어셈블리, 모듈 및 형식을 설명 하는.</xref:System.Type></span><span class="sxs-lookup"><span data-stu-id="dd635-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="dd635-104">리플렉션을 사용 하 여 동적으로 형식 인스턴스를 만들 형식을 기존 개체에 바인딩하거나, 기존 개체에서 형식을 가져오고 해당 메서드를 호출 또는 필드와 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd635-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="dd635-105">특성 코드를 사용 하는 경우 리플렉션을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd635-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="dd635-106">자세한 내용은 참조 [특성](https://msdn.microsoft.com/library/5x6cd29c)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd635-106">For more information, see [Attributes](https://msdn.microsoft.com/library/5x6cd29c).</span></span>  
  
 <span data-ttu-id="dd635-107">다음은 정적 메서드를 사용 하 여 리플렉션의 간단한 예제 `GetType` 모든 형식에서 상속 되는 `Object` 기본 클래스는 변수의 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dd635-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 <span data-ttu-id="dd635-108">출력이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd635-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="dd635-109">다음 예제에서는 리플렉션을 사용 하 여 로드 된 어셈블리의 전체 이름을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd635-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 <span data-ttu-id="dd635-110">출력이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd635-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a><span data-ttu-id="dd635-111">리플렉션 개요</span><span class="sxs-lookup"><span data-stu-id="dd635-111">Reflection Overview</span></span>  
 <span data-ttu-id="dd635-112">리플렉션은 다음과 같은 상황에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd635-112">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="dd635-113">특성 프로그램의 메타 데이터에 액세스 해야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="dd635-113">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="dd635-114">자세한 내용은 참조 [검색 특성에 저장 된 정보](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd635-114">For more information, see [Retrieving Information Stored in Attributes](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c).</span></span>  
  
-   <span data-ttu-id="dd635-115">검사 하 고 어셈블리의 형식 인스턴스화입니다.</span><span class="sxs-lookup"><span data-stu-id="dd635-115">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="dd635-116">런타임에 새 형식을 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd635-116">For building new types at runtime.</span></span> <span data-ttu-id="dd635-117"><xref:System.Reflection.Emit>.</xref:System.Reflection.Emit> 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd635-117">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="dd635-118">런타임에 바인딩을, 런타임에 작성 된 형식의 메서드에 액세스를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd635-118">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="dd635-119">항목을 참조 하십시오 [형식 동적 로드 및 사용](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd635-119">See the topic [Dynamically Loading and Using Types](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dd635-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="dd635-120">Related Sections</span></span>  
 <span data-ttu-id="dd635-121">추가 정보</span><span class="sxs-lookup"><span data-stu-id="dd635-121">For more information:</span></span>  
  
-   [<span data-ttu-id="dd635-122">리플렉션</span><span class="sxs-lookup"><span data-stu-id="dd635-122">Reflection</span></span>](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775)  
  
-   [<span data-ttu-id="dd635-123">형식 정보 보기</span><span class="sxs-lookup"><span data-stu-id="dd635-123">Viewing Type Information</span></span>](http://msdn.microsoft.com/library/7e7303a9-4064-4738-b4e7-b75974ed70d2)  
  
-   [<span data-ttu-id="dd635-124">리플렉션 및 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="dd635-124">Reflection and Generic Types</span></span>](http://msdn.microsoft.com/library/f7180fc5-dd41-42d4-8a8e-1b34288e06de)  
  
-   <span data-ttu-id="dd635-125"><xref:System.Reflection.Emit></xref:System.Reflection.Emit></span><span class="sxs-lookup"><span data-stu-id="dd635-125"><xref:System.Reflection.Emit></span></span>  
  
-   [<span data-ttu-id="dd635-126">특성에 저장 된 정보 검색</span><span class="sxs-lookup"><span data-stu-id="dd635-126">Retrieving Information Stored in Attributes</span></span>](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)  
  
## <a name="see-also"></a><span data-ttu-id="dd635-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd635-127">See Also</span></span>  
 <span data-ttu-id="dd635-128">[Visual Basic 프로그래밍 가이드](../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="dd635-128">[Visual Basic Programming Guide](../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="dd635-129"> [공용 언어 런타임의 어셈블리](https://msdn.microsoft.com/library/k3677y81)</span><span class="sxs-lookup"><span data-stu-id="dd635-129"> [Assemblies in the Common Language Runtime](https://msdn.microsoft.com/library/k3677y81)</span></span>
