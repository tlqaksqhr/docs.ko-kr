---
title: '방법: 게시자 정책 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 91971e4d41c3a54fa72ae73a3655dab650019676
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="b1481-102">방법: 게시자 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="b1481-102">How to: Create a Publisher Policy</span></span>
<span data-ttu-id="b1481-103">어셈블리 공급 업체 응용 프로그램이 업그레이드 된 어셈블리와 함께 게시자 정책 파일을 포함 하 여 최신 버전의 어셈블리를 사용 해야 명시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="b1481-104">게시자 정책 파일이 어셈블리 리디렉션 및 코드 베이스 설정을 지정 하 고 응용 프로그램 구성 파일과 같은 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="b1481-105">게시자 정책 파일을 어셈블리로 컴파일되고 전역 어셈블리 캐시에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>  
  
 <span data-ttu-id="b1481-106">게시자 정책 만들기와 관련 된 세 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-106">There are three steps involved in creating a publisher policy:</span></span>  
  
1.  <span data-ttu-id="b1481-107">게시자 정책 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-107">Create a publisher policy file.</span></span>  
  
2.  <span data-ttu-id="b1481-108">게시자 정책 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-108">Create a publisher policy assembly.</span></span>  
  
3.  <span data-ttu-id="b1481-109">게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-109">Add the publisher policy assembly to the global assembly cache.</span></span>  
  
 <span data-ttu-id="b1481-110">게시자 정책에 대 한 스키마에서 설명 [어셈블리 버전 리디렉션](../../../docs/framework/configure-apps/redirect-assembly-versions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-110">The schema for publisher policy is described in [Redirecting Assembly Versions](../../../docs/framework/configure-apps/redirect-assembly-versions.md).</span></span> <span data-ttu-id="b1481-111">다음 예제에서는 게시자 정책 파일 버전으로 리디렉션하는 `myAssembly` 다른 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->  
         <bindingRedirect oldVersion="1.0.0.0"  
                          newVersion="2.0.0.0"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="b1481-112">코드 베이스를 지정 하는 방법을 알아보려면 참조 [어셈블리의 위치 지정](../../../docs/framework/configure-apps/specify-assembly-location.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-112">To learn how to specify a code base, see [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  
  
## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="b1481-113">게시자 정책 어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="b1481-113">Creating the Publisher Policy Assembly</span></span>  
 <span data-ttu-id="b1481-114">사용 하 여는 [어셈블리 링커 (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) 게시자 정책 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-114">Use the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>  
  
#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="b1481-115">게시자 정책 어셈블리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="b1481-115">To create a publisher policy assembly</span></span>  
  
1.  <span data-ttu-id="b1481-116">명령 프롬프트에서 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-116">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="b1481-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span><span class="sxs-lookup"><span data-stu-id="b1481-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span></span>  
  
     <span data-ttu-id="b1481-118">이 명령에서</span><span class="sxs-lookup"><span data-stu-id="b1481-118">In this command:</span></span>  
  
    -   <span data-ttu-id="b1481-119">*publisherPolicyFile* 인수는 게시자 정책 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-119">The *publisherPolicyFile* argument is the name of the publisher policy file.</span></span>  
  
    -   <span data-ttu-id="b1481-120">*publisherPolicyAssemblyFile* 인수는이 명령 결과인 게시자 정책 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-120">The *publisherPolicyAssemblyFile* argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="b1481-121">어셈블리 파일 이름 형식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-121">The assembly file name must follow the format:</span></span>  
  
         <span data-ttu-id="b1481-122">**policy.**</span><span class="sxs-lookup"><span data-stu-id="b1481-122">**policy.**</span></span> <span data-ttu-id="b1481-123">*majorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="b1481-123">*majorNumber* **.**</span></span> <span data-ttu-id="b1481-124">*minorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="b1481-124">*minorNumber* **.**</span></span> <span data-ttu-id="b1481-125">*mainAssemblyName* **.dll**</span><span class="sxs-lookup"><span data-stu-id="b1481-125">*mainAssemblyName* **.dll**</span></span>  
  
    -   <span data-ttu-id="b1481-126">*keyPairFile* 인수는 키 쌍을 포함 하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-126">The *keyPairFile* argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="b1481-127">어셈블리와 동일한 키 쌍을 사용 하 여 게시자 정책 어셈블리에 서명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-127">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>  
  
    -   <span data-ttu-id="b1481-128">*processorArchitecture* 인수 특정 프로세서 관련 어셈블리의 대상 플랫폼을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-128">The *processorArchitecture* argument identifies the platform targeted by a processor-specific assembly.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b1481-129">특정 프로세서 아키텍처를 대상으로 하는 기능은.NET Framework 버전 2.0의에서 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-129">The ability to target a specific processor architecture is new in the .NET Framework version 2.0.</span></span>  
  
     <span data-ttu-id="b1481-130">다음 명령은 라는 게시자 정책 어셈블리를 만듭니다 `policy.1.0.myAssembly` 라는 게시자 정책 파일에서 `pub.config`에 있는 키 쌍을 사용 하 여 어셈블리에 강력한 이름을 할당는 `sgKey.snk` 파일과 어셈블리는 x86 대상으로 지정 함을 지정 합니다. 프로세서 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-130">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     <span data-ttu-id="b1481-131">게시자 정책 어셈블리에 적용 되는 어셈블리의 프로세서 아키텍처를 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-131">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="b1481-132">따라서, 어셈블리에 있는 경우는 <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> 값 <xref:System.Reflection.ProcessorArchitecture.MSIL>, 해당 어셈블리에 대 한 게시자 정책 어셈블리를 사용 하 여 만들어야 합니다 `/platform:anycpu`합니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-132">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="b1481-133">별도 변경 하면 각 특정 프로세서 관련 어셈블리에 대 한 게시자 정책 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-133">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>  
  
     <span data-ttu-id="b1481-134">이 규칙의 결과 어셈블리에 대 한 프로세서 아키텍처를 변경 하기 위해 버전 번호의 주 또는 보조 구성 요소 변경 해야 되므로 올바른 프로세서 아키텍처와 새 게시자 정책 어셈블리를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-134">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="b1481-135">어셈블리의 서로 다른 프로세서 아키텍처 되 면 이전 게시자 정책 어셈블리에서 어셈블리를 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-135">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>  
  
     <span data-ttu-id="b1481-136">다른 결과 항상 프로세서 아키텍처를 지정 하기 때문에 이전 버전의.NET Framework를 사용 하 여 컴파일된 어셈블리에 대 한 게시자 정책 어셈블리를 만드는 버전 2.0 링커를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-136">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="b1481-137">게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가</span><span class="sxs-lookup"><span data-stu-id="b1481-137">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>  
 <span data-ttu-id="b1481-138">사용 하 여는 [전역 어셈블리 캐시 도구 (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) 게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-138">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="b1481-139">게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="b1481-139">To add the publisher policy assembly to the global assembly cache</span></span>  
  
1.  <span data-ttu-id="b1481-140">명령 프롬프트에서 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-140">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="b1481-141">**gacutil /i**  *publisherPolicyAssemblyFile*</span><span class="sxs-lookup"><span data-stu-id="b1481-141">**gacutil /i**  *publisherPolicyAssemblyFile*</span></span>  
  
     <span data-ttu-id="b1481-142">다음 명령은 추가 `policy.1.0.myAssembly.dll` 전역 어셈블리 캐시에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-142">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b1481-143">원래 게시자 정책 파일이 어셈블리와 동일한 디렉터리에 있는 경우가 아니면 게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1481-143">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file is located in the same directory as the assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1481-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1481-144">See Also</span></span>  
 [<span data-ttu-id="b1481-145">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b1481-145">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="b1481-146">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="b1481-146">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="b1481-147">응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="b1481-147">Configuring Apps</span></span>](../../../docs/framework/configure-apps/index.md)  
 [<span data-ttu-id="b1481-148">.NET Framework 앱 구성</span><span class="sxs-lookup"><span data-stu-id="b1481-148">Configuring .NET Framework Apps</span></span>](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 [<span data-ttu-id="b1481-149">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b1481-149">Runtime Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="b1481-150">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="b1481-150">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="b1481-151">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="b1481-151">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
