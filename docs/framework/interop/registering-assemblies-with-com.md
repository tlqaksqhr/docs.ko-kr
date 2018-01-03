---
title: "COM에 어셈블리 등록"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, registering assemblies
- unregistering assemblies
- interoperation with unmanaged code, registering assemblies
- registering assemblies
ms.assetid: 87925795-a3ae-4833-b138-125413478551
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1473fa07b57dcd19ea192db6cdb0a395f119b159
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="registering-assemblies-with-com"></a><span data-ttu-id="d76be-102">COM에 어셈블리 등록</span><span class="sxs-lookup"><span data-stu-id="d76be-102">Registering Assemblies with COM</span></span>
<span data-ttu-id="d76be-103">[어셈블리 등록 도구(Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)라는 명령줄 도구를 실행하여 COM과 사용할 어셈블리를 등록하거나 등록 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76be-103">You can run a command-line tool called the [Assembly Registration Tool (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) to register or unregister an assembly for use with COM.</span></span> <span data-ttu-id="d76be-104">COM 클라이언트에서 .NET Framework 클래스를 투명하게 사용할 수 있도록 Regasm.exe에서는 클래스에 대한 정보를 시스템 레지스트리에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d76be-104">Regasm.exe adds information about the class to the system registry so COM clients can use the .NET Framework class transparently.</span></span> <span data-ttu-id="d76be-105"><xref:System.Runtime.InteropServices.RegistrationServices> 클래스는 이와 동등한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d76be-105">The <xref:System.Runtime.InteropServices.RegistrationServices> class provides the equivalent functionality.</span></span>  
  
 <span data-ttu-id="d76be-106">관리되는 구성 요소를 Windows 레지스트리에 등록해야 COM 클라이언트에서 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76be-106">A managed component must be registered in the Windows registry before it can be activated from a COM client.</span></span> <span data-ttu-id="d76be-107">다음 표에서는 Regasm.exe를 통해 일반적으로 Windows 레지스트리에 추가하는 키를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d76be-107">The following table shows the keys that Regasm.exe typically adds to the Windows registry.</span></span> <span data-ttu-id="d76be-108">(000000은 실제 GUID 값을 표시합니다.)</span><span class="sxs-lookup"><span data-stu-id="d76be-108">(000000 indicates the actual GUID value.)</span></span>  
  
|<span data-ttu-id="d76be-109">GUID</span><span class="sxs-lookup"><span data-stu-id="d76be-109">GUID</span></span>|<span data-ttu-id="d76be-110">설명</span><span class="sxs-lookup"><span data-stu-id="d76be-110">Description</span></span>|<span data-ttu-id="d76be-111">레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="d76be-111">Registry key</span></span>|  
|----------|-----------------|------------------|  
|<span data-ttu-id="d76be-112">CLSID</span><span class="sxs-lookup"><span data-stu-id="d76be-112">CLSID</span></span>|<span data-ttu-id="d76be-113">클래스 식별자</span><span class="sxs-lookup"><span data-stu-id="d76be-113">Class identifier</span></span>|<span data-ttu-id="d76be-114">HKEY_CLASSES_ROOT\CLSID\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="d76be-114">HKEY_CLASSES_ROOT\CLSID\\{000…000}</span></span>|  
|<span data-ttu-id="d76be-115">IID</span><span class="sxs-lookup"><span data-stu-id="d76be-115">IID</span></span>|<span data-ttu-id="d76be-116">인터페이스 식별자</span><span class="sxs-lookup"><span data-stu-id="d76be-116">Interface identifier</span></span>|<span data-ttu-id="d76be-117">HKEY_CLASSES_ROOT\Interface\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="d76be-117">HKEY_CLASSES_ROOT\Interface\\{000…000}</span></span>|  
|<span data-ttu-id="d76be-118">LIBID</span><span class="sxs-lookup"><span data-stu-id="d76be-118">LIBID</span></span>|<span data-ttu-id="d76be-119">라이브러리 식별자</span><span class="sxs-lookup"><span data-stu-id="d76be-119">Library identifier</span></span>|<span data-ttu-id="d76be-120">HKEY_CLASSES_ROOT\TypeLib\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="d76be-120">HKEY_CLASSES_ROOT\TypeLib\\{000…000}</span></span>|  
|<span data-ttu-id="d76be-121">ProgID</span><span class="sxs-lookup"><span data-stu-id="d76be-121">ProgID</span></span>|<span data-ttu-id="d76be-122">프로그래밍 ID</span><span class="sxs-lookup"><span data-stu-id="d76be-122">Programmatic identifier</span></span>|<span data-ttu-id="d76be-123">HKEY_CLASSES_ROOT\000…000</span><span class="sxs-lookup"><span data-stu-id="d76be-123">HKEY_CLASSES_ROOT\000…000</span></span>|  
  
 <span data-ttu-id="d76be-124">HKCR\CLSID\\{0000…0000} 키에서 기본값은 클래스의 ProgID로 설정되며 새로 이름이 지정된 두 개의 값(Class 및 Assembly)이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d76be-124">Under the HKCR\CLSID\\{0000…0000} key, the default value is set to the ProgID of the class, and two new named values, Class and Assembly, are added.</span></span> <span data-ttu-id="d76be-125">런타임 시 레지스트리에서 Assembly 값을 읽어 런타임 어셈블리 확인자에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="d76be-125">The runtime reads the Assembly value from the registry and passes it on to the runtime assembly resolver.</span></span> <span data-ttu-id="d76be-126">어셈블리 확인자는 이름 및 버전 번호와 같은 어셈블리 정보를 기반으로 어셈블리를 찾으려 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76be-126">The assembly resolver attempts to locate the assembly, based on assembly information such as the name and version number.</span></span> <span data-ttu-id="d76be-127">어셈블리 확인자에서 어셈블리를 찾으려면 어셈블리가 다음 위치 중 하나에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76be-127">For the assembly resolver to locate an assembly, the assembly has to be in one of the following locations:</span></span>  
  
-   <span data-ttu-id="d76be-128">전역 어셈블리 캐시(강력한 이름의 어셈블리여야 함).</span><span class="sxs-lookup"><span data-stu-id="d76be-128">The global assembly cache (must be a strong-named assembly).</span></span>  
  
-   <span data-ttu-id="d76be-129">응용 프로그램 디렉터리.</span><span class="sxs-lookup"><span data-stu-id="d76be-129">In the application directory.</span></span> <span data-ttu-id="d76be-130">응용 프로그램 경로에서 로드된 어셈블리는 해당 응용 프로그램에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76be-130">Assemblies loaded from the application path are only accessible from that application.</span></span>  
  
-   <span data-ttu-id="d76be-131">**/codebase** 옵션을 사용하여 지정된 Regasm.exe의 파일 경로.</span><span class="sxs-lookup"><span data-stu-id="d76be-131">Along an file path specified with the **/codebase** option to Regasm.exe.</span></span>  
  
 <span data-ttu-id="d76be-132">Regasm.exe는 HKCR\CLSID\\{0000…0000} 키 아래에 InProcServer32 키도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d76be-132">Regasm.exe also creates the InProcServer32 key under the HKCR\CLSID\\{0000…0000} key.</span></span> <span data-ttu-id="d76be-133">키의 기본값은 공용 언어 런타임(Mscoree.dll)을 초기화하는 DLL의 이름으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d76be-133">The default value for the key is set to the name of the DLL that initializes the common language runtime (Mscoree.dll).</span></span>  
  
## <a name="examining-registry-entries"></a><span data-ttu-id="d76be-134">레지스트리 항목 검사</span><span class="sxs-lookup"><span data-stu-id="d76be-134">Examining Registry Entries</span></span>  
 <span data-ttu-id="d76be-135">COM interop에서는 모든 .NET Framework 클래스의 인스턴스를 만드는 표준 클래스 팩터리 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d76be-135">COM interop provides a standard class factory implementation to create an instance of any .NET Framework class.</span></span> <span data-ttu-id="d76be-136">클라이언트는 관리되는 DLL에서 **DllGetClassObject**를 호출하여 다른 COM 구성 요소에서와 마찬가지로 클래스 팩터리를 가져오고 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76be-136">Clients can call **DllGetClassObject** on the managed DLL to get a class factory and create objects, just as they would with any other COM component.</span></span>  
  
 <span data-ttu-id="d76be-137">`InprocServer32` 하위 키의 경우, 기존 COM 형식 라이브러리의 위치에 Mscoree.dll의 참조가 표시되어 공용 언어 런타임을 통해 관리 개체가 생성되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d76be-137">For the `InprocServer32` subkey, a reference to Mscoree.dll appears in place of a traditional COM type library to indicate that the common language runtime creates the managed object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d76be-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d76be-138">See Also</span></span>  
 [<span data-ttu-id="d76be-139">.NET Framework 구성 요소를 COM에 노출</span><span class="sxs-lookup"><span data-stu-id="d76be-139">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [<span data-ttu-id="d76be-140">방법: COM에서 .NET 형식 참조</span><span class="sxs-lookup"><span data-stu-id="d76be-140">How to: Reference .NET Types from COM</span></span>](../../../docs/framework/interop/how-to-reference-net-types-from-com.md)  
 [<span data-ttu-id="d76be-141">.NET 개체를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d76be-141">Calling a .NET Object</span></span>](http://msdn.microsoft.com/en-us/40c9626c-aea6-4bad-b8f0-c1de462efd33)  
 [<span data-ttu-id="d76be-142">COM 액세스를 위해 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="d76be-142">Deploying an Application for COM Access</span></span>](http://msdn.microsoft.com/en-us/fb63564c-c1b9-4655-a094-a235625882ce)
