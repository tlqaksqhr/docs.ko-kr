---
title: '방법: DEVPATH를 사용하여 어셈블리 찾기'
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 918acf069c63d3aa8187f0f04e1f6c55ec961458
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="0c58a-102">방법: DEVPATH를 사용하여 어셈블리 찾기</span><span class="sxs-lookup"><span data-stu-id="0c58a-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="0c58a-103">개발자가 작성 하는 공유 어셈블리를 여러 응용 프로그램으로 제대로 작동 하는지 확인 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c58a-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="0c58a-104">지속적으로 개발 주기 동안 어셈블리를 전역 어셈블리 캐시에 저장, 대신 개발자 어셈블리에 대 한 빌드 출력 디렉터리를 가리키는 DEVPATH 환경 변수를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c58a-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="0c58a-105">예를 들어 가정 MySharedAssembly를 호출 하는 공유 어셈블리를 작성 하는 출력 디렉터리는 C:\MySharedAssembly\Debug 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c58a-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="0c58a-106">C:\MySharedAssembly\Debug DEVPATH 변수에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c58a-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="0c58a-107">그런 다음 지정 해야는 [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) 컴퓨터 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0c58a-107">You must then specify the [\<developmentMode>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="0c58a-108">이 요소에는 공용 언어 런타임 어셈블리를 찾는 DEVPATH를 사용 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c58a-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="0c58a-109">공유 어셈블리는 런타임에 검색 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c58a-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="0c58a-110">어셈블리 참조 사용을 확인 하기 위한 전용 디렉터리를 지정 하는 [ \<s e > 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) 또는 [ \<조사 > 요소](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) 에 설명 된 대로 구성 파일에 [어셈블리의 위치 지정](../../../docs/framework/configure-apps/specify-assembly-location.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0c58a-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) or [\<probing> Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  <span data-ttu-id="0c58a-111">또한 응용 프로그램 디렉터리의 하위 디렉터리에 어셈블리를 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c58a-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="0c58a-112">자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c58a-112">For more information, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c58a-113">이것이 개발만을 위한 고급 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0c58a-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="0c58a-114">다음 예제에서는 런타임에서 DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c58a-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c58a-115">예제</span><span class="sxs-lookup"><span data-stu-id="0c58a-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="0c58a-116">이 설정의 기본값은 false입니다.</span><span class="sxs-lookup"><span data-stu-id="0c58a-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c58a-117">개발 시에만이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c58a-117">Use this setting only at development time.</span></span> <span data-ttu-id="0c58a-118">런타임에서 DEVPATH에서 발견 된 강력한 이름의 어셈블리에 있는 버전을 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c58a-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="0c58a-119">단순히 처음 발견 한 어셈블리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c58a-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c58a-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c58a-120">See Also</span></span>  
 [<span data-ttu-id="0c58a-121">.NET Framework 앱 구성</span><span class="sxs-lookup"><span data-stu-id="0c58a-121">Configuring .NET Framework Apps</span></span>](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
