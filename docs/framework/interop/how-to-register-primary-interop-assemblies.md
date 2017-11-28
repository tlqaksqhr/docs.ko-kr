---
title: "방법: 주 Interop 어셈블리 등록"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- registering primary interop assemblies
- primary interop assemblies, registering
ms.assetid: 4b2fcf8a-429d-43ce-8334-e026040be8bb
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1b72a24f349237aa35ccae295e9e552facc21ddd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-register-primary-interop-assemblies"></a><span data-ttu-id="b7e24-102">방법: 주 Interop 어셈블리 등록</span><span class="sxs-lookup"><span data-stu-id="b7e24-102">How to: Register Primary Interop Assemblies</span></span>
<span data-ttu-id="b7e24-103">클래스는 COM interop에 의해서만 마샬링될 수 있으며 항상 인터페이스로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-103">Classes can be marshaled only by COM interop and are always marshaled as interfaces.</span></span> <span data-ttu-id="b7e24-104">클래스를 마샬링하는 데 사용되는 인터페이스를 클래스 인터페이스라고 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-104">In some cases the interface used to marshal the class is known as the class interface.</span></span> <span data-ttu-id="b7e24-105">선택한 인터페이스로 클래스 인터페이스를 재정의하는 방법에 대한 자세한 내용은 [COM 호출 가능 래퍼](../../../docs/framework/interop/com-callable-wrapper.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7e24-105">For information about overriding the class interface with an interface of your choice, see [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md).</span></span>  
  
 <span data-ttu-id="b7e24-106">.NET Framework 응용 프로그램에서 COM 형식을 사용하려는 모든 개발자가 interop 어셈블리를 생성할 수 있지만 이 경우 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-106">Although any developer who wants to use COM types from a .NET Framework application can generate an interop assembly, doing so creates a problem.</span></span> <span data-ttu-id="b7e24-107">개발자가 COM 형식 라이브러리를 가져오고 서명할 때마다 다른 개발자가 가져오고 서명한 형식과 호환되지 않는 고유한 형식 집합이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-107">Each time a developer imports and signs a COM type library, that developer creates a set of unique types that are incompatible with those imported and signed by another developer.</span></span> <span data-ttu-id="b7e24-108">이러한 형식 비호환성 문제에 대한 해결 방법은 각 개발자가 공급업체에서 제공하고 서명한 주 interop 어셈블리를 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-108">The solution to this type incompatibility problem is for each developer to obtain the vendor-supplied and signed primary interop assembly.</span></span>  
  
 <span data-ttu-id="b7e24-109">타사 COM 형식을 다른 응용 프로그램에 노출하려는 경우 항상 정의하는 형식 라이브러리와 동일한 게시자가 제공한 주 interop 어셈블리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-109">If you plan to expose third-party COM types to other applications, always use the primary interop assembly provided by the same publisher as the type library it defines.</span></span> <span data-ttu-id="b7e24-110">보장된 형식 호환성을 제공할 뿐 아니라 주 interop 어셈블리는 상호 운용성을 향상시키기 위해 공급업체에서 사용자 지정되는 경우도 많습니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-110">In addition to providing guaranteed type compatibility, primary interop assemblies are often customized by the vendor to enhance interoperability.</span></span>  
  
 <span data-ttu-id="b7e24-111">타사 COM 형식을 노출하지 않으려는 경우에도 주 interop 어셈블리를 사용하면 COM 구성 요소와의 상호 운용 작업이 쉬워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-111">Even if you do not plan to expose third-party COM types, using the primary interop assembly can ease the task of interoperating with COM components.</span></span> <span data-ttu-id="b7e24-112">그러나 이 전략은 공급업체가 주 interop 어셈블리에서 정의된 형식에 대해 수행할 수 있는 변경 내용으로부터 단절을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-112">However, this strategy provides no insulation from changes a vendor might make to types defined in a primary interop assembly.</span></span> <span data-ttu-id="b7e24-113">응용 프로그램에 이러한 단절이 필요한 경우 주 interop 어셈블리를 사용하는 대신 고유한 interop 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-113">When your application requires such insulation, generate your own interop assembly instead of using the primary interop assembly.</span></span>  
  
 <span data-ttu-id="b7e24-114">[!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)]를 사용하여 참조하려면 먼저 가져온 모든 주 interop 어셈블리를 개발 컴퓨터에 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-114">You must register all acquired primary interop assemblies on your development computer before you can reference them with [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)].</span></span> <span data-ttu-id="b7e24-115">Visual Studio는 COM 형식 라이브러리의 형식을 처음 참조할 때 주 interop 어셈블리를 찾아서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-115">Visual Studio looks for and uses a primary interop assembly the first time that you reference a type from a COM type library.</span></span> <span data-ttu-id="b7e24-116">Visual Studio가 형식 라이브러리와 연결된 주 interop 어셈블리를 찾을 수 없는 경우 가져오거나 대신 interop 어셈블리를 만들라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-116">If Visual Studio cannot locate the primary interop assembly associated with the type library, it prompts you to acquire it or offers to create an interop assembly instead.</span></span> <span data-ttu-id="b7e24-117">마찬가지로, [형식 라이브러리 가져오기(Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)도 레지스트리를 사용하여 주 interop 어셈블리를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-117">Likewise, the [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) also uses the registry to locate primary interop assemblies.</span></span>  
  
 <span data-ttu-id="b7e24-118">Visual Studio를 사용하려는 경우가 아니면 주 interop 어셈블리를 등록할 필요는 없지만 등록 시 다음과 같은 두 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-118">Although it is not necessary to register primary interop assemblies unless you plan to use Visual Studio, registration provides two advantages:</span></span>  
  
