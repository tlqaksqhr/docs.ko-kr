---
title: "상호 운용성 개요(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- COM interop
- C# language, interoperability
- C++ Interop
- interoperability, about interoperability
- platform invoke
ms.assetid: c025b2e0-2357-4c27-8461-118f0090aeff
caps.latest.revision: "43"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7e4bc1814ed5c86660b4333542a3dc4eb7462e89
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="interoperability-overview-c-programming-guide"></a><span data-ttu-id="a1b1f-102">상호 운용성 개요(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="a1b1f-102">Interoperability Overview (C# Programming Guide)</span></span>
<span data-ttu-id="a1b1f-103">이 항목에서는 C# 관리 코드와 비관리 코드 간의 상호 운용성을 사용하도록 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-103">The topic describes methods to enable interoperability between C# managed code and unmanaged code.</span></span>  
  
## <a name="platform-invoke"></a><span data-ttu-id="a1b1f-104">플랫폼 호출</span><span class="sxs-lookup"><span data-stu-id="a1b1f-104">Platform Invoke</span></span>  
 <span data-ttu-id="a1b1f-105">*플랫폼 호출*은 Microsoft Win32 API의 함수와 같이 DLL(동적 연결 라이브러리)에서 구현된 관리되지 않는 함수를 관리 코드가 호출할 수 있도록 하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-105">*Platform invoke* is a service that enables managed code to call unmanaged functions that are implemented in dynamic link libraries (DLLs), such as those in the Microsoft Win32 API.</span></span> <span data-ttu-id="a1b1f-106">이 서비스는 내보낸 함수를 찾아서 호출하고 필요에 따라 상호 운용 경계를 가로질러 인수(정수, 문자열, 배열, 구조체 등)를 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-106">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span>  
  
 <span data-ttu-id="a1b1f-107">자세한 내용은 [관리되지 않는 DLL 함수 사용](../../../framework/interop/consuming-unmanaged-dll-functions.md) 및 [방법: 플랫폼 호출을 사용하여 웨이브 파일 재생](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-107">For more information, see [Consuming Unmanaged DLL Functions](../../../framework/interop/consuming-unmanaged-dll-functions.md) and [How to: Use Platform Invoke to Play a Wave File](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1b1f-108">CLR([공용 언어 런타임](../../../standard/clr.md))은 시스템 리소스에 대한 액세스를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-108">The [Common Language Runtime](../../../standard/clr.md) (CLR) manages access to system resources.</span></span> <span data-ttu-id="a1b1f-109">CLR 외부에 있는 비관리 코드를 호출하면 이 보안 메커니즘을 우회하므로 보안 위험이 제기됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-109">Calling unmanaged code that is outside the CLR bypasses this security mechanism, and therefore presents a security risk.</span></span> <span data-ttu-id="a1b1f-110">예를 들어 비관리 코드는 CLR 보안 메커니즘을 우회하여 비관리 코드의 리소스를 직접 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-110">For example, unmanaged code might call resources in unmanaged code directly, bypassing CLR security mechanisms.</span></span> <span data-ttu-id="a1b1f-111">자세한 내용은 [.NET Framework 보안](http://go.microsoft.com/fwlink/?LinkId=37122)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-111">For more information, see [.NET Framework Security](http://go.microsoft.com/fwlink/?LinkId=37122).</span></span>  
  
## <a name="c-interop"></a><span data-ttu-id="a1b1f-112">C++ Interop</span><span class="sxs-lookup"><span data-stu-id="a1b1f-112">C++ Interop</span></span>  
 <span data-ttu-id="a1b1f-113">C# 또는 다른 .NET Framework 언어로 작성된 코드에서 사용할 수 있도록 IJW(It Just Works)라고도 하는 C++ interop를 사용하여 네이티브 C++ 클래스를 래핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-113">You can use C++ interop, also known as It Just Works (IJW), to wrap a native C++ class so that it can be consumed by code that is authored in C# or another .NET Framework language.</span></span> <span data-ttu-id="a1b1f-114">이렇게 하려면 C++ 코드를 작성하여 네이티브 DLL 또는 COM 구성 요소를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-114">To do this, you write C++ code to wrap a native DLL or COM component.</span></span> <span data-ttu-id="a1b1f-115">다른 .NET Framework 언어와 달리 [!INCLUDE[vcprvc](~/includes/vcprvc-md.md)]에는 관리 코드와 비관리 코드가 동일한 응용 프로그램 및 동일한 파일에 있을 수 있도록 하는 상호 운용성 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-115">Unlike other .NET Framework languages, [!INCLUDE[vcprvc](~/includes/vcprvc-md.md)] has interoperability support that enables managed and unmanaged code to be located in the same application and even in the same file.</span></span> <span data-ttu-id="a1b1f-116">그런 다음 **/clr** 컴파일러 스위치로 관리되는 어셈블리를 생성하여 C++ 코드를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-116">You then build the C++ code by using the **/clr** compiler switch to produce a managed assembly.</span></span> <span data-ttu-id="a1b1f-117">마지막으로, C# 프로젝트의 어셈블리에 대한 참조를 추가하고 다른 관리되는 클래스를 사용하는 것처럼 래핑된 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-117">Finally, you add a reference to the assembly in your C# project and use the wrapped objects just as you would use other managed classes.</span></span>  
  
## <a name="exposing-com-components-to-c"></a><span data-ttu-id="a1b1f-118">C#에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="a1b1f-118">Exposing COM Components to C#</span></span>  
 <span data-ttu-id="a1b1f-119">C# 프로젝트에서 COM 구성 요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-119">You can consume a COM component from a C# project.</span></span> <span data-ttu-id="a1b1f-120">일반적인 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-120">The general steps are as follows:</span></span>  
  
1.  <span data-ttu-id="a1b1f-121">COM 구성 요소를 찾아서 사용하고 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-121">Locate a COM component to use and register it.</span></span> <span data-ttu-id="a1b1f-122">regsvr32.exe를 사용하여 COM DLL을 등록하거나 등록을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-122">Use regsvr32.exe to register or un–register a COM DLL.</span></span>  
  
2.  <span data-ttu-id="a1b1f-123">COM 구성 요소 또는 형식 라이브러리에 대한 참조를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-123">Add to the project a reference to the COM component or type library.</span></span>  
  
     <span data-ttu-id="a1b1f-124">참조를 추가하면 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]에서 형식 라이브러리를 입력으로 사용하는 [Tlbimp.exe(형식 라이브러리 가져오기)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)를 통해 .NET Framework interop 어셈블리를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-124">When you add the reference, [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] uses the [Tlbimp.exe (Type Library Importer)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382), which takes a type library as input, to output a .NET Framework interop assembly.</span></span> <span data-ttu-id="a1b1f-125">RCW(런타임 호출 가능 래퍼)라고도 하는 어셈블리는 형식 라이브러리에 있는 인터페이스 및 COM 클래스를 래핑하는 인터페이스 및 관리되는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-125">The assembly, also named a runtime callable wrapper (RCW), contains managed classes and interfaces that wrap the COM classes and interfaces that are in the type library.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="a1b1f-126">에서 생성된 어셈블리에 대한 참조를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-126"> adds to the project a reference to the generated assembly.</span></span>  
  
3.  <span data-ttu-id="a1b1f-127">RCW에서 정의된 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-127">Create an instance of a class that is defined in the RCW.</span></span> <span data-ttu-id="a1b1f-128">그러면 COM 개체의 인스턴스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-128">This, in turn, creates an instance of the COM object.</span></span>  
  
4.  <span data-ttu-id="a1b1f-129">다른 관리되는 개체와 동일한 방식으로 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-129">Use the object just as you use other managed objects.</span></span> <span data-ttu-id="a1b1f-130">개체가 가비지 수집에 의해 회수되면 COM 개체 인스턴스도 메모리에서 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-130">When the object is reclaimed by garbage collection, the instance of the COM object is also released from memory.</span></span>  
  
 <span data-ttu-id="a1b1f-131">자세한 내용은 [.NET Framework에 COM 구성 요소 노출](http://msdn.microsoft.com/library/e78b14f1-e487-43cd-9c6d-1a07483f1730)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-131">For more information, see [Exposing COM Components to the .NET Framework](http://msdn.microsoft.com/library/e78b14f1-e487-43cd-9c6d-1a07483f1730).</span></span>  
  
## <a name="exposing-c-to-com"></a><span data-ttu-id="a1b1f-132">COM에 C# 노출</span><span class="sxs-lookup"><span data-stu-id="a1b1f-132">Exposing C# to COM</span></span>  
 <span data-ttu-id="a1b1f-133">COM 클라이언트는 올바르게 노출된 C# 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-133">COM clients can consume C# types that have been correctly exposed.</span></span> <span data-ttu-id="a1b1f-134">C# 형식을 노출하는 기본 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-134">The basic steps to expose C# types are as follows:</span></span>  
  
1.  <span data-ttu-id="a1b1f-135">C# 프로젝트에서 Interop 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-135">Add interop attributes in the C# project.</span></span>  
  
     <span data-ttu-id="a1b1f-136">[!INCLUDE[csprcs](~/includes/csprcs-md.md)] 프로젝트 속성을 수정하여 어셈블리 COM이 표시되도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-136">You can make an assembly COM visible by modifying [!INCLUDE[csprcs](~/includes/csprcs-md.md)] project properties.</span></span> <span data-ttu-id="a1b1f-137">자세한 내용은 [어셈블리 정보 대화 상자](/visualstudio/ide/reference/assembly-information-dialog-box)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-137">For more information, see [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box).</span></span>  
  
2.  <span data-ttu-id="a1b1f-138">COM 형식 라이브러리를 생성하고 COM 사용을 위해 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-138">Generate a COM type library and register it for COM usage.</span></span>  
  
     <span data-ttu-id="a1b1f-139">COM interop에 대해 C# 어셈블리를 자동으로 등록하도록 [!INCLUDE[csprcs](~/includes/csprcs-md.md)] 프로젝트 속성을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-139">You can modify [!INCLUDE[csprcs](~/includes/csprcs-md.md)] project properties to automatically register the C# assembly for COM interop.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="a1b1f-140">에서는 [Regasm.exe(어셈블리 등록 도구)](http://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb)를 사용하며, 관리되는 어셈블리를 입력으로 사용하는 `/tlb` 명령줄 스위치를 통해 형식 라이브러리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-140"> uses the [Regasm.exe (Assembly Registration Tool)](http://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb), using the `/tlb` command-line switch, which takes a managed assembly as input, to generate a type library.</span></span> <span data-ttu-id="a1b1f-141">이 형식 라이브러리는 어셈블리의 `public` 형식을 설명하고, COM 클라이언트가 관리되는 클래스를 만들 수 있도록 레지스트리 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-141">This type library describes the `public` types in the assembly and adds registry entries so that COM clients can create managed classes.</span></span>  
  
 <span data-ttu-id="a1b1f-142">자세한 내용은 [.NET Framework 구성 요소를 COM에 노출](http://msdn.microsoft.com/library/e42a65f7-1e61-411f-b09a-aca1bbce24c6) 및 [예제 COM 클래스](../../../csharp/programming-guide/interop/example-com-class.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b1f-142">For more information, see [Exposing .NET Framework Components to COM](http://msdn.microsoft.com/library/e42a65f7-1e61-411f-b09a-aca1bbce24c6) and [Example COM Class](../../../csharp/programming-guide/interop/example-com-class.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1b1f-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1b1f-143">See Also</span></span>  
 [<span data-ttu-id="a1b1f-144">Interop 성능 향상</span><span class="sxs-lookup"><span data-stu-id="a1b1f-144">Improving Interop Performance</span></span>](http://go.microsoft.com/fwlink/?LinkId=99564)  
 [<span data-ttu-id="a1b1f-145">COM Interop 소개</span><span class="sxs-lookup"><span data-stu-id="a1b1f-145">Introduction to COM Interop</span></span>](http://go.microsoft.com/fwlink/?LinkId=112406)  
 [<span data-ttu-id="a1b1f-146">관리 코드와 비관리 코드 간의 마샬링</span><span class="sxs-lookup"><span data-stu-id="a1b1f-146">Marshaling between Managed and Unmanaged Code</span></span>](http://go.microsoft.com/fwlink/?LinkId=112398)  
 [<span data-ttu-id="a1b1f-147">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="a1b1f-147">Interoperating with Unmanaged Code</span></span>](../../../../docs/framework/interop/index.md)  
 [<span data-ttu-id="a1b1f-148">고급 COM 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="a1b1f-148">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/library/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [<span data-ttu-id="a1b1f-149">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a1b1f-149">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
