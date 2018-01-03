---
title: "방법: 등록이 필요 없는 활성화를 위한 .NET Framework 기반 COM 구성 요소 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- components [.NET Framework], manifest
- application manifests [.NET Framework]
- manifests [.NET Framework]
- registration-free COM interop, configuring .NET-based components
- activation, registration-free
ms.assetid: 32f8b7c6-3f73-455d-8e13-9846895bd43b
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a704930f707895e7f343566fab544e2f8b32b22c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-net-framework-based-com-components-for-registration-free-activation"></a><span data-ttu-id="719da-102">방법: 등록이 필요 없는 활성화를 위한 .NET Framework 기반 COM 구성 요소 구성</span><span class="sxs-lookup"><span data-stu-id="719da-102">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>
<span data-ttu-id="719da-103">.NET Framework 기반 구성 요소에 대한 등록 없는 활성화는 COM 구성 요소보다 약간 더 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-103">Registration-free activation for .NET Framework-based components is only slightly more complicated than it is for COM components.</span></span> <span data-ttu-id="719da-104">설치 프로그램에 다음 두 개의 매니페스트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-104">The setup requires two manifests:</span></span>  
  
-   <span data-ttu-id="719da-105">COM 응용 프로그램이 관리되는 구성 요소를 식별하려면 Win32 스타일 응용 프로그램 매니페스트가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-105">COM applications must have a Win32-style application manifest to identify the managed component.</span></span>  
  
-   <span data-ttu-id="719da-106">.NET Framework 기반 구성 요소에는 런타임에 필요한 활성화 정보를 위해 구성 요소 매니페스트가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-106">.NET Framework-based components must have a component manifest for activation information needed at run time.</span></span>  
  
 <span data-ttu-id="719da-107">이 항목에서는 응용 프로그램 매니페스트를 응용 프로그램에 연결하고, 구성 요소 매니페스트를 구성 요소에 연결하며, 구성 요소 매니페스트를 어셈블리에 포함하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-107">This topic describes how to associate an application manifest with an application; associate a component manifest with a component; and embed a component manifest in an assembly.</span></span>  
  
### <a name="to-create-an-application-manifest"></a><span data-ttu-id="719da-108">응용 프로그램 매니페스트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="719da-108">To create an application manifest</span></span>  
  
1.  <span data-ttu-id="719da-109">XML 편집기를 사용하여 하나 이상의 관리되는 구성 요소와 상호 운용되는 COM 응용 프로그램이 소유하는 응용 프로그램 매니페스트를 만들거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-109">Using an XML editor, create (or modify) the application manifest owned by the COM application that is interoperating with one or more managed components.</span></span>  
  
