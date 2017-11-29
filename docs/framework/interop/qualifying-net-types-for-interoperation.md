---
title: "상호 운용할 .NET 형식의 정규화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, qualifying .NET types
- qualifying .NET types for interoperation
- interoperation with unmanaged code, qualifying .NET types
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b6487c151f49f6084977deb600e7f93e5eb7acee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="qualifying-net-types-for-interoperation"></a><span data-ttu-id="781dc-102">상호 운용할 .NET 형식의 정규화</span><span class="sxs-lookup"><span data-stu-id="781dc-102">Qualifying .NET Types for Interoperation</span></span>
<span data-ttu-id="781dc-103">어셈블리에서 형식을 COM 응용 프로그램으로 노출하려는 경우 디자인 타임에 COM interop의 요구 사항을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="781dc-103">If you intend to expose types in an assembly to COM applications, consider the requirements of COM interop at design time.</span></span> <span data-ttu-id="781dc-104">다음 지침을 준수하면 관리되는 형식(클래스, 인터페이스, 구조체 및 열거형)이 COM 형식과 원활하게 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-104">Managed types (class, interface, structure, and enumeration) seamlessly integrate with COM types when you adhere to the following guidelines:</span></span>  
  
-   <span data-ttu-id="781dc-105">클래스에서 인터페이스를 명시적으로 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-105">Classes should implement interfaces explicitly.</span></span>  
  
     <span data-ttu-id="781dc-106">COM interop에서 클래스의 모든 멤버와 기본 클래스의 멤버를 포함하는 인터페이스를 자동으로 생성하는 메커니즘을 제공하지만 명시적 인터페이스를 제공하는 것이 훨씬 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-106">Although COM interop provides a mechanism to automatically generate an interface containing all members of the class and the members of its base class, it is far better to provide explicit interfaces.</span></span> <span data-ttu-id="781dc-107">자동으로 생성된 인터페이스는 클래스 인터페이스라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-107">The automatically generated interface is called the class interface.</span></span> <span data-ttu-id="781dc-108">지침은 [클래스 인터페이스 소개](http://msdn.microsoft.com/en-us/733c0dd2-12e5-46e6-8de1-39d5b25df024)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="781dc-108">For guidelines, see [Introducing the Class Interface](http://msdn.microsoft.com/en-us/733c0dd2-12e5-46e6-8de1-39d5b25df024).</span></span>  
  
     <span data-ttu-id="781dc-109">IDL(Interface Definition Language) 또는 이와 동등한 사항을 사용할 필요 없이 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# 및 C++를 사용하여 코드에 인터페이스 정의를 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-109">You can use [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C#, and C++ to incorporate interface definitions in your code, instead of having to use Interface Definition Language (IDL) or its equivalent.</span></span> <span data-ttu-id="781dc-110">구문에 대한 세부 정보는 언어 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="781dc-110">For syntax details, see your language documentation.</span></span>  
  
-   <span data-ttu-id="781dc-111">관리되는 형식은 public이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-111">Managed types must be public.</span></span>  
  
     <span data-ttu-id="781dc-112">어셈블리의 public 형식만 등록하고 형식 라이브러리로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-112">Only public types in an assembly are registered and exported to the type library.</span></span> <span data-ttu-id="781dc-113">결과적으로 public 형식만 COM에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-113">As a result, only public types are visible to COM.</span></span>  
  
     <span data-ttu-id="781dc-114">관리되는 형식은 COM에 노출되지 않을 수 있는 기타 관리 코드에 기능을 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-114">Managed types expose features to other managed code that might not be exposed to COM.</span></span> <span data-ttu-id="781dc-115">예를 들어 매개 변수화된 생성자, 정적 메서드 및 상수 필드는 COM 클라이언트에 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-115">For instance, parameterized constructors, static methods, and constant fields are not exposed to COM clients.</span></span> <span data-ttu-id="781dc-116">또한 런타임 시 데이터를 형식에 대해 마샬링할 때 데이터가 복사되거나 변환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-116">Further, as the runtime marshals data in and out of a type, the data might be copied or transformed.</span></span>  
  
-   <span data-ttu-id="781dc-117">메서드, 속성, 필드 및 이벤트는 public이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-117">Methods, properties, fields, and events must be public.</span></span>  
  
     <span data-ttu-id="781dc-118">public 형식의 멤버를 COM에 표시하려는 경우 해당 멤버도 public이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-118">Members of public types must also be public if they are to be visible to COM.</span></span> <span data-ttu-id="781dc-119"><xref:System.Runtime.InteropServices.ComVisibleAttribute>를 적용하여 어셈블리의 가시성, public 형식 또는 public 형식의 공용 멤버를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-119">You can restrict the visibility of an assembly, a public type, or public members of a public type by applying the <xref:System.Runtime.InteropServices.ComVisibleAttribute>.</span></span> <span data-ttu-id="781dc-120">기본적으로 모든 public 형식 및 멤버만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-120">By default, all public types and members are visible.</span></span>  
  
-   <span data-ttu-id="781dc-121">형식에는 COM에서 활성화될 public 기본 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-121">Types must have a public default constructor to be activated from COM.</span></span>  
  
     <span data-ttu-id="781dc-122">관리되는 public 형식만 COM에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-122">Managed, public types are visible to COM.</span></span> <span data-ttu-id="781dc-123">그러나 public 기본 생성자(인수 없는 생성자)가 없으면 COM 클라이언트에서 형식을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-123">However, without a public default constructor (a constructor with no arguments), COM clients cannot create the type.</span></span> <span data-ttu-id="781dc-124">다른 방법으로 활성화된 경우에도 COM 클라이언트에서 여전히 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-124">COM clients can still use the type if it is activated by some other means.</span></span>  
  
-   <span data-ttu-id="781dc-125">형식은 추상일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-125">Types cannot be abstract.</span></span>  
  
     <span data-ttu-id="781dc-126">COM 클라이언트와 .NET 클라이언트 모두 추상 형식을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-126">Neither COM clients nor .NET clients can create abstract types.</span></span>  
  
 <span data-ttu-id="781dc-127">COM으로 내보낼 때 관리되는 형식의 상속 계층 구조가 평면화됩니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-127">When exported to COM, the inheritance hierarchy of a managed type is flattened.</span></span> <span data-ttu-id="781dc-128">관리되는 환경과 관리되지 않는 환경에서는 버전 관리도 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-128">Versioning also differs between managed and unmanaged environments.</span></span> <span data-ttu-id="781dc-129">COM에 노출된 형식에는 관리되는 다른 형식과 동일한 버전 관리 특성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="781dc-129">Types exposed to COM do not have the same versioning characteristics as other managed types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="781dc-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="781dc-130">See Also</span></span>  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute>  
 [<span data-ttu-id="781dc-131">.NET Framework 구성 요소를 COM에 노출</span><span class="sxs-lookup"><span data-stu-id="781dc-131">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [<span data-ttu-id="781dc-132">클래스 인터페이스 소개</span><span class="sxs-lookup"><span data-stu-id="781dc-132">Introducing the Class Interface</span></span>](http://msdn.microsoft.com/en-us/733c0dd2-12e5-46e6-8de1-39d5b25df024)  
 [<span data-ttu-id="781dc-133">Interop 특성 적용</span><span class="sxs-lookup"><span data-stu-id="781dc-133">Applying Interop Attributes</span></span>](../../../docs/framework/interop/applying-interop-attributes.md)  
 [<span data-ttu-id="781dc-134">COM에서 사용할 어셈블리의 패키징</span><span class="sxs-lookup"><span data-stu-id="781dc-134">Packaging an Assembly for COM</span></span>](../../../docs/framework/interop/packaging-an-assembly-for-com.md)