-   <span data-ttu-id="b7e24-119">등록된 주 interop 어셈블리가 원래 형식 라이브러리의 레지스트리 키 아래에 명확하게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-119">A registered primary interop assembly is clearly marked under the registry key of the original type library.</span></span> <span data-ttu-id="b7e24-120">등록이 컴퓨터에서 주 interop 어셈블리를 찾는 최상의 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-120">Registration is the best way for you to locate a primary interop assembly on your computer.</span></span>  
  
-   <span data-ttu-id="b7e24-121">나중에 Visual Studio를 사용하여 등록되지 않은 주 interop 어셈블리가 있는 형식을 참조할 경우 실수로 새 interop 어셈블리를 생성 및 사용하는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-121">You can avoid accidentally generating and using a new interop assembly if, at some time in the future, you do use Visual Studio to reference a type for which you have an unregistered primary interop assembly.</span></span>  
  
 <span data-ttu-id="b7e24-122">[어셈블리 등록 도구(Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)를 사용하여 주 interop 어셈블리를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-122">Use the [Assembly Registration Tool (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) to register a primary interop assembly.</span></span>  
  
### <a name="to-register-a-primary-interop-assembly"></a><span data-ttu-id="b7e24-123">주 Interop 어셈블리를 등록하려면</span><span class="sxs-lookup"><span data-stu-id="b7e24-123">To register a primary interop assembly</span></span>  
  
1.  <span data-ttu-id="b7e24-124">명령 프롬프트에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-124">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="b7e24-125">**regasm** *assemblyname*</span><span class="sxs-lookup"><span data-stu-id="b7e24-125">**regasm** *assemblyname*</span></span>  
  
     <span data-ttu-id="b7e24-126">이 명령에서 *assemblyname*은 등록된 어셈블리의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-126">In this command, *assemblyname* is the file name of the assembly that is registered.</span></span> <span data-ttu-id="b7e24-127">Regasm.exe는 원래 형식 라이브러리와 동일한 레지스트리 키 아래에 주 interop 어셈블리에 대한 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-127">Regasm.exe adds an entry for the primary interop assembly under the same registry key as the original type library.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7e24-128">예제</span><span class="sxs-lookup"><span data-stu-id="b7e24-128">Example</span></span>  
 <span data-ttu-id="b7e24-129">다음 예제에서는 `CompanyA.UtilLib.dll` 주 interop 어셈블리를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b7e24-129">The following example registers the `CompanyA.UtilLib.dll` primary interop assembly.</span></span>  
  
```  
regasm CompanyA.UtilLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7e24-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7e24-130">See Also</span></span>  
 [<span data-ttu-id="b7e24-131">주 Interop 어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b7e24-131">Programming with Primary Interop Assemblies</span></span>](http://msdn.microsoft.com/en-us/306fa1d6-0703-4004-9e93-d0a57f1be81e)  
 [<span data-ttu-id="b7e24-132">주 Interop 어셈블리 찾기</span><span class="sxs-lookup"><span data-stu-id="b7e24-132">Locating Primary Interop Assemblies</span></span>](http://msdn.microsoft.com/en-us/d6768e4b-cd80-414d-a4f8-05d979eb393b)  
 [<span data-ttu-id="b7e24-133">기본 Interop 어셈블리 재배포</span><span class="sxs-lookup"><span data-stu-id="b7e24-133">Redistributing Primary Interop Assemblies</span></span>](http://msdn.microsoft.com/en-us/e76384f0-d631-474c-bdbd-13884cba0265)