2.  <span data-ttu-id="719da-110">파일의 시작 부분에 다음과 같은 표준 헤더를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-110">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
     <span data-ttu-id="719da-111">매니페스트 요소와 해당 특성에 대 한 정보를 참조 하십시오. [응용 프로그램 매니페스트](https://msdn.microsoft.com/library/windows/desktop/aa374191.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-111">For information about manifest elements and their attributes, see [Application Manifests](https://msdn.microsoft.com/library/windows/desktop/aa374191.aspx).</span></span>  
  
3.  <span data-ttu-id="719da-112">매니페스트의 소유자를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-112">Identify the owner of the manifest.</span></span> <span data-ttu-id="719da-113">다음 예제에서는 `myComApp` 버전 1이 매니페스트 파일을 소유합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-113">In the following example, `myComApp` version 1 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="msil"   
      />  
    ```  
  
4.  <span data-ttu-id="719da-114">종속 어셈블리를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-114">Identify dependent assemblies.</span></span> <span data-ttu-id="719da-115">다음 예제에서는 `myComApp`이 `myManagedComp`에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="719da-115">In the following example, `myComApp` depends on `myManagedComp`.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="x86"   
                        publicKeyToken="8275b28176rcbbef"  
      />  
      <dependency>  
        <dependentAssembly>  
          <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myManagedComp"   
                        version="6.0.0.0"   
                        processorArchitecture="X86"   
                        publicKeyToken="8275b28176rcbbef"  
          />  
        </dependentAssembly>  
      </dependency>  
    </assembly>  
    ```  
  
5.  <span data-ttu-id="719da-116">매니페스트 파일을 저장하고 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-116">Save and name the manifest file.</span></span> <span data-ttu-id="719da-117">응용 프로그램 매니페스트 이름은 어셈블리 실행 파일의 이름 뒤에 .manifest 확장명이 추가된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="719da-117">The name of an application manifest is the name of the assembly executable followed by the .manifest extension.</span></span> <span data-ttu-id="719da-118">예를 들어 myComApp.exe의 응용 프로그램 매니페스트 파일 이름은 myComApp.exe.manifest입니다.</span><span class="sxs-lookup"><span data-stu-id="719da-118">For example, the application manifest file name for myComApp.exe is myComApp.exe.manifest.</span></span>  
  
 <span data-ttu-id="719da-119">COM 응용 프로그램과 동일한 디렉터리에 응용 프로그램 매니페스트를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="719da-119">You can install an application manifest in the same directory as the COM application.</span></span> <span data-ttu-id="719da-120">또는 응용 프로그램의 .exe 파일에 리소스로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="719da-120">Alternatively, you can add it as a resource to the application's .exe file.</span></span> <span data-ttu-id="719da-121">자세한 내용은 추가 정보를 참조 하십시오. [Side-by-side-어셈블리에 대 한](https://msdn.microsoft.com/library/windows/desktop/ff951640.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-121">For additional information, For more information, see [About Side-by-Side Assemblies](https://msdn.microsoft.com/library/windows/desktop/ff951640.aspx).</span></span>  
  
#### <a name="to-create-a-component-manifest"></a><span data-ttu-id="719da-122">구성 요소 매니페스트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="719da-122">To create a component manifest</span></span>  
  
1.  <span data-ttu-id="719da-123">XML 편집기를 사용하여 관리되는 어셈블리를 설명하는 구성 요소 매니페스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="719da-123">Using an XML editor, create a component manifest to describe the managed assembly.</span></span>  
  
2.  <span data-ttu-id="719da-124">파일의 시작 부분에 다음과 같은 표준 헤더를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-124">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
3.  <span data-ttu-id="719da-125">파일의 소유자를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-125">Identify the owner of the file.</span></span> <span data-ttu-id="719da-126">응용 프로그램 매니페스트 파일에 있는 `<dependentAssembly>` 요소의 `<assemblyIdentity>` 요소는 구성 요소 매니페스트에 있는 요소와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-126">The `<assemblyIdentity>` element of the `<dependentAssembly>` element in application manifest file must match the one in the component manifest.</span></span> <span data-ttu-id="719da-127">다음 예제에서는 `myManagedComp` 버전 1.2.3.4가 매니페스트 파일을 소유합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-127">In the following example, `myManagedComp` version 1.2.3.4 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"  
                        publicKeyToken="8275b28176rcbbef"  
                        processorArchitecture="msil"  
           />  
    ```  
  
4.  <span data-ttu-id="719da-128">어셈블리에 있는 각 클래스를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-128">Identify each class in the assembly.</span></span> <span data-ttu-id="719da-129">`<clrClass>` 요소를 사용하여 관리되는 어셈블리에 있는 각 클래스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-129">Use the `<clrClass>` element to uniquely identify each class in the managed assembly.</span></span> <span data-ttu-id="719da-130">`<assembly>` 요소의 하위 요소인 요소에는 다음 표에 설명된 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="719da-130">The element, which is a subelement of the `<assembly>` element, has the attributes described in the following table.</span></span>  
  
    |<span data-ttu-id="719da-131">특성</span><span class="sxs-lookup"><span data-stu-id="719da-131">Attribute</span></span>|<span data-ttu-id="719da-132">설명</span><span class="sxs-lookup"><span data-stu-id="719da-132">Description</span></span>|<span data-ttu-id="719da-133">필수</span><span class="sxs-lookup"><span data-stu-id="719da-133">Required</span></span>|  
    |---------------|-----------------|--------------|  
    |`clsid`|<span data-ttu-id="719da-134">활성화할 클래스를 지정하는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="719da-134">The identifier that specifies the class to be activated.</span></span>|<span data-ttu-id="719da-135">예</span><span class="sxs-lookup"><span data-stu-id="719da-135">Yes</span></span>|  
    |`description`|<span data-ttu-id="719da-136">구성 요소에 대해 사용자에게 알려주는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="719da-136">A string that informs the user about the component.</span></span> <span data-ttu-id="719da-137">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="719da-137">An empty string is the default.</span></span>|<span data-ttu-id="719da-138">아니요</span><span class="sxs-lookup"><span data-stu-id="719da-138">No</span></span>|  
    |`name`|<span data-ttu-id="719da-139">관리되는 클래스를 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="719da-139">A string that represents the managed class.</span></span>|<span data-ttu-id="719da-140">예</span><span class="sxs-lookup"><span data-stu-id="719da-140">Yes</span></span>|  
    |`progid`|<span data-ttu-id="719da-141">런타임에 바인딩된 활성화에 사용할 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="719da-141">The identifier to be used for late-bound activation.</span></span>|<span data-ttu-id="719da-142">아니요</span><span class="sxs-lookup"><span data-stu-id="719da-142">No</span></span>|  
    |`threadingModel`|<span data-ttu-id="719da-143">COM 스레딩 모델.</span><span class="sxs-lookup"><span data-stu-id="719da-143">The COM threading model.</span></span> <span data-ttu-id="719da-144">"Both"가 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="719da-144">"Both" is the default value.</span></span>|<span data-ttu-id="719da-145">아니요</span><span class="sxs-lookup"><span data-stu-id="719da-145">No</span></span>|  
    |`runtimeVersion`|<span data-ttu-id="719da-146">사용할 CLR(공용 언어 런타임) 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-146">Specifies the common language runtime (CLR) version to use.</span></span> <span data-ttu-id="719da-147">이 특성을 지정하지 않고 CLR이 아직 로드되지 않은 경우 CLR 버전 4 이전의 최신 설치된 CLR과 함께 구성 요소가 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="719da-147">If you do not specify this attribute, and the CLR is not already loaded, the component is loaded with the latest installed CLR prior to CLR version 4.</span></span> <span data-ttu-id="719da-148">v1.0.3705, v1.1.4322 또는 v2.0.50727을 지정하면 버전이 CLR 버전 4 이전의 최신 설치된 CLR 버전(일반적으로 v2.0.50727)으로 자동으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-148">If you specify v1.0.3705, v1.1.4322, or v2.0.50727, the version automatically rolls forward to the latest installed CLR version prior to CLR version 4 (usually v2.0.50727).</span></span> <span data-ttu-id="719da-149">다른 버전의 CLR이 이미 로드되었으며 지정된 버전을 In-Process Side-by-Side로 로드할 수 있는 경우 지정된 버전이 로드되고, 그러지 않으면 로드된 CLR이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="719da-149">If another version of the CLR is already loaded and the specified version can be loaded side-by-side in-process, the specified version is loaded; otherwise, the loaded CLR is used.</span></span> <span data-ttu-id="719da-150">이 경우 로드에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="719da-150">This might cause a load failure.</span></span>|<span data-ttu-id="719da-151">아니요</span><span class="sxs-lookup"><span data-stu-id="719da-151">No</span></span>|  
    |`tlbid`|<span data-ttu-id="719da-152">클래스에 대한 형식 정보를 포함하는 형식 라이브러리의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="719da-152">The identifier of the type library that contains type information about the class.</span></span>|<span data-ttu-id="719da-153">아니요</span><span class="sxs-lookup"><span data-stu-id="719da-153">No</span></span>|  
  
     <span data-ttu-id="719da-154">모든 특성 태그는 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-154">All attribute tags are case-sensitive.</span></span> <span data-ttu-id="719da-155">OLE/COM ObjectViewer(Oleview.exe)를 사용하여 어셈블리에 대해 내보낸 형식 라이브러리를 보면 CLSID, ProgID, 스레딩 모델, 런타임 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="719da-155">You can obtain CLSIDs, ProgIDs, threading models, and the runtime version by viewing the exported type library for the assembly with the OLE/COM ObjectViewer (Oleview.exe).</span></span>  
  
     <span data-ttu-id="719da-156">다음 구성 요소 매니페스트는 `testClass1` 및 `testClass2`라는 두 개의 클래스를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-156">The following component manifest identifies two classes, `testClass1` and `testClass2`.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4" />  
                        publicKeyToken="8275b28176rcbbef"  
           />  
           <clrClass  
                        clsid="{65722BE6-3449-4628-ABD3-74B6864F9739}"  
                        progid="myManagedComp.testClass1"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass1"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <clrClass  
                        clsid="{367221D6-3559-3328-ABD3-45B6825F9732}"  
                        progid="myManagedComp.testClass2"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass2"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <file name="MyManagedComp.dll">  
           </file>  
    </assembly>  
    ```  
  
5.  <span data-ttu-id="719da-157">매니페스트 파일을 저장하고 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-157">Save and name the manifest file.</span></span> <span data-ttu-id="719da-158">구성 요소 매니페스트 이름은 어셈블리 라이브러리의 이름 뒤에 .manifest 확장명이 추가된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="719da-158">The name of a component manifest is the name of the assembly library followed by the .manifest extension.</span></span> <span data-ttu-id="719da-159">예를 들어 myManagedComp.dll은 myManagedComp.manifest입니다.</span><span class="sxs-lookup"><span data-stu-id="719da-159">For example, the myManagedComp.dll is myManagedComp.manifest.</span></span>  
  
 <span data-ttu-id="719da-160">구성 요소 매니페스트를 어셈블리에 리소스로 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-160">You must embed the component manifest as a resource in the assembly.</span></span>  
  
#### <a name="to-embed-a-component-manifest-in-a-managed-assembly"></a><span data-ttu-id="719da-161">관리되는 어셈블리에 구성 요소 매니페스트를 포함하려면</span><span class="sxs-lookup"><span data-stu-id="719da-161">To embed a component manifest in a managed assembly</span></span>  
  
1.  <span data-ttu-id="719da-162">다음 문을 포함하는 리소스 스크립트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="719da-162">Create a resource script that contains the following statement:</span></span>  
  
     `RT_MANIFEST 1 myManagedComp.manifest`  
  
     <span data-ttu-id="719da-163">이 문에서 `myManagedComp.manifest`는 포함되는 구성 요소 매니페스트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="719da-163">In this statement, `myManagedComp.manifest` is the name of the component manifest being embedded.</span></span> <span data-ttu-id="719da-164">이 예제에서 스크립트 파일 이름은 `myresource.rc`입니다.</span><span class="sxs-lookup"><span data-stu-id="719da-164">For this example, the script file name is `myresource.rc`.</span></span>  
  
2.  <span data-ttu-id="719da-165">Microsoft Windows Resource Compiler(Rc.exe)를 사용하여 스크립트를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-165">Compile the script using the Microsoft Windows Resource Compiler (Rc.exe).</span></span> <span data-ttu-id="719da-166">명령 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-166">At the command prompt, type the following command:</span></span>  
  
     `rc myresource.rc`  
  
     <span data-ttu-id="719da-167">Rc.exe는 `myresource.res` 리소스 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-167">Rc.exe produces the `myresource.res` resource file.</span></span>  
  
3.  <span data-ttu-id="719da-168">어셈블리의 소스 파일을 다시 컴파일하고 **/win32res** 옵션을 사용하여 리소스 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="719da-168">Compile the assembly's source file again and specify the resource file by using the **/win32res** option:</span></span>  
  
    ```  
    /win32res:myresource.res  
    ```  
  
     <span data-ttu-id="719da-169">다시, `myresource.res`는 포함 리소스를 있는 리소스 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="719da-169">Again, `myresource.res` is the name of the resource file containing embedded resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="719da-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="719da-170">See Also</span></span>  
 [<span data-ttu-id="719da-171">등록이 필요 없는 COM interop</span><span class="sxs-lookup"><span data-stu-id="719da-171">Registration-Free COM Interop</span></span>](../../../docs/framework/interop/registration-free-com-interop.md)  
 [<span data-ttu-id="719da-172">등록이 필요 없는 COM Interop에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="719da-172">Requirements for Registration-Free COM Interop</span></span>](http://msdn.microsoft.com/en-us/0c43bc57-eecf-4e6c-8114-490141cce4da)  
 [<span data-ttu-id="719da-173">등록이 필요 없는 활성화를 위한 COM 구성 요소 구성</span><span class="sxs-lookup"><span data-stu-id="719da-173">Configuring COM Components for Registration-Free Activation</span></span>](http://msdn.microsoft.com/en-us/bfe9b02f-d964-4784-960e-a1f94692fbfe)  
 [<span data-ttu-id="719da-174">.NET 기반 구성 요소의 등록이 필요 없는 활성화: 연습</span><span class="sxs-lookup"><span data-stu-id="719da-174">Registration-Free Activation of .NET-Based Components: A Walkthrough</span></span>](http://go.microsoft.com/fwlink/?LinkId=158812)
