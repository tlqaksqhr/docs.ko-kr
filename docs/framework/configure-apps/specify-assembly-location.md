---
title: 어셈블리를 지정 하&#39;s 위치
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 65bd075115e33486e86e8081b01b96db665e9da5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="specifying-an-assembly39s-location"></a><span data-ttu-id="faf20-102">어셈블리를 지정 하&#39;s 위치</span><span class="sxs-lookup"><span data-stu-id="faf20-102">Specifying an Assembly&#39;s Location</span></span>
<span data-ttu-id="faf20-103">두 가지 방법으로 어셈블리의 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-103">There are two ways to specify an assembly's location:</span></span>  
  
-   <span data-ttu-id="faf20-104">사용 하 여 [ \<코드 베이스 >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-104">Using the [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) element.</span></span>  
  
-   <span data-ttu-id="faf20-105">사용 하는 [ \<조사 >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-105">Using the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="faf20-106">사용할 수도 있습니다는 [.NET Framework 구성 도구 (Mscorcfg.msc)](http://msdn.microsoft.com/library/a7106c52-68da-490e-b129-971b2c743764) 어셈블리 위치를 지정 하거나 어셈블리를 조사 공용 언어 런타임에 대 한 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](http://msdn.microsoft.com/library/a7106c52-68da-490e-b129-971b2c743764) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="faf20-107">사용 하 여 \<s e > 요소</span><span class="sxs-lookup"><span data-stu-id="faf20-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="faf20-108">사용할 수는  **\<s e >** 도 어셈블리 버전을 리디렉션하는 컴퓨터 구성 또는 게시자 정책 파일에만 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="faf20-109">런타임에서 어셈블리 버전을 사용 하 여 결정을 버전을 결정 하는 파일의 코드 베이스 설정을 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="faf20-110">코드 베이스가 없습니다 지정 하는 경우 런타임에서 어셈블리에 대 한 일반적인 방법으로 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="faf20-111">자세한 내용은 참조 [런타임에서 어셈블리를 찾는 방법을](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-111">For details, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="faf20-112">다음 예제에서는 어셈블리의 위치를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-112">The following example shows how to specify an assembly's location.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="faf20-113">**버전** 특성이 모두 강력한 이름의 어셈블리에 대 한 필요 하나 강력한 이름이 아닌 어셈블리에 대 한 생략 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="faf20-114">**\<s e >** 요소를 사용 하려면는 **href** 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="faf20-115">에서는 버전 범위를 지정할 수 없습니다는  **\<s e >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="faf20-116">강력한 이름이 지정 되지 않은 어셈블리에 대 한 코드 베이스 힌트를 제공 하는 경우 힌트는 응용 프로그램 기준 위치 또는 응용 프로그램 기본 디렉터리의 하위 디렉터리를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="faf20-117">사용 하 여 \<조사 > 요소</span><span class="sxs-lookup"><span data-stu-id="faf20-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="faf20-118">런타임에서 검색 하 여 코드 베이스를 갖지 않는 어셈블리를 찾는 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="faf20-119">검색에 대 한 자세한 내용은 참조 [런타임에서 어셈블리를 찾는 방법을](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-119">For more information about probing, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="faf20-120">사용할 수는 [ \<조사 >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) 어셈블리를 찾을 때 런타임에서 검색 해야 하는 하위 디렉터리를 지정할 응용 프로그램 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-120">You can use the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="faf20-121">다음 예제에는 런타임에서 검색 해야 하는 디렉터리를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="faf20-122">**privatePath** 특성 런타임에서 어셈블리를 검색 해야 하는 디렉터리를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="faf20-123">응용 프로그램 C:\Program Files\MyApp에 있을 경우 런타임에서 C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin 및 C:\Program Files\MyApp\Bin3 코드 베이스를 지정 하지 않는 어셈블리를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="faf20-124">에 지정 된 디렉터리 **privatePath** 응용 프로그램 기본 디렉터리의 하위 디렉터리 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf20-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faf20-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="faf20-125">See Also</span></span>  
 [<span data-ttu-id="faf20-126">공용 언어 런타임의 어셈블리</span><span class="sxs-lookup"><span data-stu-id="faf20-126">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [<span data-ttu-id="faf20-127">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="faf20-127">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="faf20-128">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="faf20-128">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="faf20-129">.NET Framework 앱 구성</span><span class="sxs-lookup"><span data-stu-id="faf20-129">Configuring .NET Framework Apps</span></span>](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
