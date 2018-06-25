---
title: CLR(공용 언어 런타임)
ms.custom: updateeachrelease
ms.date: 04/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- compiling source code, runtime functionality
- code, execution
- managed data
- runtime
- common language runtime
- metadata, runtime functionality
- .NET Framework, common language runtime
- language compilers
- managed code
- source code execution
- code, runtime functionality
ms.assetid: 059a624e-f7db-4134-ba9f-08b676050482
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89989b4b7730f4e252dc846377b385cb359dbee1
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36315123"
---
# <a name="common-language-runtime-clr-overview"></a><span data-ttu-id="05b41-102">CLR(공용 언어 런타임) 개요</span><span class="sxs-lookup"><span data-stu-id="05b41-102">Common Language Runtime (CLR) overview</span></span>

<span data-ttu-id="05b41-103">.NET Framework에서는 공용 언어 런타임이라고 하는 런타임 환경을 제공하는데, 여기에서는 코드를 실행하며 개발 과정을 더 쉽게 해 주는 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-103">The .NET Framework provides a run-time environment called the common language runtime, which runs the code and provides services that make the development process easier.</span></span>

<span data-ttu-id="05b41-104">컴파일러와 도구는 공용 언어 런타임의 기능을 노출하며 관리되는 이 실행 환경을 활용하는 코드를 작성할 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-104">Compilers and tools expose the common language runtime's functionality and enable you to write code that benefits from this managed execution environment.</span></span> <span data-ttu-id="05b41-105">런타임을 대상으로 하는 언어 컴파일러를 사용하여 개발한 코드를 관리 코드라고 합니다. 이 코드에서는 언어 간 통합, 언어 간 예외 처리, 향상된 보안, 버전 관리 및 배포 지원, 구성 요소 상호 작용을 위한 간단한 모델, 디버깅 및 프로파일링 서비스 등의 기능을 이용합니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-105">Code that you develop with a language compiler that targets the runtime is called managed code; it benefits from features such as cross-language integration, cross-language exception handling, enhanced security, versioning and deployment support, a simplified model for component interaction, and debugging and profiling services.</span></span>

> [!NOTE]
> <span data-ttu-id="05b41-106">형식 시스템, 메타데이터의 형식 및 런타임 환경(가상 실행 시스템)은 모두 공용 표준인 ECMA Common Language Infrastructure 사양으로 정의하기 때문에 컴파일러 및 도구에서 공용 언어 런타임이 사용할 수 있는 출력을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-106">Compilers and tools are able to produce output that the common language runtime can consume because the type system, the format of metadata, and the runtime environment (the virtual execution system) are all defined by a public standard, the ECMA Common Language Infrastructure specification.</span></span> <span data-ttu-id="05b41-107">자세한 내용은 [ECMA C# 및 공용 언어 인프라 사양](https://visualstudio.microsoft.com/license-terms/ecma-c-common-language-infrastructure-standards/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05b41-107">For more information, see [ECMA C# and Common Language Infrastructure Specifications](https://visualstudio.microsoft.com/license-terms/ecma-c-common-language-infrastructure-standards/).</span></span>

<span data-ttu-id="05b41-108">런타임에서 관리 코드에 서비스를 제공할 수 있게 하려면 언어 컴파일러에서 사용자 코드의 형식, 멤버 및 참조를 설명하는 메타데이터를 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-108">To enable the runtime to provide services to managed code, language compilers must emit metadata that describes the types, members, and references in your code.</span></span> <span data-ttu-id="05b41-109">메타데이터는 코드와 함께 저장되며 로드 가능한 모든 공용 언어 런타임 PE(이식 가능한 실행) 파일에는 메타데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-109">Metadata is stored with the code; every loadable common language runtime portable executable (PE) file contains metadata.</span></span> <span data-ttu-id="05b41-110">런타임에서는 메타데이터를 사용하여 클래스를 찾고 로드하며, 메모리에 인스턴스를 배치하고, 메서드 호출을 확인하고, 네이티브 코드를 생성하고, 보안을 강화하며, 런타임 컨텍스트 경계를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-110">The runtime uses metadata to locate and load classes, lay out instances in memory, resolve method invocations, generate native code, enforce security, and set run-time context boundaries.</span></span>

<span data-ttu-id="05b41-111">런타임에서는 자동으로 개체 레이아웃을 처리하고 개체에 대한 참조를 관리하며, 이들이 더 이상 사용되지 않을 때는 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-111">The runtime automatically handles object layout and manages references to objects, releasing them when they are no longer being used.</span></span> <span data-ttu-id="05b41-112">수명을 이런 식으로 관리하는 개체를 관리되는 데이터라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-112">Objects whose lifetimes are managed in this way are called managed data.</span></span> <span data-ttu-id="05b41-113">가비지 수집을 통해 메모리 누수뿐만 아니라 기타 몇 가지 일반적인 프로그래밍 오류도 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-113">Garbage collection eliminates memory leaks as well as some other common programming errors.</span></span> <span data-ttu-id="05b41-114">코드를 관리할 경우 관리되는 데이터, 관리되지 않는 데이터 또는 관리되는 데이터와 관리되지 않는 데이터 모두를 .NET Framework 응용 프로그램에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-114">If your code is managed, you can use managed data, unmanaged data, or both managed and unmanaged data in your .NET Framework application.</span></span> <span data-ttu-id="05b41-115">언어 컴파일러에서는 자체 형식(예: 기본 형식)을 제공하기 때문에 데이터가 관리되고 있는지 항상 알 수 없으며 알 필요도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-115">Because language compilers supply their own types, such as primitive types, you might not always know (or need to know) whether your data is being managed.</span></span>

<span data-ttu-id="05b41-116">공용 언어 런타임을 사용하면 구성 요소 및 응용 프로그램에 속한 개체가 여러 언어를 통해 상호 작용하는 경우 이를 쉽게 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-116">The common language runtime makes it easy to design components and applications whose objects interact across languages.</span></span> <span data-ttu-id="05b41-117">다른 언어로 작성된 개체들이 서로 통신할 수 있고 해당 동작들이 완벽하게 통합될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-117">Objects written in different languages can communicate with each other, and their behaviors can be tightly integrated.</span></span> <span data-ttu-id="05b41-118">예를 들어, 클래스를 정의한 다음 다른 언어를 사용하여 원본 클래스에서 클래스를 파생시키거나 원본 클래스의 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-118">For example, you can define a class and then use a different language to derive a class from your original class or call a method on the original class.</span></span> <span data-ttu-id="05b41-119">또한 클래스의 인스턴스를 다른 언어로 작성된 클래스의 메서드로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-119">You can also pass an instance of a class to a method of a class written in a different language.</span></span> <span data-ttu-id="05b41-120">런타임을 대상으로 하는 언어 컴파일러 및 도구에서 런타임에서 정의한 공용 형식 시스템을 사용하고, 형식의 생성, 사용, 유지 및 바인딩 뿐만 아니라 새 형식을 정의할 때도 런타임 규칙을 따르기 때문에 이러한 언어 간 통합이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-120">This cross-language integration is possible because language compilers and tools that target the runtime use a common type system defined by the runtime, and they follow the runtime's rules for defining new types, as well as for creating, using, persisting, and binding to types.</span></span>

<span data-ttu-id="05b41-121">모든 관리되는 구성 요소는 메타데이터를 작성할 때 참고한 구성 요소와 리소스에 대한 정보를 메타데이터의 일부로 갖고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-121">As part of their metadata, all managed components carry information about the components and resources they were built against.</span></span> <span data-ttu-id="05b41-122">런타임에서는 이 정보를 사용하여 해당 구성 요소나 응용 프로그램에서 필요한 모든 항목으로 구성된 지정 버전을 가질 수 있도록 해줍니다. 그러면 맞지 않는 일부 종속성 때문에 코드가 중단되는 일이 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-122">The runtime uses this information to ensure that your component or application has the specified versions of everything it needs, which makes your code less likely to break because of some unmet dependency.</span></span> <span data-ttu-id="05b41-123">설정 및 유지가 어려운 레지스트리에 속성과 상태 데이터가 더 이상 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-123">Registration information and state data are no longer stored in the registry where they can be difficult to establish and maintain.</span></span> <span data-ttu-id="05b41-124">오히려 사용자가 정의한 형식과 해당 종속성에 대한 정보는 코드와 함께 메타데이터로 저장되어 구성 요소 복제 및 제거 작업이 훨씬 덜 복잡하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-124">Instead, information about the types you define (and their dependencies) is stored with the code as metadata, making the tasks of component replication and removal much less complicated.</span></span>

<span data-ttu-id="05b41-125">언어 컴파일러 및 도구는 개발자에게 유용하고 자연스러운 방식으로 런타임의 기능을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-125">Language compilers and tools expose the runtime's functionality in ways that are intended to be useful and intuitive to developers.</span></span> <span data-ttu-id="05b41-126">이것은 런타임의 일부 기능이 환경에 따라 더 두드러질 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-126">This means that some features of the runtime might be more noticeable in one environment than in another.</span></span> <span data-ttu-id="05b41-127">사용하는 언어 컴파일러 또는 도구에 따라 런타임을 사용하는 방법이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-127">How you experience the runtime depends on which language compilers or tools you use.</span></span> <span data-ttu-id="05b41-128">예를 들어, Visual Basic 개발자일 경우 공용 언어 런타임을 사용하면 Visual Basic 언어가 이전보다 더 개체 지향적인 기능을 갖고 있음을 알게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-128">For example, if you are a Visual Basic developer, you might notice that with the common language runtime, the Visual Basic language has more object-oriented features than before.</span></span> <span data-ttu-id="05b41-129">런타임은 다음과 같은 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-129">The runtime provides the following benefits:</span></span>

- <span data-ttu-id="05b41-130">성능 향상</span><span class="sxs-lookup"><span data-stu-id="05b41-130">Performance improvements.</span></span>

- <span data-ttu-id="05b41-131">다른 언어로 개발된 구성 요소를 쉽게 사용할 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="05b41-131">The ability to easily use components developed in other languages.</span></span>

- <span data-ttu-id="05b41-132">클래스 라이브러리에서 제공하는 확장 가능한 형식</span><span class="sxs-lookup"><span data-stu-id="05b41-132">Extensible types provided by a class library.</span></span>

- <span data-ttu-id="05b41-133">상속, 인터페이스, 개체 지향적인 프로그래밍을 위한 오버로딩 등과 같은 언어 기능</span><span class="sxs-lookup"><span data-stu-id="05b41-133">Language features such as inheritance, interfaces, and overloading for object-oriented programming.</span></span>

- <span data-ttu-id="05b41-134">확장 가능한 다중 스레드 응용 프로그램을 만들 수 있도록 해주는 명시적 자유 스레딩에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="05b41-134">Support for explicit free threading that allows creation of multithreaded, scalable applications.</span></span>

- <span data-ttu-id="05b41-135">구조적 예외 처리에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="05b41-135">Support for structured exception handling.</span></span>

- <span data-ttu-id="05b41-136">사용자 지정 특성에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="05b41-136">Support for custom attributes.</span></span>

- <span data-ttu-id="05b41-137">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="05b41-137">Garbage collection.</span></span>

- <span data-ttu-id="05b41-138">향상된 형식 안정성과 보안을 위해 함수 포인터 대신 대리자 사용.</span><span class="sxs-lookup"><span data-stu-id="05b41-138">Use of delegates instead of function pointers for increased type safety and security.</span></span> <span data-ttu-id="05b41-139">대리자에 대한 자세한 내용은 [공용 형식 시스템](../../docs/standard/base-types/common-type-system.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05b41-139">For more information about delegates, see [Common Type System](../../docs/standard/base-types/common-type-system.md).</span></span>

## <a name="clr-versions"></a><span data-ttu-id="05b41-140">CLR 버전</span><span class="sxs-lookup"><span data-stu-id="05b41-140">CLR versions</span></span>

<span data-ttu-id="05b41-141">.NET Framework 버전 번호는 포함하는 CLR 버전 번호와 반드시 일치하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-141">The version number of the .NET Framework doesn't necessarily correspond to the version number of the CLR it includes.</span></span> <span data-ttu-id="05b41-142">다음 표에 두 버전 번호가 어떻게 상호 연관되는지가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-142">The following table shows how the two version numbers correlate.</span></span>

|<span data-ttu-id="05b41-143">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="05b41-143">.NET Framework version</span></span>|<span data-ttu-id="05b41-144">포함하는 CLR 버전</span><span class="sxs-lookup"><span data-stu-id="05b41-144">Includes CLR version</span></span>|
|----------------------------|--------------------------|
|<span data-ttu-id="05b41-145">1.0</span><span class="sxs-lookup"><span data-stu-id="05b41-145">1.0</span></span>|<span data-ttu-id="05b41-146">1.0</span><span class="sxs-lookup"><span data-stu-id="05b41-146">1.0</span></span>|
|<span data-ttu-id="05b41-147">1.1</span><span class="sxs-lookup"><span data-stu-id="05b41-147">1.1</span></span>|<span data-ttu-id="05b41-148">1.1</span><span class="sxs-lookup"><span data-stu-id="05b41-148">1.1</span></span>|
|<span data-ttu-id="05b41-149">2.0</span><span class="sxs-lookup"><span data-stu-id="05b41-149">2.0</span></span>|<span data-ttu-id="05b41-150">2.0</span><span class="sxs-lookup"><span data-stu-id="05b41-150">2.0</span></span>|
|<span data-ttu-id="05b41-151">3.0</span><span class="sxs-lookup"><span data-stu-id="05b41-151">3.0</span></span>|<span data-ttu-id="05b41-152">2.0</span><span class="sxs-lookup"><span data-stu-id="05b41-152">2.0</span></span>|
|<span data-ttu-id="05b41-153">3.5</span><span class="sxs-lookup"><span data-stu-id="05b41-153">3.5</span></span>|<span data-ttu-id="05b41-154">2.0</span><span class="sxs-lookup"><span data-stu-id="05b41-154">2.0</span></span>|
|<span data-ttu-id="05b41-155">4</span><span class="sxs-lookup"><span data-stu-id="05b41-155">4</span></span>|<span data-ttu-id="05b41-156">4</span><span class="sxs-lookup"><span data-stu-id="05b41-156">4</span></span>|
|<span data-ttu-id="05b41-157">4.5(4.5.1 및 4.5.2 포함)</span><span class="sxs-lookup"><span data-stu-id="05b41-157">4.5 (including 4.5.1 and 4.5.2)</span></span>|<span data-ttu-id="05b41-158">4</span><span class="sxs-lookup"><span data-stu-id="05b41-158">4</span></span>|
|<span data-ttu-id="05b41-159">4.6(4.6.1 및 4.6.2 포함)</span><span class="sxs-lookup"><span data-stu-id="05b41-159">4.6 (including 4.6.1 and 4.6.2)</span></span>|<span data-ttu-id="05b41-160">4</span><span class="sxs-lookup"><span data-stu-id="05b41-160">4</span></span>|
|<span data-ttu-id="05b41-161">4.7(4.7.1 및 4.7.2 포함)</span><span class="sxs-lookup"><span data-stu-id="05b41-161">4.7 (including 4.7.1 and 4.7.2)</span></span>|<span data-ttu-id="05b41-162">4</span><span class="sxs-lookup"><span data-stu-id="05b41-162">4</span></span>|

## <a name="related-topics"></a><span data-ttu-id="05b41-163">관련 항목</span><span class="sxs-lookup"><span data-stu-id="05b41-163">Related topics</span></span>

|<span data-ttu-id="05b41-164">제목</span><span class="sxs-lookup"><span data-stu-id="05b41-164">Title</span></span>|<span data-ttu-id="05b41-165">설명</span><span class="sxs-lookup"><span data-stu-id="05b41-165">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="05b41-166">관리되는 실행 프로세스</span><span class="sxs-lookup"><span data-stu-id="05b41-166">Managed Execution Process</span></span>](managed-execution-process.md)|<span data-ttu-id="05b41-167">공용 언어 런타임을 사용하는 데 필요한 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-167">Describes the steps required to take advantage of the common language runtime.</span></span>|
|[<span data-ttu-id="05b41-168">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="05b41-168">Automatic Memory Management</span></span>](automatic-memory-management.md)|<span data-ttu-id="05b41-169">가비지 수집기에서 메모리를 할당하고 해제하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-169">Describes how the garbage collector allocates and releases memory.</span></span>|
|[<span data-ttu-id="05b41-170">.NET Framework의 개요</span><span class="sxs-lookup"><span data-stu-id="05b41-170">Overview of the .NET Framework</span></span>](../framework/get-started/overview.md)|<span data-ttu-id="05b41-171">공용 형식 시스템, 언어 간 상호 운용성, 관리되는 실행, 응용 프로그램 도메인, 어셈블리 등과 같은 .NET Framework의 주요 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-171">Describes key .NET Framework concepts such as the common type system, cross-language interoperability, managed execution, application domains, and assemblies.</span></span>|
|[<span data-ttu-id="05b41-172">공용 형식 시스템</span><span class="sxs-lookup"><span data-stu-id="05b41-172">Common Type System</span></span>](./base-types/common-type-system.md)|<span data-ttu-id="05b41-173">언어 간 통합을 지원하면서 런타임에서 형식을 선언, 사용, 관리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05b41-173">Describes how types are declared, used, and managed in the runtime in support of cross-language integration.</span></span>|

## <a name="see-also"></a><span data-ttu-id="05b41-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05b41-174">See also</span></span>

[<span data-ttu-id="05b41-175">버전 및 종속성</span><span class="sxs-lookup"><span data-stu-id="05b41-175">Versions and Dependencies</span></span>](../framework/migration-guide/versions-and-dependencies.md)
